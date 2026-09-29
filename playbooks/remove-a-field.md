---
type: Playbook
title: Remove a field from a service
description: Steps for removing a field that other systems may consume through events or CDC.
owner: team:backend
status: stable
verified: { by: human:backend-lead, at: 2026-09-20T09:00:00Z }
tags: [playbook, schema, cdc]
---

# Before you start

1. Open the system's concept and read **Consumers**
   (example: [user service](/systems/user-service.md)).
2. For every consumer, ask its `owner` whether they still depend on the field.
3. Check `decisions/` for anything that keeps the field.

# Steps

1. Stop writing the field (collection stops; the column stays).
2. Mark the field deprecated in the system's concept.
3. Consumers migrate off the field. Their owner confirms in the PR.
4. Remove the column and the CDC field together.
5. Update the system's concept and append an entry to `/log.md` in the same PR.
