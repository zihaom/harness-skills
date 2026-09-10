---
name: code-quality
description: Apply the harness's project-aware maintainability standard while implementing, changing code under a Debug/Search mutation grant, or independently reviewing a Task. Use when judging naming, cohesion, simplicity, contracts, effects, tests, cleanup, or maintainability findings.
license: MIT
metadata:
  version: "0.2.0"
  adapted-from: "wondelai/skills clean-code@dd37ee506ff558e939b3d421557987cced49b866"
---

# Code Quality

Make code easy to understand, verify, and change without imposing one
programming ideology.

This is a shared reference. It does not own a stage or standalone artifact.
Implementation and mutation-granted Debug/Search apply it while changing code.
Code Review applies it independently and records findings in the review
artifact.

## Authority

Read first:

1. the confirmed Task and accepted design artifacts
2. Project `AGENTS.md`, stable docs, and Project-local standards
3. the surrounding code and tests

Confirmed architecture and Project conventions override this skill. Existing
code is evidence of convention, not automatic proof of good design. Report a
material conflict; do not silently choose a new architecture.

## Standard

Prefer code that:

- uses domain-accurate names that reveal intent
- keeps behavior that changes together close together
- gives each unit a coherent responsibility
- makes inputs, outputs, errors, state changes, and external effects visible
- uses the least indirection that keeps the design clear
- removes duplication when it represents one stable concept
- tests meaningful behavior, boundaries, and failure paths
- keeps tests readable and resistant to irrelevant implementation changes
- uses comments for reasons, constraints, and non-obvious tradeoffs
- leaves touched code coherent without expanding into unrelated cleanup

An abstraction must earn its cost. Do not create a helper, interface, layer, or
pattern merely to make the code look organized.

## Implementation

Before returning the Implementation artifact:

1. compare the change with nearby conventions and the confirmed design
2. simplify names, control flow, contracts, and effects where that improves
   the touched behavior
3. remove accidental duplication and dead code introduced or exposed by the
   change when removal is safe and in scope
4. verify behavior at the most meaningful available seam
5. record any deliberate local debt, convention conflict, or deferred cleanup

Do not perform a broad refactor merely because nearby code could be improved.

## Debug/Search

Do not use this skill to bias read-only reconnaissance toward cleanup.

After receiving a mutation grant:

1. apply the same standard as Implementation to the fix
2. keep the change focused on the evidenced failure
3. clean up code made obsolete or incoherent by that fix when safe and in scope
4. record remaining debt instead of broadening the diagnosis

## Code Review

Review independently. Do not trust Implementation's quality self-assessment.

Classify each quality finding:

- `blocking`: a confirmed-design violation or material risk to understanding,
  correctness, safe change, testing, or long-term consistency
- `advisory`: a reasonable preference with no demonstrated material
  consequence

A blocking finding must cite the code, the violated authority or principle,
the likely consequence, and the smallest credible correction. Do not block on
personal style, unfamiliarity, or formatting that deterministic tooling owns.

## Never Mandate

Do not require:

- numeric quality scores
- fixed function, class, or argument-count limits
- object-oriented nouns/verbs or a particular design-pattern catalog
- exceptions, option types, null objects, or another universal error strategy
- TDD for every change
- comments to be removed merely because the code can restate them

Read [provenance.md](references/provenance.md) for the pinned source, retained
principles, removals, and license.
