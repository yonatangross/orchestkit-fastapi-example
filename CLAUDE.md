# CLAUDE.md — FastAPI project template (OrchestKit)

## Stack

- Python 3.12, FastAPI, SQLAlchemy 2.0 async, Alembic, PostgreSQL
- Tests: pytest (+ pytest-xdist) · Lint/type: ruff + ty

## Conventions

- Async-first: no sync DB calls in request paths
- Cursor pagination only (offset pagination is an anti-pattern here)
- Errors: RFC 9457 Problem Details · Inputs: Pydantic models, no raw dicts
- Migrations: one Alembic revision per PR, reversible

## Commands

```bash
uv run uvicorn app.main:app --reload
uv run pytest -n auto
uv run ruff check . && uv run ty check
uv run alembic upgrade head
```

## OrchestKit workflows used here

- Features: `/ork:implement <feature>` · Reviews: `/ork:review-pr <n>`
