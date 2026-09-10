# Hierarchical Wiki Shape

A strong project wiki is a reader path, not a file dump.

```text
docs/
  README.md
  project_map.md
  architecture/
    README.md
  <real subsystem>/
    README.md
  tests/
    README.md
  artifacts/
    README.md
  update_logs/
    README.md
```

Adapt names to the repository. Do not force another project's subsystem names
onto it.

- `docs/README.md`: navigation and truth policy.
- `project_map.md`: important directories, files, and entrypoints.
- `architecture/README.md`: system purpose, flow, ownership, and status.
- subsystem pages: owns, does not own, contracts, flow, and next pages.
- test pages: proof layers and their limits.
- artifact pages: generated, runtime, and environment material.
- update logs: volatile working material.

Use these labels whenever current and target differ:

```markdown
## Current Code Truth
## Target Architecture
## Migration Gap
```

