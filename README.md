# NBA V3 Repo Skeleton

This is a repo-ready scaffold for the V3 redesign.

It is intentionally built to run next to an existing V2.x system so you can preserve prior work, log parallel runs, and compare V2.x vs V3 without deleting historical logic.

## Included

- additive SQLite migrations
- deployment-mode config (`OBSERVE`, `PAPER`, `LIVE`)
- odds snapshot ingestion that appends history rather than overwriting lines
- real-data fixture pack under `backdata/real_world/`
- tests that only use real-world fixture values from cited sources
- totals and sides scoring stubs that persist observation-mode outputs
- CLV and residual grading helpers
- training stubs for totals residual modeling and sides cover modeling
- implementation docs in `docs/`

## Important guardrails

- The tests avoid fake recommendations, fake historical outcomes, and fake odds.
- The real-world fixtures are factual source captures, not simulated betting histories.
- The scoring code is starter logic. It is safe for observation-mode logging, but not a claim of production betting edge.

## Quick start

```bash
python -m src.db.migrate --db-path data/nba_quant.db
pytest -q
```
