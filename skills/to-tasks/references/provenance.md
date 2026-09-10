# Provenance

## Local Decisions

Talk decisions on 2026-08-21 define a generalized pure splitter. It may split
any node in a nested task tree, returns only that node's flat ordered list of
immediate children, and is reapplied recursively when another level is needed.
If execution invalidates a split, the next invocation recomputes the entire
immediate list from the updated whole tree. Smallness uses hard semantic
conditions only; no numerical benchmark is required.

Earlier Harness ADRs were researched as prior art, but the skill does not
encode Harness Task ontology, Center materialization, role authority,
validation, scheduling, or closure transitions.

## Upstream Inspiration

The tracer-bullet, fresh-context, and immediate blocking-edge concepts were adapted from
`mattpocock/skills` `skills/engineering/to-tickets/SKILL.md` at revision
`5b15a47f2d7150f545fbcacbfe381787fc0230dc`. The upstream MIT license is in
`UPSTREAM-LICENSE.txt`. No tracker publication or interactive approval flow was
copied.

## Research Inputs

- METR, *Measuring AI Ability to Complete Long Software Tasks* (2025): task
  duration is a capability signal, not a universal boundary.
- Anthropic, *Building Effective Agents* (2024): clean decomposition plus
  programmatic gates can trade latency for accuracy.
- OpenAI, *Harness engineering: leveraging Codex in an agent-first world*
  (2026): construct larger goals depth-first from smaller enforceable blocks
  and keep repository context legible.
- Xia et al., *Agentless* (2024): localization, repair, and validation show the
  value of simple staged boundaries.
- Asthana et al., *Runtime-Structured Task Decomposition for Agentic Coding
  Systems* (2026): deterministic branching and selective retry outperform
  static decomposition alone in the reported workloads.
- Mehtiyev and Assunção, *Beyond Resolution Rates* (2026): patch size alone
  does not capture architectural difficulty.

Research informed the semantic boundary. The skill intentionally contains no
empirical threshold, benchmark requirement, or orchestration design.
