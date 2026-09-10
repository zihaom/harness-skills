---
name: project-docs-init
description: Initialize a hierarchical, code-grounded project wiki for a repo. Use during Project Init or docs bootstrap when a repo needs navigation, a project map, architecture docs, domain context, and AGENTS.md without inventing target architecture.
---

# Project Docs Init

Build the first stable docs for a repository.

Current code truth comes first. Target architecture waits until it has been
grilled or already confirmed.

## Read First

1. Root orientation, agent guidance, manifests, and test configuration.
2. Top-level directories and their entrypoints.
3. Existing docs, domain context, and ADRs.
4. Test layout and supported verification commands.
5. Project-local skills and existing harness metadata.

Build a map before sampling deeper boundaries. Do not read the repository
blindly.

## Create

Create missing docs gradually:

1. `docs/README.md`
2. `docs/project_map.md`
3. `docs/architecture/README.md`
4. `CONTEXT.md` or the project's existing domain-language equivalent
5. `AGENTS.md` or the existing agent-guidance equivalent

Only create deeper pages after the top-level reader path is coherent.

## Page Pattern

Use only the sections that help:

```markdown
# Title

## Purpose
## What This Owns
## What This Does Not Own
## Key Concepts
## How It Works
## Inputs And Outputs
## Contracts
## Relationship To Other Modules
## Current Code Truth
## Target Architecture
## Migration Gap
## Where To Read Next
```

## Rules

- Ground current claims in code, config, manifests, or tests.
- Label target architecture as target.
- Leave undecided target architecture empty or explicitly draft.
- Keep volatile status out of stable docs.
- Keep domain context free of implementation plans.
- Do not create PRDs, Issues, or Tasks during docs initialization.

## Completion

The initial docs pass only when:

- a fresh reader knows where to start
- ownership boundaries match the repository
- current truth and target architecture are distinct
- links lead to the next useful page
- uncertainty is visible

Read [references/wiki-shape.md](references/wiki-shape.md) for the hierarchy.

