---
type: Decision
title: Keep session_source in user events
description: Data Science feature pipeline reads it. Do not remove.
owner: team:data-science
status: stable
verified: { by: human:ds-lead, at: 2026-06-25T09:00:00Z }
stale_after: 2027-01-01T00:00:00Z
tags: [fence, schema]
---

# What is kept

The `session_source` field on [user events](/systems/user-events.md).

# Why

The churn model uses `session_source` as a feature. Nothing in the backend
repo reads it; the Data Science pipeline does. Removing it silently
degrades the model without failing any test in this repo.

# Before changing

Ask [Data Science](/teams/data-science.md). If the model stops using the
field, set `status: deprecated` here first, then remove the field.

# History

- 2024-11: field added for an A/B test.
- 2025-03: A/B test ended; field kept because the churn model had started
  reading it.
