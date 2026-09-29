---
type: Reference
title: OKF starter bundle
description: A minimal Open Knowledge Format bundle for one team — clone, rename, replace the examples.
---

# OKF starter bundle

A small knowledge bundle a human and an agent can both read.
Plain Markdown with YAML frontmatter, cross-linked. Nothing to install.

Spec: https://github.com/GoogleCloudPlatform/open-knowledge-format (SPEC.md, v0.2)
Announcement: https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing

## What's inside

```
index.md                              what's here (progressive disclosure)
log.md                                what changed, newest first
systems/user-service.md               one system, with its Consumers section
systems/analytics-segments.md         the consumer, owned by another team
decisions/stop-collecting-gender.md   one decision, with its reason
playbooks/remove-a-field.md           one process: check consumers first
teams/analytics.md                    who to ask
```

The example is a real shape: a field nothing in the codebase used, an
agent that removed it, a reviewer who approved it, and a consumer on the
other side of a CDC stream that nobody in the room knew about.

## Start on Monday

1. Copy this directory into your repo as `.okf/` (or keep it as its own repo).
2. Replace the examples with the five concepts people ask you about most.
3. Write the Consumers section for the system people change most. Add `owner`.
4. Point your agents at it (see below) and delete the per-tool copies.
5. Change `.okf/` in the same PR as the code. Same reviewer.

## Pointing agents at the bundle

Put this in `CLAUDE.md`, `AGENTS.md`, or whatever your tool reads —
and nothing else in that file:

```
Before changing anything, read .okf/index.md and follow its links.
Treat decisions/ as binding: do not remove or bypass what a decision keeps
without asking its owner.
```

## Conventions used here

- `type` is the only required frontmatter key (System, Decision, Playbook, Team, Reference).
- `owner: team:<name>` is a producer extension — the spec allows any extra key.
- `verified`, `status`, `stale_after` follow OKF v0.2 (a backward-compatible
  extension of v0.1; v0.1 consumers simply ignore them).
- Links are bundle-relative and start with `/`.
