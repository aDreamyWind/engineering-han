# Project adapter

Use this reference when adopting `engineering-han` in a repository. The skill intentionally has no framework-specific configuration file; repository-local instructions are the adapter.

Create or refine the project's normal instruction file, such as `AGENTS.md`. Keep it concise and link to authoritative documents instead of copying them.

A useful structure is:

```markdown
# Project overview

State the product purpose and repository layout briefly.

# Required reading

Link architecture, persistence, security, or subsystem documents that govern changes.

# Commands

List setup, focused test, type/static check, lint, build, documentation, and packaging commands. Explain when each command applies.

# Engineering rules

State project-specific invariants, extension points, compatibility promises, generated-file ownership, and migration rules.

# Change evidence

Map important change surfaces to required tests, snapshots, documentation, migrations, or runtime smokes.

# Completion

Define any project-specific requirement before commit, push, review, or release.
```

Put rules at the narrowest applicable directory when a monorepo contains substantially different subsystems. Keep global rules at the root. Prefer executable gates for mechanically checkable requirements.

Do not duplicate the generic workflows from this skill into every project. The adapter should answer only what is unique about that repository.
