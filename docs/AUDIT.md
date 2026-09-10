# Initial Skill Audit

## Test

Each candidate was checked for:

1. information or procedure a capable model does not already have
2. one non-overlapping owner and trigger
3. compatibility with unattended Run stages
4. compatibility with harness artifacts and Python state authority
5. freedom appropriate to the fragility of the job

## Findings

### Keep Or Adapt

| Candidate | Disposition | Reason |
|---|---|---|
| Matt `grilling`, `grill-with-docs`, `domain-modeling` | Talk only, adapt | Valuable interactive discovery; direct human interaction is intentional |
| Matt `to-spec`, `to-tickets` | Talk inspiration only | Human-oriented and tracker-specific; harness keeps PRD, Issue, and Task |
| Matt `code-review` | Adapt | Strong Standards versus Spec separation; must use harness fixed points, Task contract, evidence, and docs |
| Matt `research` | Adapt for Debug/Search | Good primary-source rule; output must use the Run artifact contract |
| Matt `diagnosing-bugs` | Adapt | Strong feedback-loop discipline; its ban on bounded reconnaissance is too rigid |
| Matt `tdd` | Conditional reference | Useful at a Task-approved seam; must not become mandatory for every change |
| Matt `prototype`, `improve-codebase-architecture` | Talk only | Both require human selection and design feedback |
| `project-docs-init`, `project-docs-maintenance` | Keep and refine | Harness-specific docs truth and hierarchy are not generic model knowledge |

### Do Not Put In The Default Run Bundle

| Candidate | Reason |
|---|---|
| `clean-code` | Long, language-biased, arbitrary size rules, and forced scoring |
| `pragmatic-programmer` | Broad philosophy overlapping implementation, testing, and architecture |
| `domain-driven-design` | Useful design reference, but default activation encourages pattern projection |
| `refactoring-patterns` | Catalog reference, not a universal execution workflow |
| `software-design-philosophy` | Overlaps `codebase-design` and biases Evaluation toward one ideology |
| `working-with-legacy-code` | Useful only when a Project or Task explicitly declares the legacy-code condition |
| Superpowers orchestration suite | Duplicates the harness state machine, requires human checkpoints, and over-prescribes agent behavior |
| Superpowers TDD/debug/review skills | Overlap Matt candidates and contain rigid global mandates |
| prototype strat-live skills | Project-specific file workflows superseded by canonical state and artifacts |

### Confirmed Code-Quality Adaptation

Maintainability remains a Run responsibility even though the broad
craftsmanship skills are rejected. Round 31 confirms one concise,
project-aware `code-quality` reference shared by Implementation, mutation-
granted Debug/Search work, and Code Review. It is adapted from the pinned
Wondel.ai `clean-code` skill rather than authored as an unrelated ideology.

The adaptation preserves clear intent, cohesion, locality, explicit contracts
and effects, justified abstractions, meaningful tests, and bounded cleanup. It
removes arbitrary scoring, fixed function-size rules, blanket comment rules,
mandatory object-oriented patterns, and style preferences that override the
repository. Blocking findings require a material maintainability consequence;
other preferences are advisory.

Debug/Search does not apply this skill during read-only reconnaissance.

### Candidate Task-Decomposition Adaptation

`to-tasks` is a generalized pure counterpart to Matt's tracker-oriented
`to-tickets`. Given any current Task plus the surrounding tree, it returns one
ordered flat list of immediate children whose completion is sufficient to
complete that Task. Repeated calls create deeper levels; one result never nests
another result.

The skill recomputes the whole immediate split when facts change and carries no
materialization, tracker, validation, execution, monitoring, or closure
authority. Its hard model-fit boundary is semantic rather than a file, line,
token, duration, or benchmark threshold.

### Retire

- `ask-matt`: deterministic Talk command routing replaces it.
- `setup-matt-pocock-skills`: Project Init replaces it.
- `implement` as written: it assumes direct human scope, mandatory commit, and
  same-session review.
- `resolving-merge-conflicts` as written: "always resolve; never abort" is not
  safe automation policy.
- `strat-live-solo-orchestrator`: canonical orchestration now uses `run-task`
  plus Python validation.

## Missing Harness Skills

These jobs are specific enough to author rather than search for generically:

- `implement-task`
- `debug-task`
- `review-task`
- `evaluate-task`
- `refresh-context`
- `record-evidence`
- `raise-decision`
- `cleanup-task`
- Talk-owned `to-prd` and `to-issues`

External catalogs remain useful for optional domain skills such as security,
browser testing, deployment, and framework expertise. Project Init should
propose those per Project; they should not enter the harness-core bundle.

A generic `evaluate-skill` workflow is not required for v1. Talk and the human
own promotion. The Evaluation role itself has a separate fixed release baseline
because a weak pass gate can invalidate every Run.

## Runner Boundary

The default Codex Task root needs one orchestration skill: `run-task`.

Codex natively spawns and manages child agent threads. The skill teaches the
root the harness protocol and its limits. Python still validates every stage,
selects the exact role grant, and commits state. The root never performs a
canonical role, modifies code, or decides pass.
