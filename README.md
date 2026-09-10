# Harness Global Skills

Canonical, versioned skills for the harness control system.

## Status

This repository is in bootstrap state. It contains audited candidate skills,
but no runtime bundle has been released or activated.

## Design Rule

A skill must add something the model does not reliably have already:

- a harness-specific protocol
- project or domain knowledge
- a non-obvious tool workflow
- an artifact contract
- a corrective discipline proven by evaluation

Generic advice is not enough. Preserve reasoning freedom unless the operation
is fragile enough to need a narrow procedure.

## Boundaries

- Python owns scheduling, claims, leases, transitions, and pass commitment.
- Agent profiles own model, effort, sandbox, tools, and skill allowlists.
- Skills own repeatable LLM-facing procedures and artifact quality.
- Project-specific skills remain beside their repositories.
- Run skills never ask the human directly. They emit a typed decision request.

## Layout

```text
catalog.json             bootstrap catalog; not a runtime lock
docs/                    audit and upstream provenance
skills/<name>/           canonical skill source
upstreams/               inert source/reference snapshots; never active by presence
```

The harness control repository will pin a released commit and materialized tree
digest. Workers must never hot-edit an installed bundle.

## Promotion

A candidate becomes releasable only after:

1. Talk records the concrete purpose, owner, adjacent boundaries, and conflicts
2. the human approves global promotion
3. boundary review and schema validation pass
4. any risk-proportionate rehearsal named in the approved release plan passes
5. a tagged repository commit is created

A generic no-skill comparison is optional evidence, not promotion authority.
