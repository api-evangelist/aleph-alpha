---
name: Build and query a semantic search index with the Aleph Alpha Document Index
description: Create a namespace, collection and index in PhariaSearch, ingest documents, and run semantic search with relevance filtering.
api: openapi/aleph-alpha-pharia-search-openapi.json
operations: []
---

# Build and query a semantic search index

The Document Index (PhariaSearch) provides semantic search over your knowledge base. It handles
chunking and embedding and keeps embeddings in sync as documents change.

> **Note on operation identifiers.** The published PhariaSearch OpenAPI declares no `operationId`
> on any of its 34 operations, so every step below is grounded in the spec's method + path rather
> than a named operation. This is a real gap in the contract, not an omission here.

## Authentication

`Authorization: Bearer <token>` (securityScheme `token`, an HTTP bearer JWT).

## Steps

1. **Create the namespace** — `PUT /namespaces/{namespace}`. Idempotent: re-running converges on
   the same namespace rather than erroring.
2. **Create the collection** — `PUT /collections/{namespace}/{collection}`.
3. **Define the index** — `PUT /indexes/{namespace}/{index}` to declare the embedding/chunking
   configuration, then attach it with
   `PUT /collections/{namespace}/{collection}/indexes/{index}`.
4. **Add filter indexes if you need metadata filtering** —
   `PUT /filter_indexes/{namespace}/{filterIndex}`, attached with
   `PUT /collections/{namespace}/{collection}/indexes/{index}/filter_indexes/{filterIndex}`.
5. **Ingest documents** — `PUT /collections/{namespace}/{collection}/docs/{name}`. The document
   name is caller-chosen, so re-ingestion updates in place instead of duplicating.
6. **Wait for indexing** — poll `GET /collections/{namespace}/{collection}/progress` and
   `GET /collections/{namespace}/{collection}/transitioning`. Embedding is asynchronous; do not
   search immediately after a bulk load.
7. **Search** — `POST /collections/{namespace}/{collection}/indexes/{index}/search`.
8. **Inspect what matched** — `GET /collections/{namespace}/{collection}/docs/{name}` for the
   document, `.../docs/{name}/versions` for its history, and
   `.../docs/{name}/indexes/{index}/chunks` for the exact chunks that were embedded.

## Rules

- **Prefer `minRelevancy` over `minScore` for a quality gate.** `minScore` filters the dense
  candidate pool inside Qdrant *before* fusion; `minRelevancy` (added in PhariaAI v1.260500.0 on
  the search store search API) is applied *after* all scoring and fusion, directly on the final
  score returned to the caller.
- **Every create is a `PUT`.** There is no idempotency key because there does not need to be —
  the write surface is content-addressed by caller-chosen name. Deletes are not reversible.
- **Health endpoints are not search endpoints** — `GET /health/liveness` and
  `GET /health/readiness` are for operators.
