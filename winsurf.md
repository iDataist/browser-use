# Cascade Chat Conversation

  Note: _This is purely the output of the chat conversation and does not contain any raw data, codebase snippets, etc. used to generate the output._

### User Input

Walk me through the architecture of this repo

### Planner Response

I'll first create a small plan to scan and summarize the repo architecture. Then I'll list the top-level directory and search for common manifest files (pyproject, package.json, requirements, README) and typical source roots to identify the language and structure. Running these in parallel speeds things up.

*Updated todo list*

### Planner Response

I’m going to quickly scan the repository root and look for common manifest files and top-level directories to determine the language, tooling, and primary structure. I’ll run these lookups in parallel to speed things up.

*Listed directory [browser-use](file:///Users/hren/Downloads/browser-use) *

*Searched filesystem*

*Searched filesystem*

*Searched filesystem*

*Searched filesystem*

*Searched filesystem*

*Searched filesystem*

*Searched filesystem*

*Searched filesystem*

*Searched filesystem*

*Searched filesystem*

*Updated todo list*

### Planner Response

I’ll read the repo manifest and docs to determine language, dependencies, and entry points; and list key directories to map modules and examples/tests. Running these in parallel for speed.

*Viewed [pyproject.toml](file:///Users/hren/Downloads/browser-use/pyproject.toml) *

*Viewed [README.md](file:///Users/hren/Downloads/browser-use/README.md) *

*Listed directory [browser_use](file:///Users/hren/Downloads/browser-use/browser_use) *

*Listed directory [examples](file:///Users/hren/Downloads/browser-use/examples) *

*Listed directory [tests](file:///Users/hren/Downloads/browser-use/tests) *

*Viewed [Dockerfile](file:///Users/hren/Downloads/browser-use/Dockerfile) *

### Planner Response

I’ll inspect key packages and initializers to map exported API classes and responsibilities, and look at the CLI to confirm entry points. Running these reads in parallel to keep it fast.

*Listed directory [agent](file:///Users/hren/Downloads/browser-use/browser_use/agent) *

### Planner Response

I'll scan key modules to identify primary classes and responsibilities: exported API in [browser_use/__init__.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/__init__.py:0:0-0:0), major subpackages like [browser/](cci:7://file:///Users/hren/Downloads/browser-use/examples/browser:0:0-0:0), [llm/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm:0:0-0:0), [actor/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor:0:0-0:0), and check for `Agent`, `Browser`, `ChatBrowserUse` classes and CLI `main()` entrypoint. Running these in parallel.

*Viewed [__init__.py](file:///Users/hren/Downloads/browser-use/browser_use/__init__.py) *

### Planner Response

I'll list [browser_use/browser/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser:0:0-0:0) to understand browser automation internals (CDP/playwright) and key classes. I'll also peek at [browser_use/llm/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm:0:0-0:0) to see supported models and abstractions, and [browser_use/tools/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools:0:0-0:0) to summarize built-in tool integration.

*Listed directory [browser](file:///Users/hren/Downloads/browser-use/browser_use/browser) *

### Planner Response

I'll scan key subpackages to identify components and confirm responsibilities before summarizing the architecture. Running directory listings in parallel for speed.

*Searched filesystem*

*Updated todo list*

### Planner Response

I'll quickly list key subpackages under [browser_use/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use:0:0-0:0) to ensure the architecture summary names real modules and their responsibilities accurately. Running these directory reads in parallel.

*Listed directory [actor](file:///Users/hren/Downloads/browser-use/browser_use/actor) *

*Listed directory [dom](file:///Users/hren/Downloads/browser-use/browser_use/dom) *

*Listed directory [llm](file:///Users/hren/Downloads/browser-use/browser_use/llm) *

*Listed directory [browser_use](file:///Users/hren/Downloads/browser-use/browser_use/llm/browser_use) *

*Listed directory [tools](file:///Users/hren/Downloads/browser-use/browser_use/tools) *

*Listed directory [mcp](file:///Users/hren/Downloads/browser-use/browser_use/mcp) *

*Listed directory [controller](file:///Users/hren/Downloads/browser-use/browser_use/controller) *

*Listed directory [integrations](file:///Users/hren/Downloads/browser-use/browser_use/integrations) *

*Listed directory [filesystem](file:///Users/hren/Downloads/browser-use/browser_use/filesystem) *

*Listed directory [screenshots](file:///Users/hren/Downloads/browser-use/browser_use/screenshots) *

*Listed directory [sync](file:///Users/hren/Downloads/browser-use/browser_use/sync) *

*Listed directory [telemetry](file:///Users/hren/Downloads/browser-use/browser_use/telemetry) *

*Listed directory [tokens](file:///Users/hren/Downloads/browser-use/browser_use/tokens) *

*Updated todo list*

### Planner Response

# Architecture Walkthrough

## Top-level
- **[pyproject.toml](cci:7://file:///Users/hren/Downloads/browser-use/pyproject.toml:0:0-0:0)**: Python 3.11+ package. Entrypoints `browseruse` and [browser-use](cci:7://file:///Users/hren/Downloads/browser-use:0:0-0:0) point to `browser_use.cli:main`. Optional extras: `cli`, [aws](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/aws:0:0-0:0), `oci`, `video`, [examples](cci:7://file:///Users/hren/Downloads/browser-use/examples:0:0-0:0), `eval`, `all`.
- **[browser_use/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use:0:0-0:0)**: Main library code.
- **[examples/](cci:7://file:///Users/hren/Downloads/browser-use/examples:0:0-0:0)**: Many runnable examples across API, models, integrations, UI, and use-cases.
- **[tests/](cci:7://file:///Users/hren/Downloads/browser-use/tests:0:0-0:0)**: Test suites with pytest config in [pyproject.toml](cci:7://file:///Users/hren/Downloads/browser-use/pyproject.toml:0:0-0:0).
- **[Dockerfile](cci:7://file:///Users/hren/Downloads/browser-use/Dockerfile:0:0-0:0)**: Ships a runnable container with Chromium and the package installed; `ENTRYPOINT ["browser-use"]`.
- **[README.md](cci:7://file:///Users/hren/Downloads/browser-use/README.md:0:0-0:0)**: Quickstart and usage.

## Public API surface
- **[browser_use/__init__.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/__init__.py:0:0-0:0)**: Exposes lazy-imported symbols:
  - Agent layer: `Agent`, `SystemPrompt`, `ActionModel`, `ActionResult`, `AgentHistoryList` (from [browser_use/agent/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent:0:0-0:0)).
  - Browser: `BrowserSession` and alias `Browser` (from [browser_use/browser/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser:0:0-0:0)), `BrowserProfile`.
  - DOM: `DomService` (from [browser_use/dom/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0)).
  - Tools: `Tools`, `Controller` (from [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0)).
  - LLMs: `ChatOpenAI`, `ChatAnthropic`, `ChatGoogle`, `ChatGroq`, `ChatAzureOpenAI`, `ChatOCIRaw`, `ChatOllama`, `ChatBrowserUse`, and [models](cci:7://file:///Users/hren/Downloads/browser-use/examples/models:0:0-0:0) (from [browser_use/llm/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm:0:0-0:0)).
  - Initializes logging via [browser_use/logging_config.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/logging_config.py:0:0-0:0) and monkeypatches asyncio subprocess cleanup to reduce noisy shutdown errors.

## Core subsystems

- **Agent orchestration ([browser_use/agent/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent:0:0-0:0))**
  - **[service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0)**: The central orchestrator. Runs the task loop, prompts the LLM, interprets actions, coordinates with Browser and Tools, tracks history.
  - **[prompts.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/prompts.py:0:0-0:0), `system_prompt*.md`**: Prompt templates and system prompts.
  - **[views.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/views.py:0:0-0:0)**: Pydantic models for actions, results, and agent history.
  - **[gif.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/gif.py:0:0-0:0), [cloud_events.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/cloud_events.py:0:0-0:0)**: UX/telemetry helpers for visualizing and emitting events.

- **Browser/session control ([browser_use/browser/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser:0:0-0:0))**
  - Likely built on Chrome DevTools Protocol via `cdp-use` (see dependency `cdp-use>=1.4.0`). Chromium is installed via Playwright shortcut in README; container installs system `chromium`.
  - **[session.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/session.py:0:0-0:0)**: Main browser session class. Navigation, element interaction plumbing, event hooks.
  - **[events.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/events.py:0:0-0:0)**: Browser event modeling and pipelines.
  - **[profile.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/profile.py:0:0-0:0)**: Profiles, storage, and state handling for sessions.
  - **[watchdogs/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/watchdogs:0:0-0:0), [watchdog_base.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/watchdog_base.py:0:0-0:0)**: Safety and progress monitors to detect hangs or issues.
  - **[video_recorder.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/video_recorder.py:0:0-0:0)**, **[views.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/views.py:0:0-0:0)**: Recording/serialization for observability.

- **DOM capture and representation ([browser_use/dom/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom:0:0-0:0))**
  - **[service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0)**: DOM snapshotting, extraction, and transformations fed to LLM.
  - **[serializer/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/serializer:0:0-0:0)**, **[enhanced_snapshot.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/enhanced_snapshot.py:0:0-0:0)**, **[markdown_extractor.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/markdown_extractor.py:0:0-0:0)**: JS injection/serialization and text/structure extraction.

- **Low-level actions (“actor”) ([browser_use/actor/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor:0:0-0:0))**
  - **[page.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor/page.py:0:0-0:0), [element.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor/element.py:0:0-0:0), [mouse.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor/mouse.py:0:0-0:0)**: Imperative, low-level primitives for clicking, typing, scrolling, and element resolution. The Agent/Tools layer composes these.

- **LLM abstraction ([browser_use/llm/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm:0:0-0:0))**
  - **[base.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/base.py:0:0-0:0), [schema.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/schema.py:0:0-0:0), [messages.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/messages.py:0:0-0:0), [models.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/models.py:0:0-0:0)**: Common interfaces and message schemas.
  - Providers under subpackages: [openai/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/openai:0:0-0:0), [anthropic/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/anthropic:0:0-0:0), [google/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/google:0:0-0:0), [groq/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/groq:0:0-0:0), [ollama/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/ollama:0:0-0:0), [azure/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/azure:0:0-0:0), [openrouter/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/openrouter:0:0-0:0), [cerebras/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/cerebras:0:0-0:0), [deepseek/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/deepseek:0:0-0:0), [oci_raw/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/oci_raw:0:0-0:0).
  - **[browser_use/llm/browser_use/chat.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/browser_use/chat.py:0:0-0:0)**: First-party “ChatBrowserUse” model integrated with Browser Use Cloud.

- **Tooling and function calls ([browser_use/tools/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools:0:0-0:0))**
  - **[service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0)**: Tool registry, orchestration, and the `Controller` alias; provides function-call style extensions the Agent can invoke.

- **Config, observability, telemetry**
  - **[config.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/config.py:0:0-0:0)**: Centralized configuration (env-driven); [.env.example](cci:7://file:///Users/hren/Downloads/browser-use/.env.example:0:0-0:0) at repo root.
  - **[logging_config.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/logging_config.py:0:0-0:0), [observability.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/observability.py:0:0-0:0)**: Logging setup and tracing helpers.
  - **[telemetry/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/telemetry:0:0-0:0)**: Structured telemetry models and emitters.

- **Auth, sync, and integrations**
  - **[sync/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/sync:0:0-0:0)**: [auth.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/sync/auth.py:0:0-0:0), [service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0) for Browser Use Cloud auth/sync paths.
  - **[integrations/gmail/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/integrations/gmail:0:0-0:0)**: Example integration scaffold.
  - **[filesystem/file_system.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/filesystem/file_system.py:0:0-0:0)**, **[screenshots/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/screenshots/service.py:0:0-0:0)**: File IO helpers and screenshot capture.

- **MCP support ([browser_use/mcp/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp:0:0-0:0))**
  - **[server.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/server.py:0:0-0:0), [client.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/client.py:0:0-0:0), [controller.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/controller.py:0:0-0:0), [__main__.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/__main__.py:0:0-0:0), [manifest.json](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/manifest.json:0:0-0:0)**: Model Context Protocol server/client to expose browser-use as MCP tools for external LLM runtimes.

## CLI and runtime entrypoints
- **[browser_use/cli.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/cli.py:0:0-0:0)**: The CLI/TUI implementation (70k+ bytes). Uses `rich`, `click`, `textual` when `browser-use[cli]` is installed.
- Pyproject scripts:
  - `browseruse = "browser_use.cli:main"`
  - `browser-use = "browser_use.cli:main"`
- **Docker**: `ENTRYPOINT ["browser-use"]` runs the CLI inside the container.

## Typical control/data flow

```mermaid
flowchart LR
  U[Your code or CLI] --> A[Agent (agent/service.py)]
  A -->|prompts/actions| L[LLM (llm/*)]
  A -->|invoke tools| T[Tools (tools/service.py)]
  T --> ACT[Actor (actor/*)]
  ACT --> B[BrowserSession (browser/session.py)]
  B -->|navigate/interact| CH[Chromium via CDP]
  B --> D[DOM Service (dom/service.py)]
  D --> A
  A -->|history, telemetry| OBS[logging/telemetry]
```

- **Construction**: You create `Browser()` and an LLM (e.g., `ChatBrowserUse()`), then an `Agent(task, llm, browser)`; see [README.md](cci:7://file:///Users/hren/Downloads/browser-use/README.md:0:0-0:0) example and [browser_use/__init__.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/__init__.py:0:0-0:0) exports.
- **Loop**: `Agent.run()` gathers DOM state, prompts LLM, interprets actions, executes them through Tools/Actor against BrowserSession, and iterates until done.
- **State**: DOM snapshots and action results are modeled via [agent/views.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/views.py:0:0-0:0) and [dom/views.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/views.py:0:0-0:0).
- **Observability**: Logs, screenshots, videos/GIFs, and telemetry emitted during the run.

## Tests and examples
- **[tests/](cci:7://file:///Users/hren/Downloads/browser-use/tests:0:0-0:0)**: Pytest config in [pyproject.toml](cci:7://file:///Users/hren/Downloads/browser-use/pyproject.toml:0:0-0:0) with markers (`unit`, `integration`, `slow`) and sensible defaults (asyncio session scope, timeouts).
- **[examples/](cci:7://file:///Users/hren/Downloads/browser-use/examples:0:0-0:0)**: Organized by domain:
  - [models/](cci:7://file:///Users/hren/Downloads/browser-use/examples/models:0:0-0:0) for LLM backends.
  - [integrations/](cci:7://file:///Users/hren/Downloads/browser-use/examples/integrations:0:0-0:0) (e.g., Slack).
  - [use-cases/](cci:7://file:///Users/hren/Downloads/browser-use/examples/use-cases:0:0-0:0) (job apply, groceries, etc.).
  - [api/](cci:7://file:///Users/hren/Downloads/browser-use/examples/api:0:0-0:0), [ui/](cci:7://file:///Users/hren/Downloads/browser-use/examples/ui:0:0-0:0), [browser/](cci:7://file:///Users/hren/Downloads/browser-use/examples/browser:0:0-0:0), [cloud/](cci:7://file:///Users/hren/Downloads/browser-use/examples/cloud:0:0-0:0), etc., showing different entry patterns.

## Configuration and packaging
- **Python**: `>=3.11`, `hatchling` build backend.
- **Dependency management**: Uses `uv` in Docker for fast, reproducible envs. Optional extras enable CLI and integrations.
- **Env**: `.env` key `BROWSER_USE_API_KEY` for cloud features.

## Extensibility hotspots
- **New LLM provider**: Add a subpackage under [browser_use/llm/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm:0:0-0:0) and integrate with [models.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/models.py:0:0-0:0)/[schema.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/schema.py:0:0-0:0).
- **New tool/action**: Implement in [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0) and wire to the Agent; use low-level primitives in [browser_use/actor/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor:0:0-0:0).
- **Browser behaviors**: Extend [browser_use/browser/watchdogs/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/watchdogs:0:0-0:0) or augment [session.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/session.py:0:0-0:0) hooks.
- **DOM extraction**: Add serializers or text extractors under [browser_use/dom/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom:0:0-0:0).

# Recommended Actions
- **[Run a simple example]**: Start with [examples/simple.py](cci:7://file:///Users/hren/Downloads/browser-use/examples/simple.py:0:0-0:0) or `examples/getting_started/*` to see end-to-end flow.
- **[Inspect core]**: Skim [browser_use/agent/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/service.py:0:0-0:0) and [browser_use/browser/session.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/session.py:0:0-0:0) for orchestration and browser plumbing details.
- **[Try CLI]**: [browser-use](cci:7://file:///Users/hren/Downloads/browser-use:0:0-0:0) after installing extras `browser-use[cli]`.

# Status
- **Completed**: Repository architecture summarized with components, entrypoints, and control/data flow, citing key files and directories.

### User Input

Explain to me what the main use case is for this repo. What specific values does it deliver? What are similar projects? How does this differentiate from others?

*Updated todo list*

*Updated todo list*

### Planner Response

# Main Use Case

- **[LLM-powered web agent automation]**: This library lets an LLM act as an autonomous browser user to complete multi-step tasks on real websites (navigate, search, fill forms, click, upload, scrape). You compose an `Agent` with a `Browser` and an LLM (e.g., `ChatBrowserUse`) and call `agent.run()` to execute a task end-to-end.
  - Example API: [README.md](cci:7://file:///Users/hren/Downloads/browser-use/README.md:0:0-0:0) shows `Agent`, `Browser`, `ChatBrowserUse` usage.
  - Core orchestrator: [browser_use/agent/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/service.py:0:0-0:0)
  - Browser control: [browser_use/browser/session.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/session.py:0:0-0:0)
  - DOM extraction: [browser_use/dom/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0)
  - Tool calls: [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0)

The quickstart demos point to typical tasks:
- **Form filling** and application flows: [README.md](cci:7://file:///Users/hren/Downloads/browser-use/README.md:0:0-0:0), `examples/use-cases/apply_to_job.py`
- **Shopping**: `examples/use-cases/buy_groceries.py`
- **Personal assistant** workflows: `examples/use-cases/pcpartpicker.py`

# Specific Value Delivered

- **[Agent runtime out-of-the-box]**
  - High-level `Agent` loop that iterates between DOM snapshots, LLM reasoning, action execution, and history tracking.
  - Files: [browser_use/agent/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/service.py:0:0-0:0), [browser_use/agent/views.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/views.py:0:0-0:0), [browser_use/agent/prompts.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/prompts.py:0:0-0:0)

- **[Robust browser session with reliability features]**
  - Chromium-based control (CDP), profiles, event handling, and watchdogs to detect stalls/hangs.
  - Files: [browser_use/browser/session.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/session.py:0:0-0:0), [browser_use/browser/profile.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/profile.py:0:0-0:0), [browser_use/browser/events.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/events.py:0:0-0:0), [browser_use/browser/watchdogs/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/watchdogs:0:0-0:0)

- **[LLM-optimized DOM capture]**
  - Structured DOM snapshots and text extraction tuned for prompting.
  - Files: [browser_use/dom/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0), [browser_use/dom/serializer/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/serializer:0:0-0:0), [browser_use/dom/markdown_extractor.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/markdown_extractor.py:0:0-0:0)

- **[Extensible tool/function call layer]**
  - Tools the agent can invoke to perform concrete actions; `Controller` alias provided.
  - Files: [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0), [browser_use/tools/registry/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/registry:0:0-0:0)

- **[Multi-LLM support incl. first-party cloud model]**
  - Adapters for OpenAI, Anthropic, Google, Groq, Azure, Ollama, OCI Raw, OpenRouter, etc., plus `ChatBrowserUse`.
  - Files: `browser_use/llm/*`, [browser_use/llm/browser_use/chat.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/browser_use/chat.py:0:0-0:0)

- **[CLI/TUI and containerized runtime]**
  - [browser-use](cci:7://file:///Users/hren/Downloads/browser-use:0:0-0:0) CLI (also `browseruse`) and a Docker image that ships Python + Chromium + deps; zero-friction trials and demos.
  - Files: [browser_use/cli.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/cli.py:0:0-0:0), [pyproject.toml](cci:7://file:///Users/hren/Downloads/browser-use/pyproject.toml:0:0-0:0) `[project.scripts]`, [Dockerfile](cci:7://file:///Users/hren/Downloads/browser-use/Dockerfile:0:0-0:0)

- **[Observability and artifacts]**
  - Logging, telemetry, screenshots, GIF/video recording for debugging and reporting.
  - Files: [browser_use/logging_config.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/logging_config.py:0:0-0:0), [browser_use/telemetry/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/telemetry:0:0-0:0), [browser_use/screenshots/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/screenshots/service.py:0:0-0:0), [browser_use/agent/gif.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/gif.py:0:0-0:0), [browser_use/browser/video_recorder.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/video_recorder.py:0:0-0:0)

- **[MCP integration]**
  - Exposes Browser Use as an MCP server so external LLM runtimes can call it as a tool.
  - Files: [browser_use/mcp/server.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/server.py:0:0-0:0), [browser_use/mcp/manifest.json](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/manifest.json:0:0-0:0), [browser_use/mcp/__main__.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/__main__.py:0:0-0:0)

- **[Configuration and cloud hooks]**
  - Env-driven config and optional cloud sync/auth for “stealth” browsers and hosted runs.
  - Files: [.env.example](cci:7://file:///Users/hren/Downloads/browser-use/.env.example:0:0-0:0), [browser_use/config.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/config.py:0:0-0:0), [browser_use/sync/auth.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/sync/auth.py:0:0-0:0), [examples/cloud/](cci:7://file:///Users/hren/Downloads/browser-use/examples/cloud:0:0-0:0)

# Similar Projects and Categories

- **[Headless browser automation (non-LLM)]**
  - Playwright, Selenium. Great primitives, but you hand-write flows. Browser Use adds an LLM agent loop and DOM-to-prompt tooling.

- **[LLM frameworks with browser toolkits]**
  - LangChain + Playwright/Selenium toolkits, CrewAI + browser tools. These provide building blocks; you assemble agent loops and DOM handling. Browser Use is a batteries-included agent runtime specialized for the web.

- **[Research/benchmarks for web agents]**
  - WebArena, Mind2Web. Focused on evaluation/datasets and reference agents. This repo includes test assets for Mind2Web ([tests/mind2web_data/](cci:7://file:///Users/hren/Downloads/browser-use/tests/mind2web_data:0:0-0:0)) but ships a production-focused library, CLI, and Docker packaging.

# How This Differentiates

- **[Production-ready agent loop purpose-built for the web]**
  - A cohesive runtime with opinionated DOM capture, tool layer, and browser reliability features. You get a usable `Agent` on day one.
  - Files: [browser_use/agent/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/service.py:0:0-0:0), [browser_use/dom/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0), [browser_use/browser/watchdogs/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/watchdogs:0:0-0:0)

- **[End-to-end distribution and UX]**
  - Polished CLI/TUI ([browser_use/cli.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/cli.py:0:0-0:0)), Docker image with Chromium ([Dockerfile](cci:7://file:///Users/hren/Downloads/browser-use/Dockerfile:0:0-0:0)), extensive examples ([examples/](cci:7://file:///Users/hren/Downloads/browser-use/examples:0:0-0:0)), and lazy-import public API ([browser_use/__init__.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/__init__.py:0:0-0:0)) for fast starts.

- **[Deep observability]**
  - Built-in logs, telemetry, screenshots, and video/GIF capture to understand and debug agent behavior.
  - Files: [browser_use/telemetry/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/telemetry:0:0-0:0), [browser_use/agent/gif.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/gif.py:0:0-0:0), [browser_use/browser/video_recorder.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/video_recorder.py:0:0-0:0)

- **[Cloud model and MCP support]**
  - First-party `ChatBrowserUse` for cloud integration and an MCP server for ecosystem interoperability.
  - Files: [browser_use/llm/browser_use/chat.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/browser_use/chat.py:0:0-0:0), [browser_use/mcp/server.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/server.py:0:0-0:0)

- **[Multi-LLM, immediate portability]**
  - Swap providers without changing agent code. Adapters live under `browser_use/llm/*`.

# Recommended Actions

- **[Try a minimal script]**: [examples/simple.py](cci:7://file:///Users/hren/Downloads/browser-use/examples/simple.py:0:0-0:0) to see `Agent + Browser + ChatBrowserUse` end-to-end.
- **[Run the CLI]**: After installing extras (`browser-use[cli]`), run [browser-use](cci:7://file:///Users/hren/Downloads/browser-use:0:0-0:0) and explore the TUI.
- **[Skim core files]**: [browser_use/agent/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/service.py:0:0-0:0) and [browser_use/browser/session.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/session.py:0:0-0:0) to understand orchestration and browser control.
- **[Extend]**: Add a custom tool in [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0) and wire it into the agent.

# Status

- Explained the main use case, specific delivered value, comparable projects, and concrete differentiators with citations to key files and directories.

### User Input

Provide ideas of cool ways of using this repo

*Updated todo list*

*Updated todo list*

### Planner Response

# Ideas: Cool Ways To Use This Repo

## Growth, Ops, and Biz Automation
- **[Lead capture + outreach]**
  - Crawl lists, enrich on sites, fill CRM forms, and post summaries to Slack.
  - Use `Agent` + `Browser` ([browser_use/agent/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/service.py:0:0-0:0), [browser_use/browser/session.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/session.py:0:0-0:0)), Slack example (`examples/integrations/slack/`), and DOM extraction ([browser_use/dom/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0)).

- **[Competitor change detection]**
  - Nightly visit pages, snapshot DOM/text, diff, and alert.
  - Use DOM markdown ([browser_use/dom/markdown_extractor.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/markdown_extractor.py:0:0-0:0)), screenshots ([browser_use/screenshots/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/screenshots/service.py:0:0-0:0)), and run via Docker `ENTRYPOINT` ([Dockerfile](cci:7://file:///Users/hren/Downloads/browser-use/Dockerfile:0:0-0:0)).

- **[Price monitor + auto-cart]**
  - Track product prices and, on threshold, add to cart and notify.
  - Build from `examples/use-cases/buy_groceries.py` and watchdogs for reliability ([browser_use/browser/watchdogs/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/watchdogs:0:0-0:0)).

- **[Form filling at scale]**
  - Apply to portals (vendor onboarding, job apps), upload files, save receipts/GIFs.
  - Use `Agent` + file uploads in [actor/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor:0:0-0:0) ([browser_use/actor/page.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor/page.py:0:0-0:0), [browser_use/actor/element.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor/element.py:0:0-0:0)), plus [agent/gif.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/gif.py:0:0-0:0).

## Engineering & QA
- **[LLM-resilient E2E smoke tests]**
  - Replace brittle CSS/XPath with goal-oriented steps robust to UI tweaks.
  - Execute under pytest (config in `pyproject.toml [tool.pytest.ini_options]`) and capture vids ([browser_use/browser/video_recorder.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/video_recorder.py:0:0-0:0)).

- **[Visual runbooks for flaky flows]**
  - Record GIF/video of critical flows on release and archive with logs/telemetry.
  - Use [agent/gif.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/gif.py:0:0-0:0), [telemetry/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/telemetry:0:0-0:0) ([browser_use/telemetry/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/telemetry/service.py:0:0-0:0)), and [logging_config.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/logging_config.py:0:0-0:0).

- **[Backoffice data chores]**
  - Populate dashboards (admin portals, analytics), export CSVs, re-upload to another system.
  - Compose custom tools in [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0) and schedule with Docker.

## Support & CX
- **[Ticket triage across portals]**
  - Log in, fetch recent cases, summarize, escalate rules, post to Slack.
  - Use multi-LLM (`browser_use/llm/*`), Slack example (`examples/integrations/slack/`), and DOM snapshots.

- **[Warranty/returns submission]**
  - Recreate customer steps, fill forms, upload proofs, store artifacts (screenshots/GIF).
  - Use [filesystem/file_system.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/filesystem/file_system.py:0:0-0:0) for artifacts, [screenshots/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/screenshots/service.py:0:0-0:0).

## Research & Data Ops
- **[Multi-source research agent]**
  - Query multiple sites, collect facts, dedupe, export report PDF.
  - Use content extraction ([dom/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0)), PDF libs are already deps (`pypdf`, `reportlab` via [pyproject.toml](cci:7://file:///Users/hren/Downloads/browser-use/pyproject.toml:0:0-0:0)), and LLM routing in [llm/models.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/models.py:0:0-0:0).

- **[Invoice/PO copy-paste between portals]**
  - Parse portal A; fill portal B; reconcile totals; output audit bundle.
  - Use `AgentHistoryList` ([browser_use/agent/views.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/views.py:0:0-0:0)) + screenshots for auditability.

## Security & Compliance
- **[Policy attestations across vendors]**
  - Navigate vendor portals monthly, accept policies, capture screenshots and logs for evidence.
  - Bundle outputs via [screenshots/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/screenshots/service.py:0:0-0:0) and [agent/gif.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/gif.py:0:0-0:0).

- **[2FA/TOTP flows]**
  - Handle TOTP-based logins with `pyotp` support ([pyproject.toml](cci:7://file:///Users/hren/Downloads/browser-use/pyproject.toml:0:0-0:0)), then proceed with automations.
  - Implement in [actor/page.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor/page.py:0:0-0:0) with timing + watchdogs ([browser_use/browser/watchdogs/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/watchdogs:0:0-0:0)).

## DevEx & AI Integrations
- **[MCP: Let your LLM use the web]**
  - Expose Browser Use as an MCP tool to Claude/others to perform live web tasks from chat.
  - Use [browser_use/mcp/server.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/server.py:0:0-0:0), [browser_use/mcp/manifest.json](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/manifest.json:0:0-0:0), [__main__.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/__main__.py:0:0-0:0).

- **[Stealth cloud browsing]**
  - Use `ChatBrowserUse` and optional cloud profile for sites sensitive to automation.
  - See [browser_use/llm/browser_use/chat.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/browser_use/chat.py:0:0-0:0), [.env.example](cci:7://file:///Users/hren/Downloads/browser-use/.env.example:0:0-0:0), and [sync/auth.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/sync/auth.py:0:0-0:0).

- **[Domain-specific copilots]**
  - Build a thin CLI/UI around `Agent` for, e.g., “Procurement Copilot” or “Travel Booker.”
  - Start from [examples/ui/](cci:7://file:///Users/hren/Downloads/browser-use/examples/ui:0:0-0:0) and [examples/api/](cci:7://file:///Users/hren/Downloads/browser-use/examples/api:0:0-0:0), with runtime in [browser_use/cli.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/cli.py:0:0-0:0).

## Content & Social
- **[Editorial workflow automator]**
  - Log into CMS, create drafts from research, upload media, schedule posts, and confirm links.
  - Use `Actor` low-level inputs ([browser_use/actor/mouse.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor/mouse.py:0:0-0:0), [page.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/actor/page.py:0:0-0:0)) for media pickers and uploads.

- **[Social scheduling]**
  - Publish to web dashboards with multi-step wizards, capture links and analytics snapshots.
  - Store artifacts with [filesystem/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/filesystem:0:0-0:0) and send recaps via Slack integration.

# Quick Implementation Notes
- **[Core pattern]**: `Agent(task=..., llm=ChatBrowserUse()|ChatOpenAI()|..., browser=Browser())` then `await agent.run()` ([README.md](cci:7://file:///Users/hren/Downloads/browser-use/README.md:0:0-0:0), [browser_use/__init__.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/__init__.py:0:0-0:0) exports).
- **[Reliability]**: Watchdogs and events in [browser_use/browser/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser:0:0-0:0); prompt templates in [browser_use/agent/prompts.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/prompts.py:0:0-0:0).
- **[Extend tools]**: Add domain actions in [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0) and register in the `Controller`.
- **[Run modes]**:
  - Python with extras: `browser-use[cli]` (`pyproject.toml [project.optional-dependencies]`).
  - Docker: ships Chromium and CLI ([Dockerfile](cci:7://file:///Users/hren/Downloads/browser-use/Dockerfile:0:0-0:0), `ENTRYPOINT ["browser-use"]`).
  - MCP: expose to external LLMs ([browser_use/mcp/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp:0:0-0:0)).

# Recommended Actions
- **[Pick 2–3 ideas to prototype]**: I can scaffold a minimal script per idea in [examples/](cci:7://file:///Users/hren/Downloads/browser-use/examples:0:0-0:0) style.
- **[Choose LLM + runtime]**: Local (OpenAI/Anthropic/etc. under `browser_use/llm/*`) vs. Cloud (`ChatBrowserUse`).
- **[Add one custom tool]**: Implement a domain action in [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0) to see the extension pattern end-to-end.

# Status
- Delivered 15+ grounded use ideas with file/directory pointers, plus quick implementation guidance and next steps.

### User Input

RPA workflows are more predictable. If I know that I need to repeat a task, why would I choose this instead of using RPA?

*Updated todo list*

*Updated todo list*

### Planner Response

# When to Use This vs RPA

- **[Choose RPA]**
  - Stable, single UI with strict, repeatable selectors and few text-understanding needs.
  - Compliance requires deterministic, auditable scripts without LLM variability.
  - Example: Monthly invoice download from a single internal portal.

- **[Choose Browser Use]**
  - Multiple different sites or frequently changing UIs where selector brittleness is a maintenance burden.
  - Tasks that require text understanding, interpreting unstructured pages, or adapting to unfamiliar layouts.
  - You want to direct flows with natural language goals and swap LLMs as needed.

# Why Browser Use Can Win for Repeatable Tasks

- **[Lower maintenance under UI churn]**
  - LLM-driven action planning over DOM summaries reduces selector brittleness.
  - Files: [browser_use/dom/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0), [browser_use/dom/markdown_extractor.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/markdown_extractor.py:0:0-0:0), [browser_use/agent/prompts.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/prompts.py:0:0-0:0).

- **[Cross-site generalization]**
  - A single agent can handle many vendor sites without bespoke scripts per portal.
  - Core orchestrator: [browser_use/agent/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/service.py:0:0-0:0).

- **[Reasoning + Tool calls]**
  - Can decide next steps from content (“which plan to pick”, “is this the right form?”) and call tools/function-like actions.
  - Files: [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0) (tool registry/Controller), `browser_use/llm/*` (multi-LLM adapters).

- **[Reliability aids out-of-the-box]**
  - Watchdogs, events, and session management reduce hangs and enable recovery paths.
  - Files: [browser_use/browser/session.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/session.py:0:0-0:0), [browser_use/browser/watchdogs/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/watchdogs:0:0-0:0), [browser_use/browser/events.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/events.py:0:0-0:0), [browser_use/browser/profile.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/profile.py:0:0-0:0).

- **[Observability]**
  - Built-in logs, screenshots, GIF/video for audit and debugging.
  - Files: [browser_use/agent/gif.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/gif.py:0:0-0:0), [browser_use/browser/video_recorder.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/video_recorder.py:0:0-0:0), [browser_use/screenshots/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/screenshots/service.py:0:0-0:0), [browser_use/logging_config.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/logging_config.py:0:0-0:0), [browser_use/telemetry/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/telemetry:0:0-0:0).

- **[Distribution and integration]**
  - CLI/TUI ([browser_use/cli.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/cli.py:0:0-0:0)), Docker with Chromium ([Dockerfile](cci:7://file:///Users/hren/Downloads/browser-use/Dockerfile:0:0-0:0)), and MCP server ([browser_use/mcp/server.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/server.py:0:0-0:0)) to let external LLMs use the web.

# Trade-offs vs RPA

- **[Determinism]**: RPA scripts are step-exact; LLM agents are probabilistic. You’ll tune prompts, guards, and retries.
- **[Latency/Cost]**: Inference adds latency and token cost; cache/replay and selective prompting help.
- **[Policy/Compliance]**: Some orgs require fully scripted flows. Use artifacts (logs/screens) for audit, or constrain with custom tools.
- **[Site Constraints]**: Anti-automation/CAPTCHA vary. TOTP flows are supported ([pyproject.toml](cci:7://file:///Users/hren/Downloads/browser-use/pyproject.toml:0:0-0:0) includes `pyotp`), but hard blockers still require human-in-the-loop/alternatives.

# Hybrid Patterns That Work Well

- **[RPA for stable subflows, Browser Use for fuzzy steps]**
  - Orchestrate with RPA; call an `Agent` only for ambiguous pages (search, forms with inconsistent labels).
  - Implement domain tools in [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0) so the agent calls your deterministic functions.

- **[Guardrails + Checkers]**
  - Post-action verification tools (e.g., “confirm the cart has N items”) exposed as tools the LLM must call.
  - Use [agent/views.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/views.py:0:0-0:0) to log outcomes; capture artifacts for disputes.

- **[MCP integration]**
  - Use [browser_use/mcp/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp:0:0-0:0) to expose web actions as a tool to your existing AI platform; keep your current orchestrator.

# Quick Decision Checklist

- **Multiple sites or changing UIs?** Prefer Browser Use.
- **High text understanding/heuristics?** Prefer Browser Use.
- **Strict determinism/compliance?** Prefer RPA or hybrid with tool-guardrails.
- **Long-term maintenance cost matters?** Prefer Browser Use or hybrid.

# Concrete Differentiators (grounded in this repo)

- **LLM-first DOM pipeline**: [browser_use/dom/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/service.py:0:0-0:0), [browser_use/dom/markdown_extractor.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/dom/markdown_extractor.py:0:0-0:0)
- **Agent loop & prompts**: [browser_use/agent/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/service.py:0:0-0:0), [browser_use/agent/prompts.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/prompts.py:0:0-0:0)
- **Extensible tool layer**: [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0)
- **Reliability (watchdogs, events, profiles)**: [browser_use/browser/watchdogs/](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/watchdogs:0:0-0:0), [browser_use/browser/session.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/session.py:0:0-0:0), [browser_use/browser/events.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/events.py:0:0-0:0), [browser_use/browser/profile.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/profile.py:0:0-0:0)
- **Observability**: [browser_use/agent/gif.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/agent/gif.py:0:0-0:0), [browser_use/browser/video_recorder.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/browser/video_recorder.py:0:0-0:0), [browser_use/screenshots/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/screenshots/service.py:0:0-0:0), [browser_use/logging_config.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/logging_config.py:0:0-0:0)
- **Ecosystem integration**: CLI [browser_use/cli.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/cli.py:0:0-0:0), Docker [Dockerfile](cci:7://file:///Users/hren/Downloads/browser-use/Dockerfile:0:0-0:0), MCP [browser_use/mcp/server.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/mcp/server.py:0:0-0:0)
- **Multi-LLM support**: `browser_use/llm/*` including [browser_use/llm/browser_use/chat.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/llm/browser_use/chat.py:0:0-0:0)

# Recommended Actions

- **[Pilot a hybrid]**: Keep current RPA for stable steps; add an `Agent` for brittle pages. Start from [examples/simple.py](cci:7://file:///Users/hren/Downloads/browser-use/examples/simple.py:0:0-0:0) and add a custom tool in [browser_use/tools/service.py](cci:7://file:///Users/hren/Downloads/browser-use/browser_use/tools/service.py:0:0-0:0).
- **[Add guardrails]**: Implement “checker” tools and require the agent to verify after key steps.
- **[Harden reliability]**: Turn on screenshots/video and watchdogs for runs, then review artifacts upon failure.
- **[Benchmark]**: Compare maintenance overhead over 4–8 weeks of UI churn across 5–10 target sites.

# Status

- Compared RPA vs Browser Use, mapped trade-offs and differentiators to concrete files, and provided hybrid patterns and next steps.