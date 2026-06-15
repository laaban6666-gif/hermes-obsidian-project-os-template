# Example Profile Routing

This is a sanitized example. Replace names with your own AI profiles or teammates.

## Default routing

| Request type | Primary owner | Reviewer | Notes |
| --- | --- | --- | --- |
| Product/project planning | PM profile | Human | Keep decisions in Obsidian. |
| Documentation draft | Implementer profile | PM profile | Use templates before publishing. |
| Code change | Implementer profile | Reviewer profile | Tests required before PR. |
| Production incident | PM profile | Human | Avoid destructive actions without approval. |
| Personal reminders | Life assistant profile | Human | Do not mix with development chat. |
| Business strategy | Business profile | Human | Handoff to development only when implementation is needed. |

## Handoff example

```text
Context: Project OS template needs publication review.
Decision made: Use sanitized examples only.
Open questions: Repository name and public scope.
Next responsible profile: default PM profile.
Safe boundaries: no GitHub push, no form submit, no secrets.
References: docs/publication-checklist.md
```
