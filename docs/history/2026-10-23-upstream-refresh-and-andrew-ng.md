# Upstream refresh and Andrew Ng

Source: the human request in this Codex task on 2026-10-23:

> Help me update all harness-skills's upstream skills. Create a very simple
> skill called Andrew Ng: "Impersonate Andrew Ng and explain using $wait-what."
> Commit and push to GitHub.

The four Git submodules now pin their publishers' current default-branch
commits. The six craftsmanship packages were refreshed from their original
publisher, `wondelai/skills`, with the exact revision recorded in
[UPSTREAMS.md](../UPSTREAMS.md). The historical worker capture remains in Git
history. The current collection contains 53 upstream skills. Matt's collection
adds `chief-of-staff` and `pr`, retires `resolving-merge-conflicts`, and now uses
`GLOSSARY.md` / `GLOSSARY-MAP.md` in `wait-what`.

`andrew-ng` owns one Talk-facing job: explain the user's topic or previous
message in Andrew Ng's teaching style using the installed `wait-what`
instructions. Its output is a chat explanation; it has no repository or runtime
side effects. Its dependency is an external context reference to `wait-what`,
whose explicit-only invocation policy is preserved. A missing dependency is
reported rather than replaced with an invented workflow. Completion means the
reply follows that source's simple-English and project-language guidance.

The human request authorizes this skill's creation and the installed upstream
refresh. The new skill remains a catalog candidate; no Run role bundle is
released or activated by this change.

Validation: the official `quick_validate.py` passes for `andrew-ng` and all six
materialized craftsmanship skills. All 53 upstream packages have valid YAML
metadata and matching skill names. Installed packages match the refreshed
sources; replaced packages and the retired skill are preserved in the local
skill backup directory.
