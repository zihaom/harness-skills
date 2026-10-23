# Upstream Provenance

Reviewed on 2026-10-23.

| Source | Revision | Use |
|---|---|---|
| `openai/skills` | `49f948faa9258a0c61caceaf225e179651397431` | Official skill structure, validation, and catalog review |
| `mattpocock/skills` | `5beb35b040e3de97e54fa9e386d7e42d15c295c2` | Concise workflow patterns, invocation mechanics, and candidate ideas |
| `DietrichGebert/ponytail` | `09c434ab73ca43761c5d8b0c5d341926c2fba710` | YAGNI/minimal-solution discipline and over-engineering review references |
| `obra/superpowers` | `d884ae04edebef577e82ff7c4e143debd0bbec99` | Overlap audit and verification/review ideas |
| `lennney/stop-that-shit` | `8bc1ac558167121e7f28d9fb0bec05c039952206` | Scope-discipline and `stss` writing references; inert upstream, no Guard or hooks activated |
| `ayghri/i-have-adhd` | `1ecea1993b7fce257ffbd686c070948b5e07eda6` | ADHD-friendly output-style reference; inert upstream, no role-bundle activation |
| `wondelai/skills` (`code-quality` adaptation) | `dd37ee506ff558e939b3d421557987cced49b866` | `clean-code` v1.4.0 adapted into `code-quality` |
| `wondelai/skills` (six craftsmanship skills) | `c172996495bed0fcd26896a9416b2093fd7073f0` | Current publisher sources for the six skills in `upstreams/volc-strat-prod-code-craftsmanship/` |
| strat-live harness prototype | unversioned server snapshot, 2026-07-23 | Migration input only |
| `volc-strat-prod:/root/workspace/harness/.agents/skills/engineering/code-craftsmanship` | unversioned worker snapshot captured 2026-08-10; tree digest `41f4d2f1bbcf4ffe7335b4fe22b9050706e4da8a690f107d2b7aec04fdc5f67f` | Historical craftsmanship capture, refreshed from its publisher on 2026-10-23 |

No upstream workflow skill is active merely because it was reviewed. Imported
or adapted content must record its license and exact source in the skill
directory before release.

The six craftsmanship skills remain at
`upstreams/volc-strat-prod-code-craftsmanship/`, retaining the original capture's
directory name. The original worker source was not a Git checkout; its host,
path, date, and digest above identify that historical capture. On 2026-10-23,
all six packages were refreshed from the matching skill directories in
`wondelai/skills` at the publisher revision above, including support files.
They retain the publisher's MIT license and metadata. They are not cataloged,
released, activated, or approved for a Run role bundle.

See [the 2026-10-23 Talk record](history/2026-10-23-upstream-refresh-and-andrew-ng.md)
for the upstream refresh and Andrew Ng skill request.

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
