# Sample PR Readiness: Add Project OS Templates

## Change summary

- PR title draft: `feat: add Hermes Obsidian Project OS templates`
- Branch: `<BRANCH_NAME>`
- Related project note: `examples/sample-project-note.md`

## What changed

- Added reusable project, decision, PR, routing, and cron templates.
- Added sanitized examples.
- Added documentation for publication and application readiness.

## How it was implemented

- Markdown files only.
- No external services used.
- No credentials or personal data included.

## Tests / checks run

- [x] Markdown files exist.
- [x] Required docs exist.
- [x] Secret-like patterns checked locally.
- [ ] Human review before publishing.

Details:

```text
Run local file-list and secret-pattern checks before publishing.
```

## Impact area

- Files: README, templates, examples, docs.
- Features: documentation and process templates.
- Users affected: future users copying this template.

## Safety review

- [x] No secrets.
- [x] No personal data.
- [x] No production-only configuration.
- [x] No irreversible operation.
- [x] External publication requires human approval.

## Reviewer attention

Please check:

- Are examples concrete enough without exposing private details?
- Is the OpenAI application draft honest about unknowns?
- Is the project valuable beyond any private planning or promotion goal?

## Decision notes

The first version is documentation-first because it is useful quickly and safe to publish after review. A small helper script can be added later if users need automation.
