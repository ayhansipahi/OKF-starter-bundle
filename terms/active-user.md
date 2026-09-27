---
type: Term
title: Active user
description: A user with at least one authenticated session in the last 30 days.
owner: team:product
status: stable
verified: { by: human:product-lead, at: 2026-09-01T09:00:00Z }
tags: [definition, metrics]
---

# Definition

A user is **active** when they have at least one authenticated session in the
trailing 30 days, measured on [user events](/systems/user-events.md).

Not counted: password-reset flows, bot traffic, internal test accounts.

# Used by

- The product dashboard (weekly active users)
- The churn model owned by [Data Science](/teams/data-science.md)
- Any agent answering "how many active users do we have"

# If you need a different window

Do not redefine this term. Add a new one (for example `active-user-7d`) and
link both.
