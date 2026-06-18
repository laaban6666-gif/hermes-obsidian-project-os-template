# AI Team Room Template

Use this note as a chat-style room for AI-assisted collaboration. Keep it public-safe: do not paste secrets, private account details, customer data, or non-public credentials.

## Room metadata

- Project: `<PROJECT_NAME>`
- Task: `<TASK_NAME>`
- Date: `<YYYY-MM-DD>`
- Branch/workspace: `<BRANCH_OR_LOCAL_PATH>`
- Related project note: `<LINK>`
- Related PR/readiness note: `<LINK>`

## Roles

- **Coordinator:** scopes the task, sets gates, decides who acts next.
- **Implementer:** makes local changes inside the approved scope.
- **Reviewer:** verifies results, checks safety, and blocks risky changes.
- **Human:** approves irreversible operations, publication, production changes, or anything involving private data.

## Gates

A task may move forward only when the current gate is satisfied.

- [ ] **Gate 1 — Scope:** goal, allowed files/actions, and out-of-scope items are clear.
- [ ] **Gate 2 — Implementation:** changes are made locally and summarized.
- [ ] **Gate 3 — Verification:** checks/tests/review steps are run or explicitly marked not applicable.
- [ ] **Gate 4 — Safety:** no secrets, no personal data, no production-only config, no irreversible action.
- [ ] **Gate 5 — Human approval:** required before merge, publish, deploy, billing, forms, or external submission.

## Chat log

### `<YYYY-MM-DD HH:MM>` — Coordinator

**Intent:** `<WHAT_WE_ARE_TRYING_TO_DO>`

**Approved scope:**

- `<FILE_OR_AREA>`

**Out of scope:**

- `<RISKY_OR_UNRELATED_WORK>`

**Next role:** Implementer

**Gate status:** Gate 1 is `<passed | blocked>` because `<REASON>`.

---

### `<YYYY-MM-DD HH:MM>` — Implementer

**Actions taken:**

- `<CHANGE_MADE>`

**Files touched:**

- `<PATH>`

**Assumptions:**

- `<ASSUMPTION>`

**Next role:** Reviewer

**Gate status:** Gate 2 is `<passed | blocked>` because `<REASON>`.

---

### `<YYYY-MM-DD HH:MM>` — Reviewer

**Checks run:**

```text
<COMMANDS_AND_RESULTS>
```

**Review findings:**

- `<FINDING>`

**Safety review:**

- [ ] No secrets or credentials.
- [ ] No personal data.
- [ ] No production-only configuration.
- [ ] No irreversible operation.
- [ ] Any external publication/deploy/merge is waiting for human approval.

**Next role:** `<Coordinator | Human | Implementer>`

**Gate status:** Gate 3 is `<passed | blocked>` and Gate 4 is `<passed | blocked>` because `<REASON>`.

---

### `<YYYY-MM-DD HH:MM>` — Human approval checkpoint

**Decision:** `<approved | changes requested | rejected | deferred>`

**Notes:**

- `<APPROVAL_NOTES>`

**Gate status:** Gate 5 is `<passed | blocked>`.

## Final handoff

```text
Result:
Evidence:
Remaining risks:
Next action:
Owner:
```
