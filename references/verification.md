# Verification before completion

Use this reference before claiming an implementation, repair, or refactor is complete.

## Inspect the actual change

Review the working-tree diff and status. Confirm that the diff contains the intended behavior, all required consumers, tests, and documentation, while excluding unrelated edits and accidental artifacts.

## Select evidence by surface

Derive commands from project-owned instructions and configuration. Choose the smallest set that covers the changed behavior:

- focused unit or component tests for local logic;
- integration tests for interactions across owned components;
- end-to-end or recorded scenarios for user-, protocol-, or model-visible behavior;
- type and static checks for interface changes;
- build or package smoke tests for published/runtime entry points;
- migration or compatibility tests for persisted and external formats;
- documentation checks for generated, linked, bilingual, or compiled docs.

Do not run an exhaustive suite by habit when focused evidence is sufficient. Do not omit a broader check when coupling makes focused evidence insufficient.

## Respond to failures

Treat a failing check as evidence to investigate. Do not weaken tests, suppress errors, regenerate expectations, or bypass product protections merely to obtain a pass. If a failure is unrelated and demonstrably pre-existing, record the evidence and keep it distinct from the requested work.

When the environment prevents a required check, try safe project-supported alternatives. Report the limitation and what remains unverified; do not translate inability to run a command into success.

## Report truthfully

List only commands actually run, with their outcomes. Distinguish:

- passed;
- failed because of the change;
- failed for a demonstrated unrelated reason;
- skipped because it was irrelevant;
- not run because of an environmental or authorization constraint.

Completion requires the requested outcome and proportionate evidence, not merely a clean-looking diff.
