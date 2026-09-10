# Matt-Style Skill Notes

## Patterns

- Start with the job, not a taxonomy.
- Choose model- or user-invocation before writing the body.
- Make cross-skill calls explicit and only target model-invoked skills.
- Use one strong sentence to name the principle.
- Make the main path obvious.
- Require concrete artifacts before handoff.
- Prefer "read these first" over "understand everything".
- Add a refusal only when the common wrong move corrupts the work.
- Use fresh sessions when review independence matters.
- Keep the skill shorter than the problem, but long enough to change behavior.

The detailed invocation and composition rules live in
[Matt system](matt-system.md).

## Useful Moves

### Grill

Keep asking until the artifact is safe to confirm. If blocking questions
remain, keep a draft and ask the next question.

### Run

Read the granted context. Produce the owned artifact. Return evidence and
unresolved decisions. Never take the next role's authority.

### Review

Lead with findings. Ground claims in code, tests, contracts, and docs. Keep
spec completeness separate from style or standards.

## Tone

Good:

```text
Do not confirm a Task while blocking grillables remain.
Keep the draft and ask the next question.
```

Weak:

```text
It may be helpful to consider whether additional questions remain.
```
