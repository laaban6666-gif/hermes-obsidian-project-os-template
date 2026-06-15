# Codex for OSS / ChatGPT Pro Acquisition Brief

Date: 2026-06-12T02:16:48+09:00
Status: public repository published; application not submitted.

## Objective

Prepare a legitimate, non-misleading path to use `Hermes x Obsidian Project OS Template` as an OSS candidate for a Codex for OSS / ChatGPT Pro maintainer-support application.

This document is intentionally safe to keep local or publish after review: it contains no personal information, no account identifiers, no tokens, and no claimed eligibility.

## Verified public facts from this run

### Official OpenAI pages

Requested from this VPS with a browser-like user agent:

- `https://openai.com/form/codex-for-oss/` → HTTP 403
- `https://openai.com/index/introducing-codex/` → HTTP 403
- `https://help.openai.com/en/articles/11369540-codex-in-chatgpt` → HTTP 403

Interpretation: the official form and related pages could not be verified from this environment. This is an access limitation, not proof that the pages are gone or closed.

### OpenAI Codex public repository

GitHub API request to `https://api.github.com/repos/openai/codex` returned HTTP 200.

Verified snapshot:

- Repository: `openai/codex`
- URL: `https://github.com/openai/codex`
- Description: `Lightweight coding agent that runs in your terminal`
- License: Apache-2.0
- Default branch: `main`
- Created: 2025-04-13T05:37:54Z
- Updated: 2026-06-11T17:07:53Z
- Pushed: 2026-06-11T17:14:45Z
- Stars at verification time: 90,447
- Forks at verification time: 13,316
- Open issues at verification time: 6,705

### Codex README facts verified through GitHub API

The public README states:

- Codex CLI is a coding agent from OpenAI that runs locally on your computer.
- Install options include `curl -fsSL https://chatgpt.com/codex/install.sh | sh`, npm package `@openai/codex`, and Homebrew cask `codex`.
- Codex can be used with a ChatGPT plan by signing in with ChatGPT.
- The README recommends signing into a ChatGPT account to use Codex as part of Plus, Pro, Business, Edu, or Enterprise plans.
- API-key usage is possible but requires additional setup.
- The repository is licensed under Apache-2.0.

## What remains unverified

Because official OpenAI pages returned HTTP 403 here, these points must be checked by the user in a normal logged-in browser session before any application:

- Whether the Codex for OSS form is currently open.
- Exact eligibility criteria.
- Exact fields in the form.
- Whether ChatGPT Pro is granted automatically, by review, or under limited conditions.
- Whether there are geographic, account, billing, or organization restrictions.
- Whether the project must already have adoption metrics.

## Candidate positioning

Recommended positioning for the local project:

> A documentation-first OSS starter kit for running AI-assisted projects with Obsidian memory, Hermes-style role separation, PR readiness checklists, decision logs, and safe automation boundaries.

Why this is a reasonable candidate:

- It is useful independent of any OpenAI support outcome.
- It directly helps AI-agent users and maintainers avoid secret leakage, hidden assumptions, and unsafe automation.
- It is small enough to publish quickly, but concrete enough to improve through real user feedback.
- It uses sanitized templates/examples instead of private operational data.

What not to claim:

- Do not claim acceptance, eligibility, sponsorship, partnership, or guaranteed ChatGPT Pro access.
- Do not invent stars, downloads, users, or public impact.
- Do not imply OpenAI endorsed this project.

## Acquisition funnel

### Phase 0 — Local readiness, no external writes

Completed.

Artifacts already present:

- README
- MIT license
- SECURITY
- CONTRIBUTING
- project/decision/PR-readiness/AI-routing/cron templates
- sanitized examples
- application draft
- publication checklist
- research notes
- this acquisition brief

Gate to leave Phase 0:

- User reviews local files.
- Secret scan passes.
- User approves public repository name and publication scope.

### Phase 1 — Public repository creation

Completed after user approval.

Actions:

- Create a public GitHub repository.
- Push reviewed files only.
- Confirm public rendering.
- Create first issue/roadmap if desired.

Data to record after publication:

- Public repository URL.
- Stars/forks at submission time.
- Whether there are any real users/downloads; if none, say none/new project.

Published repository:

- `https://github.com/laaban6666-gif/hermes-obsidian-project-os-template`

Publication commit:

- `3e980b7f555b2fa10f8719bec21cf2178a5763db`

### Phase 2 — Application preparation

Human/browser step required.

Actions:

- Open official OpenAI form in normal browser.
- Confirm current fields and terms.
- Fill only real values.
- Keep OpenAI organization/account identifiers out of the repository.
- Submit only with explicit final consent.

### Phase 3 — If accepted

Do not automate without user approval.

Actions:

- Record terms and expiration date in private notes, not public repo.
- Use Codex/Pro for maintainer work: issue triage, PR review, template improvements, docs QA.
- Keep usage tied to real OSS maintenance.

### Phase 4 — If rejected or ineligible

Continue project anyway.

Actions:

- Publish/maintain based on user value, not grant outcome.
- Gather feedback.
- Improve templates and examples.
- Re-apply only if criteria and real adoption improve.

## Submission-safe evidence pack template

Fill after public repository exists:

```text
Project name: Hermes x Obsidian Project OS Template
Public repo URL: https://github.com/laaban6666-gif/hermes-obsidian-project-os-template
License: MIT
One-line description: <FINAL_PUBLIC_DESCRIPTION>
Maintainer: <USER_TO_ENTER_IN_FORM_ONLY>
Stars at submission: <REAL_STARS_FROM_GITHUB_AT_SUBMISSION_TIME>
Forks at submission: <REAL_FORKS_FROM_GITHUB_AT_SUBMISSION_TIME>
Downloads/users: New project; no known external users yet unless real evidence exists at submission time.
Why it matters: <CONCISE_IMPACT_STATEMENT>
How Codex/ChatGPT Pro helps: <MAINTENANCE_USE_CASES>
Security posture: No secrets, sanitized examples, SECURITY.md, contribution rules.
Limitations: New project; adoption claims limited to real evidence.
```

## Next safe step

Before any OpenAI form submission, run the local checks in `docs/publication-checklist.md`, then have the user open the official form in a normal browser and review `docs/application-draft.md` plus this brief.
