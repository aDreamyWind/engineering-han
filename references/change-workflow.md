# Change workflow

Use this reference for features, behavioral changes, API changes, and refactors. For a defect with an unknown cause, use `debugging.md` first.

## Define the outcome

Translate the request into observable acceptance conditions. Resolve only ambiguities that materially change the result; otherwise make a conservative assumption and state it.

For medium- or high-risk changes, use a compact change brief in the conversation:

```markdown
Goal:
Non-goals:
Constraints:
Affected surfaces:
Acceptance conditions:
Verification:
```

Do not persist this brief by default. Store durable rationale in the repository's established decision-record format only when future work will depend on it.

## Design the smallest complete change

1. Identify the owning module and every in-scope consumer.
2. Prefer an existing extension point or abstraction over adding a parallel path.
3. Distinguish required behavior from optional cleanup.
4. Include migrations, compatibility handling, documentation, generated artifacts, and user-facing presentation when the changed surface requires them.
5. Decide the meaningful verification tiers before editing.

Avoid speculative generalization. Extract an abstraction when current duplication or variation demonstrates the need, not merely because another implementation might exist later.

## Implement coherently

- Keep the diff focused on the requested outcome.
- Update interface definitions and consumers together.
- Preserve local error, lifecycle, resource-ownership, and teardown patterns.
- Add or update tests around observable behavior and important failure paths.
- Update current-state documentation and public API comments with the code.
- Use repository generators for generated files and avoid hand-editing their outputs unless the project explicitly permits it.

When implementation invalidates the brief, update the intended outcome or approach before continuing. Do not quietly ship a different feature because it was easier to implement.

## Hand off to verification

Inspect the completed diff for missing consumers, unrelated changes, stale prose, and accidental generated output. Then follow `verification.md` before claiming completion.
