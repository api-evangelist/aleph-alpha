---
name: Generate text with the Aleph Alpha PhariaInference API
description: Discover which models a PhariaAI installation serves, then run a completion or an OpenAI-compatible chat completion against one of them, including token accounting.
api: openapi/aleph-alpha-pharia-inference-openapi.json
operations: [availableModels, modelSettings, complete, chatCompletions, tokenize, detokenize, getModelTokenizer, version]
---

# Generate text with PhariaInference

The PhariaInference API is Aleph Alpha's inference surface. The hosted gateway is
`https://api.aleph-alpha.com`; a self-hosted PhariaAI installation serves the same contract at
`{your-pharia-host}/v1`.

## Authentication

Every call needs `Authorization: Bearer <token>`. Get the token from PhariaStudio (profile icon →
**Copy Bearer Token**) or mint one with `newToken`. Calling any path without a token returns
`401 No client token provided`.

## Steps

1. **Confirm the deployment version** — call `version` (`GET /version`). This is the only
   anonymous endpoint on the hosted gateway and tells you which PhariaInference major you are
   talking to (4.7.0 at time of writing). Do not assume request shapes across majors; each
   version has its own published OpenAPI document.
2. **List the models** — call `availableModels` (`GET /models_available`). Never hard-code a model
   name: a PhariaAI installation only serves the models its operator deployed. Use `modelSettings`
   (`GET /model-settings`) if you need the configured limits for those models.
3. **Count tokens before you spend them** — call `tokenize` with the prompt and the chosen model
   to check it fits the context window, and `getModelTokenizer` if you need the tokenizer itself.
   `detokenize` reverses it.
4. **Generate** — pick one:
   - `complete` (`POST /complete`) for raw completion, or `completeJson` for a JSON-constrained
     completion.
   - `chatCompletions` (`POST /chat/completions`) for the OpenAI-compatible chat shape. Prefer
     this one if you already have OpenAI client code — point `base_url` at the deployment and it
     works unmodified.
5. **Stream if the response is long** — both completion endpoints stream over Server-Sent Events.

## Rules

- **Handle 503 as backpressure, not failure.** The scheduler queues tasks per model. Under peak
  load it returns `503` with *"Sorry we had to reject your request because we could not guarantee
  to finish it in a reasonable timeframe."* Back off and retry, or switch to another model from
  step 2. Timeout `500`s often accompany a full queue.
- **There is no idempotency key.** `POST /complete` and `POST /chat/completions` are not
  idempotent — a blind retry generates (and bills) a second completion. Retry only on `503`/`5xx`
  where you know no response was produced.
- **No rate-limit headers are published.** Do not parse `X-RateLimit-*`; use the `503` signal.
- Errors use the envelope `{"error": {"message", "type", "param", "code"}}` — see
  `errors/aleph-alpha-problem-types.yml`.
