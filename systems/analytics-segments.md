---
type: System
title: Analytics segments
description: User segmentation used by dashboards and campaigns; built from the user CDC stream.
owner: team:analytics
status: stable
verified: { by: human:analytics-lead, at: 2026-09-15T09:00:00Z }
tags: [analytics, segments, cdc]
---

# What it is

Segment definitions computed nightly from the user CDC stream. Dashboards
and campaign targeting read the segments, not the user service.

# Depends on

- [User service](/systems/user-service.md) fields: `gender`, `created_at`

# If a field it depends on changes

Analytics must migrate the affected segment definitions before the field is
removed. Ask [Analytics](/teams/analytics.md); see
[remove a field](/playbooks/remove-a-field.md).
