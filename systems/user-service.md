---
type: System
title: User service
description: Owns user profile data and is the source of the user CDC stream consumed by analytics.
owner: team:backend
status: stable
verified: { by: human:backend-lead, at: 2026-09-15T09:00:00Z }
tags: [system, users, cdc]
---

# What it is

The service of record for user profiles. Every change to a profile row is
published on the user CDC stream.

# Fields

| Field        | Type      | Notes                                                    |
|--------------|-----------|----------------------------------------------------------|
| `user_id`        | string    | Primary key.                                             |
| `first_name`     | string    |                                                          |
| `last_name`      | string    |                                                          |
| `date_of_birth`  | date      | Required for identity checks.                            |
| `email`          | string    | Login identifier.                                        |
| `gender`         | string    | Collection stopped 2026-09, see [decision](/decisions/stop-collecting-gender.md). Still present: see Consumers. |
| `created_at`     | timestamp | UTC.                                                     |

# Consumers

- CDC stream → [Analytics segments](/systems/analytics-segments.md) — owner [Analytics](/teams/analytics.md)

# Changing a field

Follow [remove a field](/playbooks/remove-a-field.md). Check Consumers first.
