# AI Team Routing Template

Use this to keep multiple AI profiles from mixing responsibilities.

## Profiles

### `<PROFILE_NAME_PM>`

Role: project manager / coordinator.

Allowed:

- task breakdown,
- scope control,
- local review,
- PR draft preparation.

Not allowed without human approval:

- merge,
- production deploy,
- external form submission,
- secrets or billing operations.

### `<PROFILE_NAME_IMPLEMENTER>`

Role: implementation.

Allowed:

- local code/doc edits,
- tests in a sandbox,
- draft branch preparation.

Not allowed:

- direct production edits,
- secret inspection,
- destructive commands.

### `<PROFILE_NAME_REVIEWER>`

Role: review and verification.

Allowed:

- lint/build/test,
- security review,
- PR readiness report.

## Handoff format

```text
Context:
Decision made:
Open questions:
Next responsible profile:
Safe boundaries:
References:
```
