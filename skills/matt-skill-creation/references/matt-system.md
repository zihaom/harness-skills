# Matt Skill-System Fit

Use this reference when the model-invoked `writing-for-agents` skill is not
available.

## Invocation Axis

A model-invoked skill is discoverable by agents and humans. Its description is
an always-loaded context pointer, so it earns that load only when autonomous
discovery or cross-skill composition is required.

A user-invoked skill is reachable only by the human. Pair
`disable-model-invocation: true` with
`policy.allow_implicit_invocation: false` in `agents/openai.yaml`. Other skills
cannot call it.

## Composition

- Express an operative dependency as `Call the Skill tool with "<name>"`.
- Make one Skill-tool call per model-invoked target.
- Tell the human to invoke a user-invoked prerequisite.
- Put shared passive knowledge in a plain reference rather than an invocable
  skill.
- Keep the caller responsible for its own artifact. A dependency supplies one
  bounded capability; it does not inherit the caller's role or authority.

## Information Shape

- Keep ordered actions in `SKILL.md` and end each with a checkable completion
  criterion.
- Disclose branch-only reference behind a one-level context pointer.
- Use one leading word for a repeated behavioral idea instead of repeating its
  definition.
- Remove environment facts that an agent can cheaply inspect; duplicated facts
  become stale caches.

## Provenance

Adapted from `mattpocock/skills` revision
`5b15a47f2d7150f545fbcacbfe381787fc0230dc`, especially
`skills/productivity/writing-for-agents/` and `.agents/invocation.md`.
