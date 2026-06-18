# Hermes x Obsidian Project OS Template

A practical template for running small projects with **Hermes Agent + Obsidian + GitHub-style review habits**.

It is designed for solo founders, maintainers, and small teams who want an AI-assisted project operating system without leaking secrets or relying on private infrastructure.

## Why this exists

Many AI workflows are either too ad-hoc or too tied to one person's private notes. This template turns a real Hermes/Obsidian operating pattern into a reusable, public, secret-free starter kit.

## Who it is for

- Solo founders running several technical and business projects.
- Small teams using Obsidian as project memory.
- AI-agent users who need clear boundaries between implementation, review, and operations.
- OSS maintainers who want lightweight templates for project notes, PR readiness, routing, and scheduled jobs.

## What is included

```text
.
├── README.md
├── LICENSE
├── SECURITY.md
├── CONTRIBUTING.md
├── templates/
│   ├── project-note.md
│   ├── decision-log.md
│   ├── pr-readiness.md
│   ├── ai-team-routing.md
│   └── cron-job-spec.md
├── examples/
│   ├── profile-routing.md
│   ├── sample-project-note.md
│   ├── sample-pr-readiness.md
│   └── vault-structure.md
└── docs/
    └── publication-checklist.md
```

## Quick start

1. Copy the `templates/` files into your Obsidian vault.
2. Create one project note from `templates/project-note.md`.
3. Record one decision with `templates/decision-log.md`.
4. Before publishing code, fill `templates/pr-readiness.md`.
5. If you use Hermes Agent profiles, adapt `templates/ai-team-routing.md`.
6. If you use scheduled jobs, document them with `templates/cron-job-spec.md` before automating.

## Suggested Obsidian vault structure

```text
00_Command/       # Operating rules and AI team routing
10_Projects/      # Active project notes
20_Business/      # Customer, pricing, strategy notes
30_Templates/     # Reusable templates
40_Runbooks/      # Operational procedures
50_Decisions/     # Decision logs and architecture records
90_Archive/       # Completed or paused work
```

See `examples/vault-structure.md` for a more detailed sanitized example.

## Hermes Agent usage pattern

This template assumes three roles:

- **PM / coordinator**: breaks down work, sets boundaries, checks results.
- **Implementer**: writes code or documents in a local branch/workspace.
- **Reviewer / tester**: runs checks, summarizes failures, and blocks risky operations.

The template intentionally separates:

- local drafting from public publishing,
- reversible work from irreversible operations,
- public examples from private memory,
- placeholders from real account identifiers.

## Security rules

Never put these into an Obsidian vault or public repository:

- `.env` files,
- API keys,
- GitHub tokens,
- OpenAI organization IDs,
- private emails or phone numbers,
- customer data,
- production URLs that should not be public,
- screenshots containing account details.

Use placeholders such as `<PUBLIC_REPO_URL>` or `<MAINTAINER_NAME>` when preparing public drafts. Keep application-specific or account-specific form answers outside the public repository.

## Application-readiness status

Current status: **public initial version**.

Done:

- OSS theme selected.
- README and templates drafted.
- Sanitized examples prepared.
- Publication checklist prepared.
- Public repository published at `https://github.com/laaban6666-gif/hermes-obsidian-project-os-template`.

Privacy note:

- Grant/application drafts and form answers are intentionally kept outside this public repository.
- No personal information or account-specific identifiers are stored here.

## Roadmap

- Add a small import script or checklist generator after user approval.
- Add screenshots or diagrams after checking that they contain no private data.
- Publish a real public repository only after human review.
- Collect real usage feedback and improve templates.

## License

MIT. See `LICENSE`.
