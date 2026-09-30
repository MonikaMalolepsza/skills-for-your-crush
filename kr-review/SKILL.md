---
name: kr-review
description: "Review all changes on the current git branch versus master against the KR merge-request checklist (general, backend, tooling). Runs nr-check all, reports every issue found, and fixes any that surface. Use when the user wants to KR-review a branch before merging, or asks to \"kr-review\"."
disable-model-invocation: true
---

Review every change on the current branch against `master` using the checklist below, run `nr-check all`, report all findings, and **fix any issues you find**.

## Process

### 1. Pin the diff

Compare the current branch against `master` using the merge-base:

- Diff: `git diff master...HEAD`
- Commits: `git log master..HEAD --oneline`

Confirm `master` resolves (`git rev-parse master`) and the diff is non-empty before continuing. If the branch tracks `main` instead of `master`, use that.

### 2. Run `nr-check all`

Run `nr-check all` and capture its full output. Treat every issue it reports as a finding that **must be fixed** — don't just list them. Re-run `nr-check all` after fixing to confirm it passes clean.

### 3. Walk the checklist

Go through every item below against the diff. For each, record **pass**, **fail**, or **n/a** with a one-line justification. Every **fail** must be fixed before you finish.

#### General

| Item | What to check |
| --- | --- |
| Code and documentation cleanup | No dead code, stray debug output, commented-out blocks, or stale docs. |
| Acceptance criteria met | The change delivers what the originating issue/spec asked for. |
| English spelling and grammar | Comments, docs, messages, and identifiers read correctly. |
| Swagger documentation | New/changed endpoints are documented in Swagger. |
| DB index for performance | New queries/filters are backed by appropriate indexes. |
| Sonar issues | No new Sonar findings introduced by the diff. |

#### Backend

| Item | What to check |
| --- | --- |
| Comprehensive tests | New/changed behaviour is covered by tests, including edge cases. |
| GIVEN/WHEN/THEN/EXPECT comments | Tests use the GIVEN/WHEN/THEN/EXPECT structure. |
| Test naming conventions | Names follow the Testing Guide. |
| Package name in variable names | Variables don't redundantly repeat the package name. |
| Error messages | No "failed to" / "could not" prefixes in error strings. |
| Duplicate package name in filenames | Filenames don't repeat the package name (e.g. `user/user_service.go`). |
| Go update | Go version is current. |
| Library update | All repo dependencies are up to date. |

#### Frontend

No specific items — mark n/a unless the diff touches frontend, in which case apply the General items.

### 4. Fix everything

For each **fail** from the checklist or `nr-check all`, make the fix at its root cause, then re-verify. Keep going until the checklist is all pass/n/a and `nr-check all` reports clean.

### 5. Report

Present a table of every checklist item with its status and note, followed by:

- `nr-check all` result (before and after fixes).
- A list of fixes applied, each with a `file:line` reference.
- Any remaining item you could **not** fix, with the reason it's blocked.
