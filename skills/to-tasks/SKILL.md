---
name: to-tasks
description: Split any complex task into an ordered list of smaller immediate subtasks whose completion exactly completes the parent. Use when work is too broad for one model or session, when any node in an existing task tree needs children, or when changed execution reality requires its entire split to be recomputed.
---

# To Tasks

Act as a pure splitter:

```text
to_tasks(current_task, whole_tree) -> ordered immediate subtasks
```

Return one flat list. Repeated calls on a child create deeper levels; one call
never embeds descendants.

Read [task boundary](references/task-boundary.md) before splitting.

## Gather The Tree

Gather facts from the environment before asking for them. Read the whole known
tree at useful resolution: ancestor goals, the current Task, siblings, existing
descendants, dependency edges, completion evidence, and target-executor
constraints.

Locate the current Task precisely:

- what parent outcome it completes;
- what predecessors provide and successors need;
- what siblings own and therefore exclude; and
- its exact definition of done.

Stop with `SPLIT_DECISION_REQUIRED` when a missing product or design decision
prevents a truthful boundary. Do not decide it while splitting.

## Split One Level

1. State the parent completion law before naming children. Completion
   criterion: every parent obligation, including integration and verification,
   has an owner in the proposed list.
2. Partition the parent into a strict sequence of immediate children. Each
   child is narrower, owns one coherent contribution, names its inputs and
   outputs, and excludes its siblings' responsibilities. Completion criterion:
   no child contains another child list and every child after the first names
   its immediate predecessor.
3. Apply the hard semantic boundary in the reference. Mark a child
   `leaf_ready` only when one appropriately capable model can complete it in a
   fresh session without compaction or implementation handoff. Mark a coherent
   but still-complex child `needs_split`; a later invocation may split it using
   the updated whole tree. Completion criterion: every status has explicit
   boundary evidence, never a numerical score.
4. Prove equivalence: all children completed in order implies the parent is
   complete, with no extra parent-level work. Add a final integration or
   verification child when that work would otherwise remain outside the list.
   Completion criterion: coverage is sufficient, non-overlapping, and has no
   hidden remainder.
5. Return the list using the reference template. Completion criterion: the
   response contains the parent boundary, ordered children, coverage map, and
   completion equation.

## Recompute

When execution changes what the current split requires, discard that split as
a plan and call this skill again against current facts and the entire updated
tree. Recompute the whole immediate-child list; do not patch individual entries
in place. Historical results remain facts in the input tree.

## Boundary

Split only. Do not materialize tasks, mutate a tracker, schedule or execute
work, validate external state, monitor progress, close the parent, or prescribe
an orchestration platform. Return the decomposition in conversation unless the
caller explicitly provides an output target.
