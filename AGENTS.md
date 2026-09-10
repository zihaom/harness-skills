# AGENTS.md

This repository owns reusable harness skills, not harness runtime code.

## Authoring

- Use the official `skill-creator` and `matt-skill-creation`.
- Assume the model is capable. Add only instructions that change behavior.
- Keep one job and one owner per skill.
- Preserve strategic freedom; constrain fragile mechanics and artifact shapes.
- Put deterministic enforcement in scripts or harness Python, not prose.
- Do not import overlapping workflow skills into the same role bundle.

## Automation

Every Run-facing skill must define:

- owner role
- required inputs
- artifact output
- allowed side effects
- refusal or handoff conditions
- completion evidence

Run-facing skills must not pause for conversational approval. Missing human
judgment becomes a typed Human Decision Gate request.

## Validation

Validate every changed skill with OpenAI's `quick_validate.py`. Global
promotion requires a Talk record and human confirmation. Use realistic
role/model rehearsals when the approved release plan names fragile behavior to
verify; do not make a generic no-skill benchmark an automatic authority.

The Evaluation release is stricter: its fixed local adversarial baseline must
pass before activation and after every profile, skill, rubric, or schema change.

