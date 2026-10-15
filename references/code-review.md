# Code review

Use this reference to review a diff, branch, commit, or pull request. A review identifies actionable defects and material risks; it is not a narration of the implementation.

## Establish the review target

Confirm the intended base and changed range. Read applicable project instructions and inspect enough surrounding code to understand ownership, callers, and invariants. Review generated or vendored files according to their repository-specific process.

## Review by risk

Prioritize:

1. incorrect behavior and unmet requirements;
2. data loss, security, authorization, and privacy failures;
3. concurrency, cancellation, teardown, retry, and resource-lifecycle defects;
4. compatibility, migration, persistence, and public-interface breaks;
5. missing consumers or inconsistent parallel paths;
6. insufficient tests or verification for the changed behavior;
7. misleading documentation and diagnostics;
8. maintainability issues supported by concrete future cost.

Do not elevate personal style preferences when the repository permits the implementation. Do not request speculative abstractions or defensive checks at already typed, trusted boundaries.

## Require evidence

Each finding should include:

- the smallest relevant location;
- the concrete failing scenario or violated invariant;
- why existing handling or tests do not cover it;
- severity proportional to impact and likelihood.

Verify line numbers and current code before reporting. Avoid duplicate findings that share one root cause. If a concern depends on an unverified assumption, investigate it or label it explicitly.

Report findings first, ordered by severity. If there are no findings, say so and mention material verification gaps or residual risks without inventing issues.
