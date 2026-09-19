# OpenContext

> A provider-neutral context runtime for long-running AI agents.

## Status

**Research & Validation**

OpenContext is currently a research and engineering project investigating context management, structured state, recoverability, provenance, and measurable evaluation for long-running AI agents.

The project follows a research-first approach:

```text
Research
   ↓
Baselines
   ↓
Prototype
   ↓
Benchmark
   ↓
Evaluation
   ↓
GO / NO-GO

The production framework will only be developed if the research provides sufficient evidence to justify it.
Research Question
Can a recoverability-aware context-management strategy reduce active context usage while preserving task-critical information better than simpler context-management approaches?

Initial Baselines
OpenContext will eventually be evaluated against:
1. Full conversation history
2. Sliding-window context
3. Plain summarization
4. OpenContext cascade
The strategies will be evaluated using comparable workloads, context budgets, and evaluation criteria.
Core Model
OpenContext separates:
Active Context
      +
Structured State
      +
Recoverable Artifacts
      +
Provenance
Technology
Core
- Python 3.11+
- uv
- Pydantic
- asyncio
- tiktoken
- pytest
- pytest-asyncio
- Ruff
- MyPy
- Typer
- structlog
Development Persistence
- SQLite
- Filesystem artifacts
Future Production Persistence
- PostgreSQL
- SQLAlchemy 2.x
- Alembic
- S3-compatible object storage
Providers
Initial:
- Mock provider
- Ollama
Later:
- OpenAI adapter
- Anthropic adapter
- Additional providers
Provider-specific functionality will remain behind provider interfaces.
Repository Structure
opencontext/
├── .ai/
│   └── rules/
├── .github/
│   └── workflows/
├── benchmarks/
├── docs/
├── src/
│   └── opencontext/
├── tests/
├── AGENTS.md
├── LICENSE
├── README.md
├── pyproject.toml
└── uv.lock
Development Philosophy
OpenContext prioritizes:
Evidence
   >
Architecture
   >
Features
Every major architectural component should answer:
What problem does this solve?

and:
How will we measure whether it works?

License
OpenContext is currently planned to use the Apache License 2.0.
See LICENSE for the complete license text.
Project Documentation
Project direction and governance are documented under:
docs/
Additional documentation will be added as the research and implementation progress.

Then save:

```text
Esc
:wq
Enter
The README content follows the project's stated mission, research-first sequence, research question, baseline strategies, technology stack, and repository principles.
