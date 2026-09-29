# Contributing Guide

> Historical reference only. The repository does not accept active development or support work.

## Retirement policy

The repository does not accept contributions, feature work, releases, or support requests. The source and history remain public for reference only.

## Final verification commands

```bash
mix test
mix credo --strict
mix dialyzer
```

These commands record the former development checks. They do not define an active support promise.

## Historical coding expectations

- Keep runtime contracts explicit and strict.
- Preserve compatibility of documented signal payloads.
- Prefer small private helpers over deeply nested control flow.
- Normalize and validate input close to module boundaries.

## Historical documentation expectations

Before retirement, behavior changes required these document updates:

- Update user guides in `docs/user` when external behavior changes.
- Update developer guides in `docs/developer` for internal architecture changes.
- Update `docs/architecture/contracts.md` for signal or validation contract changes.

## Historical pull request checklist

- Tests added/updated for changed behavior.
- Quality checks pass (`test`, `credo`, `dialyzer`).
- Docs updated where contracts or usage changed.
- Change is scoped to one coherent concern.
