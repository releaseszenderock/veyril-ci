# Veyril CI

Public GitHub Actions runner repository for the private `zenderock/veyril` source repository.

The authoritative workflow is `.github/workflows/gate.yml`. It is manually dispatched with an exact source branch/tag/SHA, checks out the private source with a read-only deploy key, runs `scripts/ci/public-gate.sh`, and reports `veyril-ci/gate` back to that source commit.

## Required repository secrets

- `SOURCE_DEPLOY_KEY` — read-only deploy key private half for `zenderock/veyril`.
- `SOURCE_STATUS_TOKEN` — narrowly scoped credential permitted to write commit statuses on `zenderock/veyril`.

The canonical workflow template and architecture notes live in the private source under `infra/github/veyril-ci/` and `docs/architecture/CI.md`.
