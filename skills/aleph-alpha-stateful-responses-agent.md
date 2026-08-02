---
name: Run a multi-turn agent on the Aleph Alpha Responses API
description: Use the Stateful Responses API to hold a conversation, chain turns server-side with previous_response_id, call tools, and clean up stored data.
api: openapi/aleph-alpha-responses-openapi.json
operations: [get_models_endpoint_models_get, post_responses_endpoint_v1_responses_post, get_responses_endpoint_v1_responses__response_id__get, update_response_endpoint_v1_responses__response_id__patch, delete_response_endpoint_v1_responses__response_id__delete, post_check_endpoint_v1_check_post, create_conversation_endpoint_v1_conversations_post, list_conversations_endpoint_v1_conversations_get, get_conversation_endpoint_v1_conversations__conversation_id__get, list_conversation_responses_endpoint_v1_conversations__conversation_id__responses_get, delete_conversation_endpoint_v1_conversations__conversation_id__delete, recover_conversation_endpoint_v1_conversations__conversation_id__patch]
---

# Run a multi-turn agent on Stateful Responses

The Stateful Responses API implements the OpenAI Responses API specification, so the OpenAI Python
SDK, PydanticAI and LangGraph (via `langchain-openai`) work against it by pointing `base_url` at
the deployment. What it adds on top is server-side conversation persistence, guardrails and
server-executed MCP tools.

## Authentication

`Authorization: Bearer $AA_TOKEN` on every call.

## Steps

1. **Pick a model** — `get_models_endpoint_models_get` (`GET /models`). Tool-calling requires a
   tool-capable model; the docs use `qwen3-32b-tool`.
2. **Optionally open a conversation** — `create_conversation_endpoint_v1_conversations_post`
   (`POST /v1/conversations`) if you want an explicit container you can list and delete later.
3. **Send the first turn** — `post_responses_endpoint_v1_responses_post` (`POST /v1/responses`)
   with `model` and `input`. Add `instructions` for the system prompt; it carries forward on later
   turns without resending.
4. **Chain the next turn** — send `previous_response_id` set to the previous response's `id`. The
   server reconstructs the full history; you do not resend the transcript.
5. **Handle tools**:
   - *Function tools (client-executed)*: the response comes back with a `function_call` output
     carrying `name`, `call_id` and `arguments`. Execute it yourself, then post a
     `function_call_output` with the same `call_id` plus `previous_response_id`, re-sending the
     same `tools` array.
   - *MCP tools (server-executed)*: the service connects to the MCP endpoint, runs the tool and
     feeds the result back to the model in an agentic loop. The LLM backend never sees the tool
     calls. MCP tool calls have configurable timeouts (added in PhariaAI v1.260300.0).
6. **Screen input if required** — `post_check_endpoint_v1_check_post` (`POST /v1/check`) runs the
   guardrail check (LlamaGuard integration) independently of a generation.
7. **Read back or replay** — `get_responses_endpoint_v1_responses__response_id__get`
   (`GET /v1/responses/{response_id}`), or append `?stream=true` to replay it as SSE.
8. **Clean up** — `delete_response_endpoint_v1_responses__response_id__delete` and
   `delete_conversation_endpoint_v1_conversations__conversation_id__delete`. Both soft-delete by
   default; `recover_conversation_endpoint_v1_conversations__conversation_id__patch` undoes a soft
   delete, and admins can read soft-deleted responses with `include_deleted=true`.

## Rules

- **`store=false` breaks chaining.** A non-stored response has no history entry, so any later call
  setting `previous_response_id` to it returns `404 not_found_error` / `response_not_found`. Use
  `store=false` only for one-off classification or extraction.
- **Deleting an in-flight response returns `425 too_early_error` (`response_in_progress`).** Wait
  for completion or failure, then retry.
- **Hard delete is irreversible.** It exists for GDPR erasure. Prefer the default soft delete for
  routine cleanup.
- Stored responses and conversations also expire under an automatic retention policy — do not
  treat the API as durable storage.
