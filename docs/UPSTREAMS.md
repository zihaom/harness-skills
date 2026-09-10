# Upstream Provenance

Reviewed on 2026-08-26.

| Source | Revision | Use |
|---|---|---|
| `openai/skills` | `49f948faa9258a0c61caceaf225e179651397431` | Official skill structure, validation, and catalog review |
| `mattpocock/skills` | `6654f6b60cd9d5be8b54c6fafe44346dabeb3b76` | Concise workflow patterns, invocation mechanics, and candidate ideas |
| `DietrichGebert/ponytail` | `2ed6c52c9d7e5e56942508591085fd45dea277d3` | YAGNI/minimal-solution discipline and over-engineering review references |
| `obra/superpowers` | `d884ae04edebef577e82ff7c4e143debd0bbec99` | Overlap audit and verification/review ideas |
| `lennney/stop-that-shit` | `d4b9db78063d595e65b0c163933a90c4c681d50d` | Scope-discipline and `stss` writing references; inert upstream, no Guard or hooks activated |
| `ayghri/i-have-adhd` | `ff690b6fbd3383e4fce6a7e50c7b409ca9a6a804` | ADHD-friendly output-style reference; inert upstream, no role-bundle activation |
| `wondelai/skills` | `dd37ee506ff558e939b3d421557987cced49b866` | `clean-code` v1.4.0 adapted into `code-quality` |
| strat-live harness prototype | unversioned server snapshot, 2026-07-23 | Migration input only |
| `volc-strat-prod:/root/workspace/harness/.agents/skills/engineering/code-craftsmanship` | unversioned worker snapshot captured 2026-08-10; tree digest `41f4d2f1bbcf4ffe7335b4fe22b9050706e4da8a690f107d2b7aec04fdc5f67f` | Talk-only architecture taste and reference material |

No upstream workflow skill is active merely because it was reviewed. Imported
or adapted content must record its license and exact source in the skill
directory before release.

The `volc-strat-prod` snapshot is stored unchanged at
`upstreams/volc-strat-prod-code-craftsmanship/`. Its source directory was not a
Git checkout, so the capture is identified by host, absolute source path,
capture date, and a digest of the sorted per-file SHA-256 manifest. The six
skills retain their MIT license and original Wondel.ai metadata in their own
front matter. They are not cataloged, released, activated, or approved for a
Run role bundle.

## 2026-09-10 upstream additions

Source: human instruction in Codex task
`01a08051-525c-72f1-9c48-28fcc2fabf9e`:

> help me add  [https://github.com/lennney/stop-that-shit](https://github.com/lennney/stop-that-shit)    , I-have-ADHD   to upstreams in my harness-skills, and use the github plugin to commit and push

Decision receipt: add the two repositories as pinned Git submodules under
`upstreams/`, following this repository's existing reference convention.
`I-have-ADHD` resolves to `ayghri/i-have-adhd`, the source installed in the
preceding conversation. These pins capture upstream HEAD on 2026-09-10;
the ADHD pin is newer than the previously installed local skill. Both retain
their upstream licenses. Addition does not install plugins, activate hooks,
update installed skills, or approve global promotion.
