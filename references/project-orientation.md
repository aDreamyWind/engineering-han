# Project orientation

Use this reference before substantial work in an unfamiliar repository or when the relevant subsystem is unclear.

## Establish local authority

1. Locate instruction files that apply from the repository root to the target files, including `AGENTS.md` and equivalent project guidance.
2. Read the root overview, architecture documentation, and the nearest package or subsystem README relevant to the request.
3. Inspect the working tree before editing. Separate pre-existing changes from work required by the request.

## Map the project

Determine only what the current task needs:

- language, runtime, package manager, and workspace layout;
- source, test, generated, vendored, and documentation areas;
- public entry points and likely consumers;
- build, test, lint, type, formatting, documentation, and release commands;
- generated-file ownership and whether a generator must be used;
- compatibility, migration, persistence, or deployment requirements.

Infer commands from repository-owned configuration and documentation rather than assuming familiar defaults. When documents conflict with executable configuration, investigate which source is current before acting.

## Trace the requested surface

Search from the user-visible or public entry point toward its implementation and consumers. Read focused call sites, types, tests, and documentation. Avoid scanning the entire repository when a narrower dependency path answers the question.

Before implementation, be able to state:

- where the current behavior is owned;
- which consumers or persisted representations can be affected;
- which repository rules govern the change;
- which evidence can demonstrate success.

Keep this orientation in the conversation unless the repository lacks durable documentation that future contributors genuinely need.
