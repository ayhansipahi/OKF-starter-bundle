---
type: Decision
title: Stop collecting gender; keep the field until segments migrate
description: Collection stopped in 2026-09; the column stays until Analytics migrates the segments that depend on it.
owner: team:backend
status: stable
verified: { by: human:backend-lead, at: 2026-09-20T09:00:00Z }
stale_after: 2027-03-01T00:00:00Z
tags: [decision, data-minimization, cdc]
---

# What was decided

Stop collecting `gender` in the [user service](/systems/user-service.md).
Keep the column until [Analytics segments](/systems/analytics-segments.md)
no longer depend on it.

# Why

The product no longer needs the field (data minimization). Removing the
column outright would break segment definitions fed through the CDC stream —
a dependency that was not documented anywhere the change author or the
reviewer would look.

# Next step

Analytics migrates the segments; then follow
[remove a field](/playbooks/remove-a-field.md) to drop the column and set
this decision to `deprecated`.
