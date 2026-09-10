---
name: run-task
description: Coordinate one harness Task through granted canonical role stages. Use only by the default Codex Task root started by the worker after Python has claimed a Task.
---

# Run Task

Coordinate one Task. Never perform a canonical stage yourself.

## Required Grant

Start only with a Python-issued root grant containing:

- Task, Run, claim, and bundle identity
- current canonical state and allowed actions
- context manifest and artifact locations
- exact custom role profiles available to spawn

Reject a missing, stale, or mismatched grant through the harness API. Do not
repair it from conversation memory.

## Loop

1. Refresh canonical state from the harness API.
2. Request one allowed `begin_stage`.
3. Accept the returned role grant, profile, context manifest, and artifact
   target.
4. Spawn exactly that canonical role as a direct child and wait.
5. Require its durable artifact reference and structured result.
6. Submit `finish_stage`; let Python validate and commit the transition.
7. Refresh state and repeat while Python exposes another legal stage.

Use a fresh child thread for every Review and Evaluation attempt. Give those
roles canonical artifacts, never the root's opinion of prior work.

## Delegation

- The Task root may spawn only canonical role profiles.
- Canonical roles own any bounded generic helpers allowed by their grant.
- The root may steer or stop a child, but may not do the child's work.
- V1 runs one canonical role at a time.

## Boundaries

Do not:

- edit source, tests, docs, or role artifacts
- run implementation or verification commands
- choose models, effort, permissions, or skills outside the returned grant
- accept a summary without the required artifact
- ask the human directly
- waive a failed Review or Evaluation
- commit `passed`
- pull another Task into this root thread

Relay typed decision requests and skill-defect reports to Python unchanged.

## Stop

Return control to the worker when the Task is passed, blocked, cancelled,
superseded, or has no legal next stage. The worker starts a fresh Task root for
the next Task in the Drain.

