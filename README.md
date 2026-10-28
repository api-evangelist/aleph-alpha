# Aleph Alpha

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Aleph Alpha is a Heidelberg, Germany based sovereign AI company building PhariaAI, an end-to-end, customizable AI suite for enterprises and governments that can be deployed on-premise or hosted. The stack combines leading open-source and proprietary large language models with Aleph Alpha's own Pharia-1-LLM model family and its research into transparency, explainability and domain-specific performance. PhariaAI is exposed through six documented HTTP APIs — PhariaInference (completion, chat, embeddings, tokenization), PhariaData (repositories, datasets, transformations), PhariaSearch / Document Index (semantic search over a knowledge base), PhariaStudio (projects, traces, evaluation, benchmarks), PhariaOS (cluster, use case and model lifecycle management) and a stateful, OpenAI-compatible Responses API with MCP tool calling — each published as an OpenAPI or Swagger definition on the Aleph Alpha documentation site. First-party SDKs ship for Python and Rust, alongside a CLI for publishing WebAssembly skills to the Pharia Kernel.

**Areas:** Company · Artificial Intelligence · Machine Learning · LLM · Generative AI · Sovereign AI · Inference · Embeddings · Semantic Search · Vector Search · Agents · MCP

## Aleph Alpha on APIs.io

