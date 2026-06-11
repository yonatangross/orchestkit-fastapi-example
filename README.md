# OrchestKit + FastAPI example configuration

A copy-paste starting point for using [OrchestKit](https://orchestkit.yonyon.ai) — the open-source Claude Code plugin (111 skills, 37 agents, 210 lifecycle hooks, MIT) — on a Python / FastAPI backend.

This repo is **configuration + workflow documentation**, not a demo app: drop `CLAUDE.md` and `.claude/` into your own FastAPI project and adapt.

## Setup

```bash
# 1. Install Claude Code (>= 2.1.170), then the plugin:
claude plugin install ork@orchestkit

# 2. Copy this repo's CLAUDE.md and .claude/ into your project root
# 3. Open Claude Code in the project — stack detection reads pyproject.toml
```

## What you get on a Python codebase

- **Skills that activate**: `python-backend` (asyncio TaskGroup, FastAPI DI, SQLAlchemy 2.0 async), `database-patterns` (Alembic, schema design), `api-design` (RFC 9457 errors, versioning), `testing-integration`, `testing-perf`, `security-patterns`
- **Agents in workflows**: `backend-system-architect`, `database-engineer`, `python-performance-engineer`, `security-auditor`, `test-generator`
- **Encoded defaults**: cursor pagination over offset, eager loading over N+1, no plaintext secrets — flagged by hooks, not just suggested

## The typed hook contract

Building Python tooling that consumes OrchestKit hook events?

```bash
pip install orchestkit-hook-contract
```

Typed I/O shapes, published via OIDC trusted publishing: https://pypi.org/project/orchestkit-hook-contract/

## Workflows worth trying first

```text
/ork:implement add a paginated /api/orders endpoint with cursor pagination and an Alembic migration
/ork:review-pr 123
```

See the [Python/FastAPI guide](https://orchestkit.yonyon.ai/docs/guides/orchestkit-with-python-fastapi).

## Links

- Docs: https://orchestkit.yonyon.ai · [Developer resources](https://orchestkit.yonyon.ai/developers)
- Source: https://github.com/yonatangross/orchestkit (MIT)
