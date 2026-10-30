## What & why
<!-- One or two sentences. Link the issue: Closes #123 -->

## App / area
<!-- people | attendance | payroll | recruit | visitor | crm | forms | erp | platform | bridge | website | infra -->

## Checklist
- [ ] Tests added/updated (unit, integration, or e2e as appropriate)
- [ ] Tenant-safe: every new table/query is scoped by `tenant_id`; RLS policy added
- [ ] No customer names or tenant IDs in core code (customer work goes to `opsdeck-extensions`)
- [ ] Gated correctly: entitlement check for paid features, release flag for unfinished work
- [ ] Migrations are expand/contract (safe to roll back one version)
- [ ] Config schema changed? Config migration included
- [ ] Docs / release note line added if user-visible

## Screenshots / notes for reviewer