Everything profiled for Aleph Alpha is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/aleph-alpha/](https://apis.io/providers/aleph-alpha/)** — or go straight to one of the APIs or properties below.

### APIs (37)

- [Aleph Alpha API description API](https://apis.io/apis/aleph-alpha/aleph-alpha-api-description-api/) — The API description API from Aleph Alpha — 2 operation(s) for api description.
- [Aleph Alpha Application Traces API](https://apis.io/apis/aleph-alpha/aleph-alpha-application-traces-api/) — The Application Traces API from Aleph Alpha — 2 operation(s) for application traces.
- [Aleph Alpha Benchmark Executions API](https://apis.io/apis/aleph-alpha/aleph-alpha-benchmark-executions-api/) — Endpoints for handling execution instances of benchmarks. These provides an overview of all evaluation steps during execution (run, evaluation, aggregation).
- [Aleph Alpha Benchmarks API](https://apis.io/apis/aleph-alpha/aleph-alpha-benchmarks-api/) — Endpoints for handling benchmarks. A Benchmark provides a way to compare and evaluate the quality of your task results for a specific dataset.
- [Aleph Alpha Cluster API](https://apis.io/apis/aleph-alpha/aleph-alpha-cluster-api/) — The cluster API from Aleph Alpha — 4 operation(s) for cluster.
- [Aleph Alpha Collection API](https://apis.io/apis/aleph-alpha/aleph-alpha-collection-api/) — Management of document collections
- [Aleph Alpha Connectors API](https://apis.io/apis/aleph-alpha/aleph-alpha-connectors-api/) — Available connectors for the Data Platform to ingest data from external sources.
- [Aleph Alpha Conversations API](https://apis.io/apis/aleph-alpha/aleph-alpha-conversations-api/) — Create, retrieve, update, delete, and list conversations.
- [Aleph Alpha Datasets API](https://apis.io/apis/aleph-alpha/aleph-alpha-datasets-api/) — Represents the primary data abstraction within the data platform, serving as a structured collection of data points. Datasets can be either manually…
- [Aleph Alpha Document API](https://apis.io/apis/aleph-alpha/aleph-alpha-document-api/) — A Document represents an individual item stored within a Search Store. Documents can contain content from various modalities, such as text, images, or…
- [Aleph Alpha Downloads API](https://apis.io/apis/aleph-alpha/aleph-alpha-downloads-api/) — Endpoints for managing and tracking dataset download requests within the data platform. These endpoints allow users to initiate new downloads, retrieve…
- [Aleph Alpha Evaluation Datasets API](https://apis.io/apis/aleph-alpha/aleph-alpha-evaluation-datasets-api/) — Endpoints for handling evaluation datasets, which are specific datasets to be used for evaluation in the Pharia Studio SDK.
- [Aleph Alpha Events API](https://apis.io/apis/aleph-alpha/aleph-alpha-events-api/) — Endpoints for handling Events. Events capture detailed information about specific occurrences within a Span. This includes logs, exceptions, and other…
- [Aleph Alpha Filter Index API](https://apis.io/apis/aleph-alpha/aleph-alpha-filter-index-api/) — Management of search filter indexes
- [Aleph Alpha Guardrails API](https://apis.io/apis/aleph-alpha/aleph-alpha-guardrails-api/) — Check content against guardrail policies.
- [Aleph Alpha Index API](https://apis.io/apis/aleph-alpha/aleph-alpha-index-api/) — Management of search indexes
- [Aleph Alpha Lineages API](https://apis.io/apis/aleph-alpha/aleph-alpha-lineages-api/) — Lineages represent the results of a benchmark execution. A single lineage represents an evaluation of a single example with a task and evaluation logic.…
- [Aleph Alpha Models API](https://apis.io/apis/aleph-alpha/aleph-alpha-models-api/) — The models API from Aleph Alpha — 6 operation(s) for models.
- [Aleph Alpha Namespace API](https://apis.io/apis/aleph-alpha/aleph-alpha-namespace-api/) — Management of namespaces
- [Aleph Alpha Operations API](https://apis.io/apis/aleph-alpha/aleph-alpha-operations-api/) — Health checks and operational endpoints.
- [Aleph Alpha Permissions API](https://apis.io/apis/aleph-alpha/aleph-alpha-permissions-api/) — The permissions API from Aleph Alpha — 1 operation(s) for permissions.
- [Aleph Alpha Projects API](https://apis.io/apis/aleph-alpha/aleph-alpha-projects-api/) — A Project is an abstraction representing a group of running operations associated with the same task in the Studio. Endpoints under this tag allow you to…
- [Aleph Alpha Repositories API](https://apis.io/apis/aleph-alpha/aleph-alpha-repositories-api/) — A collection of data organized by a common type, modality, and schema, stored within datasets (lists of data points) in the repositories. To share datasets…
- [Aleph Alpha Responses API](https://apis.io/apis/aleph-alpha/aleph-alpha-responses-api/) — Create, retrieve, and delete responses. Supports streaming and multi-turn conversations via response chaining.
- [Aleph Alpha Search Store API](https://apis.io/apis/aleph-alpha/aleph-alpha-search-store-api/) — A Search Store is a structured data repository optimized for indexing and retrieving searchable entities. It supports full-text search, metadata-based…
- [Aleph Alpha Service API](https://apis.io/apis/aleph-alpha/aleph-alpha-service-api/) — Service health and status
- [Aleph Alpha Spans API](https://apis.io/apis/aleph-alpha/aleph-alpha-spans-api/) — Endpoints for managing Spans. A Span is a single unit of work within a Trace and represents an individual operation in the execution sequence. Spans help in…
- [Aleph Alpha Stages API](https://apis.io/apis/aleph-alpha/aleph-alpha-stages-api/) — Stages serve as the data platform's entry point for data collection, where source files are securely stored, enabling subsequent transformations and dataset…
- [Aleph Alpha Steering API](https://apis.io/apis/aleph-alpha/aleph-alpha-steering-api/) — The steering API from Aleph Alpha — 1 operation(s) for steering.
- [Aleph Alpha Tasks API](https://apis.io/apis/aleph-alpha/aleph-alpha-tasks-api/) — Requests for different types of tasks you can request with our models.
- [Aleph Alpha Tokens API](https://apis.io/apis/aleph-alpha/aleph-alpha-tokens-api/) — Manage tokens associated with your user account for API access.
- [Aleph Alpha Traces API](https://apis.io/apis/aleph-alpha/aleph-alpha-traces-api/) — Trace management endpoints. A Trace provides a mechanism similar to OpenTelemetry for tracking the execution flow of a task. It allows you to monitor and…
- [Aleph Alpha Transformations API](https://apis.io/apis/aleph-alpha/aleph-alpha-transformations-api/) — Available transformations can be applied to an input data object of type A to produce an output data object of type B. The output data object will consist…
- [Aleph Alpha Users API](https://apis.io/apis/aleph-alpha/aleph-alpha-users-api/) — The users API from Aleph Alpha — 2 operation(s) for users.
- [Aleph Alpha V1/models API](https://apis.io/apis/aleph-alpha/aleph-alpha-v1-models-api/) — The v1/models API from Aleph Alpha — 4 operation(s) for v1/models.
- [Aleph Alpha Workspaces API](https://apis.io/apis/aleph-alpha/aleph-alpha-workspaces-api/) — A Workspace is a shared environment where users can collaborate on projects. Workspaces help in organizing and managing projects in large organizations…
- [Aleph Alpha Use Cases API](https://apis.io/apis/aleph-alpha/aleph-alpha-use-cases-api/) — **Usecases (Applications)** Usecases are full-stack end to end AI applications.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [aleph-alpha-mcp.yml](https://apis.io/servers/aleph-alpha/aleph-alpha-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Aleph Alpha Agentic Access](https://apis.io/agentic-access/aleph-alpha/aleph-alpha-agentic-access/)

#### Collections (37)

Postman and Open Collection request collections.

- [Aleph Alpha API description API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-api-description-api/)
- [PhariaStudio Application Traces API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-application-traces-api/)
- [PhariaStudio Benchmark Executions API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-benchmark-executions-api/)
- [PhariaStudio Benchmarks API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-benchmarks-api/)
- [PhariaOS Manager Cluster API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-cluster-api/)
- [Aleph Alpha Document Index Collection API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-collection-api/)
- [PhariaData Connectors API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-connectors-api/)
- [Stateful Responses Conversations API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-conversations-api/)
- [PhariaData Datasets API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-datasets-api/)
- [Aleph Alpha Document API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-document-api/)
- [PhariaData Downloads API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-downloads-api/)
- [PhariaStudio Evaluation Datasets API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-evaluation-datasets-api/)
- [PhariaStudio Events API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-events-api/)
- [Aleph Alpha Document Index Filter Index API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-filter-index-api/)
- [Stateful Responses Guardrails API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-guardrails-api/)
- [Aleph Alpha Document Index API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-index-api/)
- [PhariaStudio Lineages API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-lineages-api/)
- [Aleph Alpha Models API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-models-api/)
- [Aleph Alpha Document Index Namespace API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-namespace-api/)
- [Stateful Responses Operations API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-operations-api/)
- [Aleph Alpha Permissions API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-permissions-api/)
- [PhariaStudio Projects API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-projects-api/)
- [PhariaData Repositories API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-repositories-api/)
- [Stateful Responses API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-responses-api/)
- [PhariaData Search Store API](https://apis.io/collections/aleph-alpha/open-aleph-alpha-search-store-api/)
- …and 12 more published on APIs.io

#### Overlays (6)

OpenAPI overlays, including conversational phrasing for each operation.

- [Aleph Alpha Pharia Data Overlay](https://apis.io/overlays/aleph-alpha/aleph-alpha-pharia-data-overlay/)
- [Aleph Alpha Pharia Inference Overlay](https://apis.io/overlays/aleph-alpha/aleph-alpha-pharia-inference-overlay/)
- [Aleph Alpha Pharia Os Overlay](https://apis.io/overlays/aleph-alpha/aleph-alpha-pharia-os-overlay/)
- [Aleph Alpha Pharia Search Overlay](https://apis.io/overlays/aleph-alpha/aleph-alpha-pharia-search-overlay/)
- [Aleph Alpha Pharia Studio Overlay](https://apis.io/overlays/aleph-alpha/aleph-alpha-pharia-studio-overlay/)
- [Aleph Alpha Responses Overlay](https://apis.io/overlays/aleph-alpha/aleph-alpha-responses-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Aleph Alpha Authentication](https://apis.io/security/aleph-alpha/aleph-alpha-authentication/)
- [Aleph Alpha Domain Security](https://apis.io/security/aleph-alpha/aleph-alpha-domain-security/)
- [Aleph Alpha Trust Center](https://apis.io/security/aleph-alpha/aleph-alpha-trust-center/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://aleph-alpha.com/en/)
- [Documentation](https://docs.aleph-alpha.com/)
- [Getting started](https://docs.aleph-alpha.com/phariaai-dev-guide/latest/phariaai-applications/quick-start-custom-apps.html)
- [API reference](https://docs.aleph-alpha.com/phariaai-dev-guide/latest/pharia-openapi/index.html)
- [Support](https://supportportal.aleph-alpha.com/)
- [Changelog](https://docs.aleph-alpha.com/phariaai-home/latest/release-notes/index.html)
- [Blog](https://aleph-alpha.com/blog/)
- [Compliance](https://www.dqsglobal.com/en/customer-database/aleph-alpha-gmbh)
- [Privacy policy](https://aleph-alpha.com/data-privacy/)
- [GitHub](https://github.com/Aleph-Alpha)

## API Evangelist rating

**Kin Score 45.3** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 70.0 |
| Contract quality | 50.9 |
| Contract governance | 4.5 |
| Operational transparency | 26.3 |
| Developer ergonomics | 72.0 |
| Access clarity | 26.3 |

**Agent readiness 30.3** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 23.6** — Government & Public Sector

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/aleph-alpha/](https://apis.io/providers/aleph-alpha/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Aleph Alpha: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/aleph-alpha/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
