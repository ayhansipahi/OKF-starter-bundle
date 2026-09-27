---
type: Team
title: Data Science
description: Owns the churn model and the feature pipeline that consumes user events.
owner: team:data-science
status: stable
---

# Owns

- The churn model
- The feature pipeline reading [user events](/systems/user-events.md)
- [Keep session_source](/decisions/keep-session-source-field.md)

# Ask them when

- You change a field they consume
- You need a new metric definition based on [active user](/terms/active-user.md)
