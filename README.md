---
type: Reference
title: OKF starter bundle
description: A minimal Open Knowledge Format bundle for one team — clone, rename, replace the examples.
---

# OKF starter bundle

A small knowledge bundle a human and an agent can both read.
Plain Markdown with YAML frontmatter, cross-linked. Nothing to install.

Companion repo for the OKF talk at the SCHUFA TechKonferenz (bonify).

Spec: https://github.com/GoogleCloudPlatform/open-knowledge-format (SPEC.md, v0.2)
Announcement: https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing

## What's inside

```
index.md                                  what's here (progressive disclosure)
log.md                                    what changed, newest first
terms/active-user.md                      one shared definition
systems/user-events.md                    one system people keep asking about
decisions/keep-session-source-field.md    one fence, with its reason
playbooks/change-event-schema.md          one process, linking to the fence
teams/data-science.md                     who to ask
```

## Start on Monday

1. Copy this directory into your repo as `.okf/` (or keep it as its own repo).
2. Replace the examples with the five concepts people ask you about most.
3. Write one decision: the fence your team already argues about. Add `owner`.
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

- `type` is the only required frontmatter key (Term, System, Decision, Playbook, Team, Reference).
- `owner: team:<name>` is a producer extension — the spec allows any extra key.
- `verified`, `status`, `stale_after` follow OKF v0.2 (a backward-compatible
  extension of v0.1; v0.1 consumers simply ignore them).
- Links are bundle-relative and start with `/`.
