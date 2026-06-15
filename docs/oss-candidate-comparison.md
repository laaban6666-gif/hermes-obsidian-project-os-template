# OSS Candidate Comparison

Goal: choose one honest, useful OSS candidate to prepare before any OpenAI Codex for OSS / maintainer support application.

## Candidate A: Hermes Agent Skill Pack

Description: a set of reusable Hermes skills for solo founders, Obsidian memory, Telegram-first project management, or small automation workflows.

Pros:

- Very close to current Hermes usage.
- Small MVP is possible.
- Clear value for existing Hermes users.

Cons:

- May look narrow if the evaluator is not already familiar with Hermes Agent.
- Skill formats and distribution expectations may need more research.
- Could drift into private workflow details if not sanitized carefully.

## Candidate B: Hermes x Obsidian Project OS Template

Description: a reusable template for combining Obsidian project memory, AI-team routing, PR readiness, decision logs, and safe scheduled-job specs.

Pros:

- Useful to non-engineers and small teams, not only developers.
- Can be built from real operational patterns without exposing private data.
- Documentation-first MVP is safe and quick.
- Clear security story: separate private notes from public templates.
- If OpenAI support is not granted, it remains useful as onboarding/sales/public education material.

Cons:

- Risk of being seen as only documentation, not software.
- Needs concrete examples and possibly a small automation helper later.
- Adoption metrics will initially be low after publication.

## Candidate C: Hermes MCP / Integration Tool

Description: a small MCP server or integration, such as an Obsidian project-note reader, PR readiness summarizer, or Telegram command helper.

Pros:

- More obviously a developer OSS project.
- Easier to explain Codex usage for code review and issue triage.
- Could become a package with measurable downloads.

Cons:

- Higher implementation cost.
- Higher security risk if it touches notes, GitHub, or messaging tools.
- Requires dependency and permission decisions before MVP.

## Decision

Choose **Candidate B: Hermes x Obsidian Project OS Template** as the first candidate.

## Reasoning

Candidate B is the best first step because it is useful, safe, and can be published after human review without inventing adoption metrics. It creates a public artifact from a real workflow while avoiding secret handling and external service writes.

Candidate C can become a follow-up if the template gains real use or if users ask for automation. Candidate A can be included later as an optional companion pack.

## Honest application position

Do not claim current adoption. Publish and maintain the project first, then apply with real public repository data and a clear explanation of why the template helps maintainers and small teams operate AI-assisted projects safely.
