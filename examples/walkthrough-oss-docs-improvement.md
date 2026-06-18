# Walkthrough: small OSS docs improvement

This walkthrough shows one end-to-end path through the Project OS templates using a generic README improvement for a public OSS repository.

The example is intentionally public-safe:

- no secrets,
- no personal data,
- no private account details,
- no customer information,
- no production-only configuration,
- publication and merge stay behind human approval.

## Scenario

A maintainer notices that new users do not immediately understand what the repository is for or how to try it quickly. The change is small: improve the README opening and add a short quick-start section.

## Step 1 — Create a Project Note

Create `10_Projects/Improve README Onboarding.md` from `30_Templates/project-note.md`.

```markdown
# Improve README Onboarding

## Summary

- Project name: `Improve README Onboarding`
- Owner: `<MAINTAINER_OR_PROFILE>`
- Status: `active`
- Repo/local path: `<PUBLIC_REPO_URL_OR_LOCAL_PATH>`
- Last updated: `<YYYY-MM-DD>`

## Plain-language goal

Make the README easier for a first-time visitor to understand and try in under 3 minutes.

## Current priority

- Priority: `2`
- Why now: First impressions determine whether contributors and users can adopt the project.

## Scope

### In scope

- Clarify the opening one-liner.
- Add or improve quick-start steps.
- Link to existing examples or templates.
- Keep all examples generic and public-safe.

### Out of scope

- Changing product direction.
- Adding new dependencies.
- Publishing private roadmap details.
- Mentioning private accounts, credentials, or non-public operations.

## Safety boundaries

Actions allowed without extra approval:

- Edit Markdown files locally.
- Propose wording changes.
- Run Markdown and link checks where available.

Actions requiring human approval:

- merge,
- external publication,
- release notes,
- anything involving private data or account identifiers.

## Next actions

1. Draft README changes.
2. Review for clarity and public-safety.
3. Prepare PR readiness notes and handoff.
```

## Step 2 — Open an AI Team Room

Create or update `00_Command/AI Team Room.md` from `30_Templates/ai-team-room.md`.

```markdown
# AI Team Room — Improve README Onboarding

## Room metadata

- Project: `Improve README Onboarding`
- Task: `README first-run clarity`
- Date: `<YYYY-MM-DD>`
- Branch/workspace: `<BRANCH_NAME>`
- Related project note: `10_Projects/Improve README Onboarding.md`
- Related PR/readiness note: `40_Runbooks/PR Readiness - README Onboarding.md`

## Roles

- **Coordinator:** defines the docs outcome and safety boundaries.
- **Implementer:** edits Markdown locally.
- **Reviewer:** checks readability, links, and public-safety.
- **Human:** approves PR creation, merge, publication, or release notes.

## Gates

- [x] **Gate 1 — Scope:** README onboarding only; no private details.
- [ ] **Gate 2 — Implementation:** pending local edit summary.
- [ ] **Gate 3 — Verification:** pending checks.
- [ ] **Gate 4 — Safety:** pending public-safe review.
- [ ] **Gate 5 — Human approval:** required before merge or publication.

## Chat log

### `<YYYY-MM-DD HH:MM>` — Coordinator

**Intent:** Improve first-time README adoption for a public OSS project.

**Approved scope:**

- `README.md`
- existing example/template links

**Out of scope:**

- credentials, account details, private strategy, release publication, or dependency changes

**Next role:** Implementer

**Gate status:** Gate 1 is `passed` because the goal, files, and exclusions are explicit.

---

### `<YYYY-MM-DD HH:MM>` — Implementer

**Actions taken:**

- Rewrote the opening sentence to name the audience and outcome.
- Added a short quick-start path for new users.
- Linked to the walkthrough and existing templates.

**Files touched:**

- `README.md`

**Assumptions:**

- The project remains a lightweight public OSS template.
- A docs-only PR is appropriate for this change.

**Next role:** Reviewer

**Gate status:** Gate 2 is `passed` because the local Markdown edits are complete.

---

### `<YYYY-MM-DD HH:MM>` — Reviewer

**Checks run:**

```text
git diff --check
manual README readability review
manual public-safety review
```

**Review findings:**

- Quick-start steps are actionable for a new user.
- Links point to repository-local files.
- No secrets, private account details, or personal data are included.

**Safety review:**

- [x] No secrets or credentials.
- [x] No personal data.
- [x] No production-only configuration.
- [x] No irreversible operation.
- [x] Merge/publication is waiting for human approval.

**Next role:** Coordinator

**Gate status:** Gate 3 is `passed` and Gate 4 is `passed` because the change is docs-only and public-safe.
```

