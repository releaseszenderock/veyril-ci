# Veyril CI

Public GitHub Actions runner repository for the private `zenderock/veyril` source repository.

The authoritative workflow is `.github/workflows/gate.yml`. It is manually dispatched with an exact source branch/tag/SHA, checks out the private source with a fine-grained repository token, runs `scripts/ci/public-gate.sh`, and reports `veyril-ci/gate` back to that source commit.

## Required repository secrets

- `SOURCE_REPO_TOKEN` — fine-grained token scoped only to `zenderock/veyril` with `Contents: Read` and `Commit statuses: Read and write`.

The canonical workflow template and architecture notes live in the private source under `infra/github/veyril-ci/` and `docs/architecture/CI.md`.
