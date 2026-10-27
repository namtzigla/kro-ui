# TCN deployment branch: `tcn-deploy`

This branch is what TCN builds and deploys (the kro-ui on the TCN Cloud
Control Plane management clusters). It is `upstream/main` plus the changes
listed below, each carried as its own branch and offered upstream. The branch
is rebuilt from `upstream/main` when upstream moves; the list is the record
for the eventual upstream merge request(s).

| # | Branch | Upstream PR | Status | What |
|---|--------|-------------|--------|------|
| 1 | `fix/cluster-scoped-instance-detail` | [pnz1990/kro-ui#840](https://github.com/pnz1990/kro-ui/pull/840) | open | `GetInstance`, `GetInstanceEvents`, `GetInstanceChildren` treat the `_` namespace sentinel as cluster-scoped (404 on cluster-scoped instance detail) |

## Rules

- Every change lives on its own `fix/...` or `feat/...` branch off `upstream/main`, with a DCO sign-off and nothing else in the trailers, and is merged into `tcn-deploy` with `--no-ff`.
- A change merged upstream is dropped from this list at the next rebuild of `tcn-deploy` on `upstream/main`.
- Rebuild: `git checkout -B tcn-deploy upstream/main`, then `git merge --no-ff` each open branch in table order, then force-push.
