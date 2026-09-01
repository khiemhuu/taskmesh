# Fork lineage and maintenance

TaskMesh is a fork of [Kaneo](https://github.com/usekaneo/kaneo), pinned at upstream commit `46539164c68669cec15b1528835c10ad0a66355e` (2026-09-01). Kaneo is MIT-licensed; its license and notices are retained in full (see `LICENSE`, `CONTRIBUTORS.svg`, and the git history, which preserves upstream attribution).

## Remotes

```
origin    → khiemhuu/taskmesh        (this product)
upstream  → usekaneo/kaneo           (Kaneo)
```

## Divergence policy

- **Internal identifiers stay upstream-compatible.** Package names (`@kaneo/*`), environment variables (`KANEO_API_URL`, `KANEO_CLIENT_URL`, …), the `X-Kaneo-Window-Id` header, and database table names are deliberately **not** renamed. Renaming them would turn every upstream change into a merge conflict for no product value. Rebranding applies to user-visible surfaces only.
- **Additive schema changes.** New tables and nullable columns only; never reshape upstream columns. This keeps upstream migrations applicable during rebases.
- **Keep the patch series small.** Prefer new feature folders (`apps/api/src/<feature>/`, `apps/web/src/…`) over edits inside upstream files. When an upstream file must change, keep the diff minimal and localized.

## Rebase procedure (monthly)

1. `git fetch upstream`
2. `git checkout main && git checkout -b rebase/upstream-<date>`
3. `git rebase upstream/main` — expect conflicts mainly in `apps/api/src/index.ts` (router mount + `AppType` union) and `apps/api/src/database/schema.ts`.
4. `corepack pnpm typecheck && corepack pnpm test && corepack pnpm lint`
5. Open a PR; require the full CI (including the Postgres integration job) green before merging.
6. Never force-push `main` casually: the rebase PR merge is a regular merge; repo history cleanliness is secondary to reviewability.

## CI on this repository

Only `ci.yml` (lint, i18n, typecheck, unit, build, integration with Postgres, docker smoke build), `helm-chart.yml` (chart lint on chart changes), and the manual `release.yml` chain are active. Upstream publishing/deploy/notification workflows were removed at fork time because they target upstream registries and webhooks.