## Step 3 — Capture the Decision Log

Create `50_Decisions/README Onboarding Decision.md` from `30_Templates/decision-log.md`.

```markdown
# Decision Log — README onboarding path

## Decision

Use a short README onboarding path instead of a long process overview.

## Date

`<YYYY-MM-DD>`

## Status

`accepted`

## Context

A first-time visitor needs to understand who the project is for, what they get, and what to do next without reading every template first.

## Options considered

### Option A — Keep README mostly conceptual

- Pros: Shorter maintenance burden.
- Cons: Less useful for adoption; new users may not know what to copy.

### Option B — Add a concise onboarding path

- Pros: Shows what to do immediately; supports GitHub ZIP download and existing vault usage.
- Cons: Slightly longer README.

### Option C — Move onboarding into a separate docs site

- Pros: More room for tutorials.
- Cons: Too heavy for a lightweight starter kit.

## Chosen option

`Option B — Add a concise onboarding path`

## Reasoning

A concise path helps adoption while keeping the repository simple and Markdown-only.

## Risks

- README could become too long.
- Steps could drift from the actual file tree.

## Rollback / revisit trigger

Revisit if users report that the README is too long or the onboarding steps no longer match the repository structure.

## Links

- Project note: `10_Projects/Improve README Onboarding.md`
- PR / issue: `<PR_OR_ISSUE_LINK>`
```

## Step 4 — Prepare PR Readiness

Create `40_Runbooks/PR Readiness - README Onboarding.md` from `30_Templates/pr-readiness.md`.

```markdown
# PR Readiness — README Onboarding

## Change summary

- PR title draft: `docs: improve README onboarding`
- Branch: `<BRANCH_NAME>`
- Related project note: `10_Projects/Improve README Onboarding.md`

## What changed

- Clarified the README opening.
- Added a practical quick-start path.
- Linked supporting examples/templates.

## How it was implemented

- Markdown-only edits.
- No dependencies added.
- No private or account-specific content added.

## Tests / checks run

- [ ] Unit tests
- [ ] Build
- [ ] Lint
- [x] Markdown/readability review
- [x] Secret scan
- [x] Manual smoke test

Details:

```text
git diff --check
manual link/readability review
manual public-safety review
```

## Impact area

- Files: `README.md`, examples as needed
- Features: onboarding documentation
- Users affected: first-time users and contributors

## Safety review

- [x] No secrets.
- [x] No personal data.
- [x] No production-only configuration.
- [x] No irreversible operation.
- [x] External publication or deployment requires human approval.

## Reviewer attention

Please check:

- Is the first paragraph clear to a new visitor?
- Can a user start from a ZIP download or existing Obsidian vault?
- Do the file links match the repository tree?

## Decision notes

Chose a concise README path instead of a separate docs site to keep adoption lightweight.
```

## Step 5 — PR handoff

Use this final handoff in the AI Team Room or PR description.

```text
Result:
Improved README onboarding for a small public OSS docs change.

Evidence:
- Project note defines scope and safety boundaries.
- AI Team Room records role handoffs and gates.
- Decision log explains why concise onboarding was chosen.
- PR readiness note lists checks and reviewer focus.

Remaining risks:
- Links may need updates if files move.
- Screenshots or diagrams should be reviewed separately before publication.

Next action:
Human maintainer reviews the diff, confirms the checklist, and decides whether to open or merge the PR.

Owner:
<MAINTAINER_OR_PROFILE>
```

## Reusable checklist

- [ ] Project note exists and names goal, scope, out-of-scope work, and approval boundaries.
- [ ] AI Team Room records coordinator, implementer, reviewer, and human approval gates.
- [ ] Decision log captures the main trade-off.
- [ ] PR readiness note lists files changed, checks run, and reviewer attention.
- [ ] Public-safety review confirms no secrets, personal data, or private account details.
- [ ] Human approval is required before merge, publication, deploy, or release.
