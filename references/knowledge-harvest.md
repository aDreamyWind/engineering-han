# Knowledge harvest

Use this reference after substantial work when the result may contain knowledge worth preserving. Most changes should not create a new process document or modify this skill.

## Classify what was learned

- **Project fact:** current commands, ownership, configuration, or architecture. Update the project's current-state documentation.
- **Durable decision:** a chosen trade-off whose alternatives or consequences will guide future work. Use the project's decision-record mechanism.
- **Mechanical invariant:** a rule that can be checked deterministically. Prefer a test, lint rule, schema, type, or validation script over prose.
- **Reusable workflow:** a repeated decision process that applies across projects. Consider updating this skill only after more than one real use demonstrates the pattern.
- **One-off implementation detail:** leave it in code, tests, commit history, or the final report; do not create durable documentation.

## Preserve selectively

Record information in one authoritative location. Remove or update superseded guidance rather than adding a competing rule. State current behavior directly; avoid preserving debugging transcripts, review conversation, temporary plans, or narrative about how the change evolved.

Do not universalize a project-specific convention. Before changing `engineering-han`, verify that the guidance changes decisions across different stacks and repositories and does not conflict with project-local authority.
