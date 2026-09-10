# Task Boundary

## Whole-Tree Context

The splitter needs enough of the whole tree to understand the current node's
role, not every descendant's implementation detail. Gather:

- the ancestor chain and ultimate outcome;
- the current Task's inputs, outcome, and definition of done;
- sibling responsibilities and exclusions;
- predecessor and successor contracts;
- existing child splits and completed-result facts;
- cross-cutting integration and verification obligations; and
- the intended executor's qualitative capability and context constraints.

## Hard Semantic Boundary

A child is `leaf_ready` only when all conditions hold:

1. **One contribution:** one coherent behavioral, analytical, operational, or
   mechanical outcome.
2. **Resolved decisions:** strategy, major structure, scope, authority, and
   acceptance are fixed; only local execution judgment remains.
3. **Fresh-context fit:** mandatory context fits one fresh target-model session
   without compaction or implementation handoff.
4. **One bounded execution:** one owner can perform the work and its cleanup in
   one bounded attempt lineage.
5. **Independent done condition:** completion is directly observable without
   unfinished descendants or future siblings.
6. **Explicit interfaces:** predecessor inputs and successor outputs are named.
7. **Isolated retry:** failure can be retried or redesigned without replaying
   completed sibling work.
8. **Cohesive surface:** the work changes or produces one understandable unit,
   even when an atomic mechanical migration spans many files or systems.

Files, lines, tokens, tool calls, elapsed time, and benchmark scores may inform
judgment but never define smallness.

A coherent child that fails any condition is `needs_split`. An indivisible
child that cannot satisfy the boundary returns `SPLIT_CAPACITY_BLOCKED` rather
than a misleading leaf.

A `needs_split` child is not runnable or complete merely because it appears in
the list. It becomes completable when a later invocation supplies its own
immediate children.

## Completion Law

The split is valid only when:

```text
parent complete <=> every immediate child complete in order
```

Assign setup, migration, integration, cleanup, documentation, and verification
to children whenever the parent requires them. There is no implicit work after
the last child. Shared concerns must either have one explicit owner or become a
dedicated child; do not duplicate ownership.

## Output Template

```markdown
## Split: <current Task>

**Role in tree:** <parent contribution, sibling boundary, predecessor/successor>
**Parent done:** <exact completion condition>
**Completion equation:** `<parent> = <child-1> + ... + <child-n>`

1. **<child key — title>**
   - Contribution:
   - Inputs:
   - Outputs:
   - Blocked by: none | <immediate predecessor>
   - Definition of done:
   - Excludes:
   - Boundary: leaf_ready | needs_split
   - Boundary evidence:

## Coverage

- <parent obligation> -> <one child owner>
- Gaps: none
- Duplicate owners: none
```

The output is one immediate-child list. It contains no `children`, nested list,
tracker operation, execution state, or completion mutation.

For example:

```text
to_tasks(D2B, tree)  -> [D2B1, D2B2, D2B3]
to_tasks(D2B2, tree) -> [D2B2a, D2B2b]
```

The second result does not rewrite the first result into a nested document; the
surrounding task tree supplies the relationship.
