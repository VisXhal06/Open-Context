# OpenContext

A provider-neutral context runtime for long-running AI agents.

OpenContext investigates whether structured state, recoverability, and provenance can reduce active context usage without losing task-critical information.

**Status:** research and validation. A production framework will be built only if evaluation results justify it.

## Research question

Can a recoverability-aware context-management strategy reduce active context usage while preserving task-critical information better than simpler approaches?

## Approach

Work proceeds in a fixed sequence. Stages are not skipped without an explicit project decision.

```text
Research → Baselines → Prototype → Benchmark → Evaluation → GO / NO-GO
```

Evidence comes before architecture, and architecture comes before features. Each major component should answer two questions: what problem it solves, and how success will be measured.

## Evaluation

Strategies will be compared on the same workloads, context budgets, and criteria:

1. Full conversation history
2. Sliding-window context
3. Plain summarization
4. OpenContext cascade

## Core model

OpenContext separates four concerns:

| Layer | Role |
| --- | --- |
| Active context | What the model sees on a given turn |
| Structured state | Goals, decisions, constraints, and tasks kept in an explicit form |
| Recoverable artifacts | Information that may leave the active window but must remain retrievable |
| Provenance | How derived state was produced, so it can be audited and reconstructed |

The domain layer stays independent of databases, cloud providers, LLM vendors, and agent frameworks.

## Current stack

Day 1 is the engineering foundation, not production infrastructure.

| Area | Choice |
| --- | --- |
| Language | Python 3.11+ |
| Package and environment | [uv](https://docs.astral.sh/uv/) |
| Models and validation | Pydantic |
| Tests | pytest, pytest-asyncio |
| Quality | Ruff, MyPy |
| License | Apache License 2.0 |

Planned later, only when a later stage requires them: SQLite and filesystem artifacts for development persistence; PostgreSQL, SQLAlchemy, Alembic, and object storage for production persistence; mock and Ollama first, then other provider adapters behind the same interfaces.

## Development

```bash
uv python install 3.11
uv sync --dev
uv run pytest
uv run ruff check .
uv run mypy
```

Copy `.env.example` to `.env` for local configuration. Do not put real secrets in source, tests, or fixtures.

Contributor guidance lives in [`AGENTS.md`](AGENTS.md).

## Repository

```text
.
├── .ai/rules/          AI engineering rules
├── .github/workflows/  CI
├── src/opencontext/    Package source
├── tests/
├── AGENTS.md
├── LICENSE
├── README.md
├── pyproject.toml
└── uv.lock
```

## License

Licensed under the [Apache License 2.0](LICENSE).
