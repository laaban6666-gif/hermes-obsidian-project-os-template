# PR Readiness Checklist

Use this runbook before opening, merging, or publishing a change.

## Change summary

- PR title draft: `<TYPE>: <SUMMARY>`
- Branch: `<BRANCH_NAME>`
- Related project note: `[[Sample Project]]`

## What changed

- `<SUMMARY_OF_USER_VISIBLE_CHANGE>`

## Checks / tests run

- [ ] Unit tests, if applicable
- [ ] Build, if applicable
- [ ] Lint or formatting check, if applicable
- [ ] Markdown/readability review
- [ ] Secret scan or manual secret review
- [ ] Manual smoke test, if applicable

Details:

```text
<COMMANDS_AND_RESULTS>
```

## Safety review

- [ ] No secrets or credentials.
- [ ] No personal data.
- [ ] No production-only configuration.
- [ ] No irreversible operation.
- [ ] No external publication, merge, deploy, billing, or form submission without human approval.

## Reviewer attention

Please check:

- `<AREA_THAT_NEEDS_EXTRA_REVIEW>`

## Gate result

- [ ] Ready for maintainer review.
- [ ] Blocked until the issues below are resolved.

Blocked by:

- `<BLOCKER_OR_NONE>`
