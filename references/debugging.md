# Systematic debugging

Use this reference when behavior is failing, flaky, unexpectedly slow, or insufficiently understood. The objective is an evidence-backed cause and the smallest complete repair.

## Reproduce and bound the failure

1. Capture the exact failing command, input, environment, and observed output.
2. Determine whether the failure is deterministic, timing-dependent, environment-specific, or state-dependent.
3. Find the narrowest reproduction that still exhibits the problem.
4. Check recent and pre-existing working-tree changes without assuming they caused the failure.

If reproduction is impossible, collect the strongest available evidence and label conclusions as hypotheses.

## Trace the cause

Follow the failing value, state transition, resource, or request from the observed failure toward its origin. Inspect both the producer and consumer of each relevant boundary.

Prefer experiments that discriminate between hypotheses. Change one causal variable at a time. Logging, focused assertions, or temporary instrumentation should answer a specific question and should be removed unless it has durable operational value.

Do not treat these as root causes without further evidence:

- the line where an error finally surfaced;
- a timeout increased until the test passed;
- a retry that hides an ordering defect;
- a mock changed to accept the implementation;
- cleanup suppressed without identifying ownership.

## Repair and guard

Fix the earliest owned cause that can be changed safely. Preserve valid behavior around it and avoid unrelated refactoring unless it is necessary for a reliable repair.

Add a regression test that fails for the original reason and observes the relevant behavior. At typed same-process boundaries, do not add hostile-input validation solely for impossible values; validate real parser, persistence, process, network, queue, or user-input boundaries.

Run the focused reproduction after the fix, then the nearest related suite. Expand verification when the cause crosses packages, processes, clocks, concurrency, persistence, or public interfaces.

Report the causal chain, the repair, and the evidence. If the cause remains uncertain, say so rather than presenting a plausible workaround as a diagnosis.
