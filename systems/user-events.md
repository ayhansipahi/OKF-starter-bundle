---
type: System
title: User events
description: The user-event stream produced by the backend and consumed by analytics and Data Science.
owner: team:backend
status: stable
verified: { by: human:backend-lead, at: 2026-09-15T09:00:00Z }
tags: [events, schema]
---

# What it is

Every user action is published as an event. The backend produces; the
analytics warehouse and the Data Science feature pipeline consume.

# Schema

| Field            | Type      | Notes                                                        |
|------------------|-----------|--------------------------------------------------------------|
| `event_id`       | string    | Unique per event.                                            |
| `user_id`        | string    | See [active user](/terms/active-user.md).                    |
| `event_type`     | string    | `login`, `view`, `purchase`, ...                             |
| `session_source` | string    | Unused here — kept on purpose, see the [decision](/decisions/keep-session-source-field.md). |
| `occurred_at`    | timestamp | UTC.                                                         |

# Changing the schema

Follow [change the event schema](/playbooks/change-event-schema.md).
