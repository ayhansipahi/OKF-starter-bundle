---
okf_version: "0.2"
---

# Systems

* [User service](systems/user-service.md) - Owns user profile data; source of the user CDC stream.
* [Analytics segments](systems/analytics-segments.md) - Segmentation built from the user CDC stream.

# Decisions

* [Stop collecting gender](decisions/stop-collecting-gender.md) - Collection stopped; column stays until segments migrate.

# Playbooks

* [Remove a field from a service](playbooks/remove-a-field.md) - Check consumers, stop writing, migrate, then remove.

# Teams

* [Analytics](teams/analytics.md) - Owns segments and the analytics side of the CDC stream.
