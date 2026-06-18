# Sample Decision: Use a starter vault

## Decision

Include an Obsidian-ready `starter-vault/` directory in the public template.

## Date

2026-06-18

## Status

accepted

## Context

Users should be able to try the project operating system without manually arranging folders or copying every template first.

## Options considered

### Option A — Templates only

- Pros: Small repository and easy maintenance.
- Cons: Users must understand the intended vault structure before they can start.

### Option B — Starter vault plus standalone templates

- Pros: Users can open the vault immediately, while maintainers can still copy individual templates.
- Cons: Some template content is duplicated and must be kept in sync.

### Option C — Script-generated vault

- Pros: Avoids duplicated files.
- Cons: Adds setup friction and requires users to run tooling before trying the template.

## Chosen option

Option B — starter vault plus standalone templates.

## Reasoning

The template is meant to be adoptable quickly. A ready-to-open vault makes the first experience concrete, while standalone templates keep the repository easy to browse and copy.

## Risks

- Template and vault copies may drift over time.
- Users may mistake samples for required process.

## Rollback / revisit trigger

Revisit if users report that the starter vault is confusing, too large, or harder to maintain than standalone templates.

## Links

- Project note: `[[Sample Project]]`
- AI room: `[[AI Team Room]]`
