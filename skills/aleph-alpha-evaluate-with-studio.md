---
name: Evaluate a PhariaAI application with PhariaStudio benchmarks and traces
description: Create a project, upload an evaluation dataset, run a benchmark, read the lineages, and correlate the run against OTLP traces.
api: openapi/aleph-alpha-pharia-studio-openapi.json
operations: [create_project_projects_post, get_many_projects_projects_get, create_dataset_projects__project_id__evaluation_datasets_post, get_dataset_datapoints_projects__project_id__evaluation_datasets__dataset_id__datapoints_get, create_benchmark_projects__project_id__evaluation_benchmarks_post, create_benchmark_execution_projects__project_id__evaluation_benchmarks__benchmark_id__executions_post, get_benchmark_execution_projects__project_id__evaluation_benchmarks__benchmark_id__executions__execution_id__get, get_many_benchmark_lineages_projects__project_id__evaluation_benchmarks__benchmark_id__executions__execution_id__lineages_get, receive_otlp_traces_projects__project_id__traces_v2_post, get_traces_projects__project_id__traces_v2_get, get_all_model_cards_models_get]
---

# Evaluate an application with PhariaStudio

PhariaStudio is the workspace where PhariaAI applications are built, debugged, evaluated and
traced. Its API makes projects, evaluation datasets, benchmarks, executions, lineages, traces and
spans first-class resources.

## Authentication

`Authorization: Bearer <token>` (securityScheme `BearerAuth`).

## Steps

1. **Create or find the project** — `create_project_projects_post` (`POST /projects`) or
   `get_many_projects_projects_get` (`GET /projects`). Everything else is scoped to a
   `project_id`.
2. **Check which models the installation exposes** — `get_all_model_cards_models_get`
   (`GET /models`).
3. **Upload the evaluation dataset** —
   `create_dataset_projects__project_id__evaluation_datasets_post`
   (`POST /projects/{project_id}/evaluation/datasets`). Verify it landed with
   `get_dataset_datapoints_projects__project_id__evaluation_datasets__dataset_id__datapoints_get`.
4. **Define the benchmark** —
   `create_benchmark_projects__project_id__evaluation_benchmarks_post`
   (`POST /projects/{project_id}/evaluation/benchmarks`), binding the dataset and the evaluation
   logic.
5. **Run it** —
   `create_benchmark_execution_projects__project_id__evaluation_benchmarks__benchmark_id__executions_post`,
   then poll
   `get_benchmark_execution_projects__project_id__evaluation_benchmarks__benchmark_id__executions__execution_id__get`
   until the execution completes.
6. **Read per-example results** —
   `get_many_benchmark_lineages_projects__project_id__evaluation_benchmarks__benchmark_id__executions__execution_id__lineages_get`.
   A lineage is one example's full path through the run; this is where a regression is diagnosed,
   not in the aggregate score.
7. **Correlate with traces** — ship OpenTelemetry spans in with
   `receive_otlp_traces_projects__project_id__traces_v2_post`
   (`POST /projects/{project_id}/traces_v2`) and read them back with
   `get_traces_projects__project_id__traces_v2_get`. The v1 trace/span/event endpoints
   (`create_trace_...`, `create_span_...`, `create_span_event_...`) are still available for
   manual construction.

## Rules

- **Compare executions, not benchmarks.** Re-running the same benchmark creates a new execution;
  keep both and diff their lineages.
- **Deletes cascade conceptually** — deleting a benchmark
  (`delete_benchmark_projects__project_id__evaluation_benchmarks__benchmark_id__delete`) removes
  the definition your executions refer to. Export lineages first if you need the history.
- **Project access is workspace-scoped** — use
  `get_project_userlist_workspaces__workspace_id__projects__project_id__userlist_get` and its
  PATCH sibling to manage who can see a project's evaluation data.
