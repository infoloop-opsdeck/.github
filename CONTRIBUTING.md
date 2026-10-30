# Contributing to OpsDeck

## Branches
- `main` is always deployable. Never push to it directly.
- Branch names: `feat/OPS-123-short-name`, `fix/OPS-456-...`, `chore/...`, `docs/...`
- Keep branches short-lived (under ~2 days). Use release flags to merge unfinished work safely.

## Commits (Conventional Commits)
`feat(attendance): night-shift wage day rollover`
`fix(payroll): rounding on PF wage ceiling`
Types: feat, fix, perf, refactor, test, docs, chore, ci. Scope = app/module name.

## Pull requests
- Squash merge only. PR title becomes the commit message, so use the same format.
- 1 approval required; CODEOWNERS approval for `platform/`, migrations and CI.
- CI must be green: lint, typecheck, unit, integration, tenant-isolation, module boundaries.

## Releases
- Merge to `main` → staging automatically. Production needs approval.
- CalVer tags: `v2026.11.0`, `v2026.11.1` (hotfix). Monthly release notes from PR titles.
- Rollout rings: Infoloop internal tenant → early-access tenants → everyone.

## Golden rules
1. Modules talk through public interfaces/events only. Cross-app logic lives in `bridges/`.
2. Plans are data: check `tenant.has("app.payroll")`, never plan names.
3. No forks, no customer-specific `if`s in core. See `opsdeck-handbook/architecture/extensibility.md`.
