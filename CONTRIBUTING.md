# Contributing to OpsDeck

## Branches
- `main` is always deployable. Never push to it directly.
- Branch names: `<type>/<scope>-<short-desc>`, e.g. `feat/attendance-night-shift-rollover`. Allowed prefixes (enforced): `feat/ fix/ chore/ docs/ refactor/ perf/ test/ ci/ build/ sec/ hotfix/ release/`.
- No `dev`/`staging` branches: environments are deploy targets, not branches.
- Keep branches short-lived (under ~2 days). Use release flags to merge unfinished work safely.

## Commits (Conventional Commits)
`feat(attendance): night-shift wage day rollover`
`fix(payroll): rounding on PF wage ceiling`
Types: feat, fix, perf, refactor, test, docs, build, ci, chore, revert, sec, i18n, migration. **Scope is required** (module or area).

## Pull requests
- Squash merge only. PR title becomes the commit message, so use the same format.
- **Cubic** reviews every PR (advisory): fix each finding or reply with the reason. We don't use CodeRabbit.
- 1 human approval required, plus CODEOWNERS for core, db, kernel, payroll, migrations, infra and `.github`.
- CI must be green: lint, typecheck, unit, integration, tenant-isolation, module boundaries.

## Releases
- Merge to `main` → staging automatically. Production needs approval.
- Release tags `vYYYY.MM.DD.N` (e.g. `v2026.11.14.1`). Only org admins create them, and they are immutable. Monthly release notes come from PR titles.
- Rollout rings for features: edge (Infoloop's own tenant) → pilot → stable → lts.

## Golden rules
1. Modules talk through public interfaces/events only. Cross-app logic lives in `modules/bridges/`.
2. Plans are data: check `requireEntitlement(ctx, "module.payroll")`, never plan names.
3. No forks, no customer-specific `if`s in core. See ADR-0020 and `opsdeck/docs/architecture/extensibility.md`.

Full standard: [GitHub standards](https://github.com/infoloop-opsdeck/opsdeck-handbook/blob/main/engineering/github.md) (members only).
