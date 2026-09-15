---
name: fafo-verify
description: Assess whether implemented behaviour satisfies its intended outcome and choose focused evidence when generated tests, a green suite, or a happy-path demo provide insufficient confidence.
---

# Verify

Challenge consequential claims about the system. Test volume and execution order are not measures of confidence.

## Establish what would count as correct

Identify the outcome or invariant being claimed and where its expected result comes from: a user-grounded example, domain rule, external contract, independently worked calculation, or trusted reference implementation.

An observed output can document existing behaviour without proving that behaviour is desirable. A snapshot records an observation. A test that reproduces the implementation's calculation may reproduce its mistake. Another model's agreement is not an independent source of truth.

If correctness depends on an unresolved product decision, make that uncertainty explicit and ask the narrow question needed. Do not invent the expectation merely to complete a test.

## Choose evidence that could expose the failure

Inspect existing checks before adding more. Select checks for plausible defects and their consequences:

- Exercise a steel thread through real components to demonstrate integration. State where a fake or unavailable dependency limits the claim.
- Use focused examples or property checks for subtle logic and invariants; include representative cases so a weak property cannot pass a useless implementation.
- Use a regression reproduction for a known defect. When practical, establish that the check detects the old behaviour.
- Exercise relevant rejection, retry, partial-failure, or concurrency conditions when they threaten the intended outcome. Choose from the actual flow rather than expanding a generic checklist.
- Use direct inspection or manual interaction where the claim concerns something automation cannot adequately establish.

Prefer a layer that can expose the defect reliably with low maintenance cost. Public boundaries often preserve refactoring freedom; a narrowly scoped internal check can be appropriate when it captures important complexity more directly. Do not mock away the very behaviour being verified.

## Keep durable evidence economical

Before retaining a new test, identify the failure it detects and why existing evidence does not cover it adequately. Keep reusable regression protection for meaningful risks. One-off observations can remain brief findings when permanent machinery adds little value.

Neither a fixed test quota nor a blanket ban on tests fits every change. Preserve useful existing coverage. Propose redundant-test removal only after inspecting what would be lost and within the user's scope.

Report what ran, what was observed, and what remains unverified. Do not call a designed check a passed check, or a simulated integration a verified real integration. Stop expanding verification when consequential claims have proportionate evidence and no unresolved failure justifies another check.
