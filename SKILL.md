---
name: engineering-han
description: Apply Han's lightweight, evidence-driven engineering workflow across software projects. Use for non-trivial feature work, refactoring, debugging, code review, or completion verification that should respect repository-local instructions and avoid unnecessary specification ceremony. Skip simple explanations and tiny mechanical edits unless explicitly invoked.
---

# Engineering Han

Deliver the requested software outcome with the smallest process that still makes the result understandable, reviewable, and verifiable.

## Authority and scope

1. Preserve the user's stated outcome, scope, and authorization limits.
2. Read every applicable repository instruction file before changing code. Project-local rules override this skill's defaults.
3. Treat existing user changes as owned work. Do not discard, rewrite, or broaden them without explicit approval.
4. Prefer existing architecture, dependencies, patterns, and commands unless the task requires changing them.
5. Do not create planning artifacts merely to demonstrate process. Create durable prose only when it will remain useful after the change lands.

## Select the working mode

Read only the references needed for the current request:

- For entering an unfamiliar repository, read [references/project-orientation.md](references/project-orientation.md).
- For features, behavioral changes, or refactors, read [references/change-workflow.md](references/change-workflow.md).
- For defects, regressions, or unexplained failures, read [references/debugging.md](references/debugging.md).
- For reviewing a diff, branch, or pull request, read [references/code-review.md](references/code-review.md).
- Before claiming implementation work is complete, read [references/verification.md](references/verification.md).
- After substantial work, read [references/knowledge-harvest.md](references/knowledge-harvest.md) only when the result may contain reusable project knowledge.
- When establishing this workflow in a repository, read [references/project-adapter.md](references/project-adapter.md).

Combine modes when the request genuinely spans them. Do not load every reference by default.

## Calibrate process to risk

Use the lightest treatment that covers the actual risk:

- **Low risk:** localized, reversible, mechanically checkable changes. Inspect, edit, and run focused checks without a written plan.
- **Medium risk:** behavior crosses files or consumers, requirements contain ambiguity, or regressions would be costly. State a short change brief in the conversation before implementation.
- **High risk:** public interfaces, persisted data, security, concurrency, lifecycle behavior, migrations, or broad architectural changes. Identify invariants, affected consumers, rollback or migration needs, and verification evidence before implementation. Persist a design record only when the rationale will guide future work.

A short change brief contains only what changes decisions: goal, non-goals, constraints, affected surfaces, acceptance conditions, and verification. Revise it when implementation reveals that the intended outcome or approach is wrong.

## Evidence rules

- Inspect before editing and distinguish observed facts from assumptions.
- Diagnose causes before fixing symptoms.
- Update every in-scope consumer of a changed interface.
- Match tests and documentation to externally observable behavior and durable contracts.
- Run the smallest relevant verification set; expand it when failures or coupling justify doing so.
- Report commands actually run and their outcomes. Never imply that an unrun check passed.
- Stop and request direction when completion needs materially broader scope, new authority, or a product decision the user has not made.

## Completion

Conclude with the outcome, important implementation or design choices, verification evidence, and any unresolved risk. Keep process narration secondary to what changed and what was established.
