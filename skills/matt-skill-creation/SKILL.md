---
name: matt-skill-creation
description: Create or revise concise engineering skills that fit the Matt Pocock skill system. Use when choosing model- versus user-invocation, composing model-invoked skills, or authoring harness, project, entrypoint, and workflow skills with sharp boundaries and automation-ready artifacts.
---

# Matt Skill Creation

Write skills like a strong engineering coach: concise, concrete, composable,
and useful under pressure.

Call the Skill tool with "skill-creator" for structure and validation. When
`writing-for-agents` is available as a model-invoked skill, call the Skill tool
with "writing-for-agents" too. Otherwise read
[Matt system](references/matt-system.md). This skill adds Matt-system
composition and harness boundaries.

## Admission Test

Assume the model is already capable.

Create a skill only when it adds at least one of:

- a non-obvious repeatable procedure
- harness or project knowledge
- a tool protocol
- an artifact contract
- a guard against an observed failure

Generic programming advice is not a skill. Prefer project standards, tests, or
an evaluation rubric over a broad philosophy prompt.

## Shape

Every skill must answer:

1. What single job does it own?
2. Which role or surface owns it?
3. What must it read first?
4. What artifact does it produce?
5. What may it mutate?
6. When must it refuse or hand off?
7. What evidence proves completion?

If these answers overlap another skill, merge or narrow before writing.

## Invocation And Composition

Choose invocation before drafting:

- **Model-invoked** when an agent should discover the skill autonomously or
  another skill must call it. Keep a model-facing description with one trigger
  per branch. Omit `disable-model-invocation` and Codex's implicit-invocation
  denial.
- **User-invoked** when human judgment should be the only entrypoint. Set
  `disable-model-invocation: true`, keep the description human-facing, and set
  `policy.allow_implicit_invocation: false` in `agents/openai.yaml`.

Record every operative skill dependency. A skill may call only a
model-invoked skill, through one explicit Skill-tool call per target. A
user-invoked prerequisite becomes a human instruction or an external context
pointer; never pretend another skill can invoke it. Prefer a plain shared
reference when reusable material does not need an invocation of its own.

Check adjacent skill descriptions before adding a new model-invoked trigger.
Context load is justified only by an independent branch or a real composition
edge.

## Freedom

- Preserve high freedom for design, diagnosis, and code strategy.
- Use medium freedom for preferred workflows with contextual variation.
- Use scripts or Python for fragile, deterministic mechanics.

Do not encode scheduling, state transitions, leases, or permissions as prose.
The harness enforces those.

## Automation

For Run-facing skills:

- consume explicit Task, stage, and artifact inputs
- never ask the human directly
- emit a typed decision request when human judgment is required
- write the owned artifact before returning
- separate claims from evidence

Interactive questions belong to Talk-facing skills.

## Process

1. Name one job and one owner with a short verb-led name.
2. Map adjacent skills, choose the invocation axis, and record valid
   composition edges.
3. Initialize a new skill with the official `skill-creator` script.
4. Define inputs, artifact output, side effects, stop conditions, and exact
   completion evidence.
5. Write the shortest flow that changes behavior. End every step on a
   checkable completion criterion.
6. Move branch-only detail into one-level references and delete instructions
   the model already follows reliably.
7. Keep `SKILL.md`, `agents/openai.yaml`, bucket metadata, and dependency
   wording consistent with the chosen invocation axis.
8. Validate with the official skill validator and rehearse any fragile role or
   composition boundary named by the release plan.
9. Present the boundary and behavior through Talk. Require human approval
   before global promotion.

## Tests

A skill is not ready merely because its YAML parses.

Check:

- a fresh agent finds the right boundary
- model-invoked dependencies are reachable and user-invoked dependencies are
  never called by another skill
- `SKILL.md` and `agents/openai.yaml` agree on invocation policy
- a Run agent does not pause for conversational approval
- a strong model keeps useful strategic freedom
- a cheaper model still produces the required artifact
- the skill addresses its named risk without overriding Project judgment
- an adjacent skill does not trigger for the same job

Use realistic pressure-case rehearsal when the approved release plan requires
it. A no-skill comparison may inform Talk, but it does not decide promotion.
