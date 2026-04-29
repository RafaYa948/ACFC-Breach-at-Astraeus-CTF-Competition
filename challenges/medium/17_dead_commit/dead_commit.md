# Dead Commit 

**Category:** Hidden Data & Access
**Difficulty:** Medium
**Points:** 267
**Files:** None
**Platform:** Docker
**Prepared by:** Rafa Islam Diba

---

## Description

> A Git repository was recovered from ASTRS-WKS-014 during the forensic investigation.
>
> It belongs to a developer who was building the station's internal API.
>
> Something was committed that should not have been.
> Then it was removed.
>
> But removed does not mean gone.
>
> Flag Format: `ACFC{...}`

---

## What This Tests

- Git commit history analysis — reading log messages for suspicious entries
- Git stash awareness — knowing that uncommitted work can be saved and recovered
- Dangling object recovery — understanding that `git reset` does not delete objects, only removes references to them
- Base64 decoding — recovering the flag from encoded content in the stash
- Methodical investigation — not stopping at the first obvious finding

---

