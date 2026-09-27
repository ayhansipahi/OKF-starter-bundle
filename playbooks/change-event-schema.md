---
type: Playbook
title: Change the event schema
description: Steps for adding, renaming or removing a field on user events.
owner: team:backend
status: stable
verified: { by: human:backend-lead, at: 2026-09-15T09:00:00Z }
tags: [playbook, schema]
---

# Before you start

1. Read [user events](/systems/user-events.md).
2. Check `decisions/` for anything that keeps the field you want to touch.
   Currently: [keep session_source](/decisions/keep-session-source-field.md).
3. If a decision applies, ask its `owner` before continuing.

# Steps

1. Add the field as optional; never rename in place.
2. Update the schema table in [user events](/systems/user-events.md).
3. Notify consumers listed under "Used by" in the affected terms.
4. Remove old fields only after a decision marks them `deprecated`.
5. Append an entry to `/log.md` in the same PR.
