# Jerson Montes

Software engineer. I build applications, scientific software, machine-learning tooling and database
systems.

Most of my professional work lives in private codebases. The repositories below are small, self-contained
projects, one per area, each written to show a single thing done carefully: a design whose decisions are
written down, limits that are stated, and tests that check every claim the README makes.

| Area | Repository | What it shows |
|---|---|---|
| Databases | [lsm-kv](https://github.com/jersoncoder/lsm-kv) | An embedded LSM-tree key-value store in pure Python, with a write-ahead log, checksummed SSTables, snapshots and compaction. Crash tests replay a recorded workload, crash it before every file operation and at every byte of the last log records, and check what recovery keeps. A [mutation script](https://github.com/jersoncoder/lsm-kv/blob/main/scripts/mutations.py) removes each fsync and checksum check in turn and confirms the tests notice. |
| Applications | [feature-flag-service](https://github.com/jersoncoder/feature-flag-service) | A self-hostable feature-flag service built on FastAPI and SQLite. It has deterministic percentage rollouts, optimistic concurrency with ETags (412 on a stale write) and an audit log. A Python SDK evaluates flags locally, and [a test](https://github.com/jersoncoder/feature-flag-service/blob/main/tests/test_agreement.py) checks that it agrees with the server on thousands of random contexts. |
| Science in software | [verified-diffusion](https://github.com/jersoncoder/verified-diffusion) | A finite-volume heat-conduction solver in 1D and 2D, verified with manufactured solutions, analytic solutions, grid-convergence studies and an energy balance at round-off. The [verification report](https://github.com/jersoncoder/verified-diffusion/blob/main/docs/verification.md) shows the measured orders of accuracy. |
| Machine learning | [evalstats](https://github.com/jersoncoder/evalstats) | Comparison of machine-learning models with their uncertainty: bootstrap confidence intervals, paired tests (McNemar, DeLong, permutation), calibration and slice analysis. Metrics are cross-checked against scikit-learn, and [simulations](https://github.com/jersoncoder/evalstats/blob/main/tests/test_simulation.py) check coverage and type-I error. |

All four share the same setup: Python 3.11 to 3.13, `ruff`, `mypy --strict` and `pytest` in CI, and MIT
licenses.

[![lsm-kv](https://github.com/jersoncoder/lsm-kv/actions/workflows/ci.yml/badge.svg)](https://github.com/jersoncoder/lsm-kv/actions/workflows/ci.yml)
[![feature-flag-service](https://github.com/jersoncoder/feature-flag-service/actions/workflows/ci.yml/badge.svg)](https://github.com/jersoncoder/feature-flag-service/actions/workflows/ci.yml)
[![verified-diffusion](https://github.com/jersoncoder/verified-diffusion/actions/workflows/ci.yml/badge.svg)](https://github.com/jersoncoder/verified-diffusion/actions/workflows/ci.yml)
[![evalstats](https://github.com/jersoncoder/evalstats/actions/workflows/ci.yml/badge.svg)](https://github.com/jersoncoder/evalstats/actions/workflows/ci.yml)
