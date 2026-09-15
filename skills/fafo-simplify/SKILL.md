---
name: fafo-simplify
description: Reduce demonstrated complexity in code, tests, or development artifacts while preserving required behaviour. Use for a requested simplification or when accumulated machinery obstructs the current change.
---

# Simplify

Reduce the cost of understanding and changing the system. Fewer lines are useful only when the result is clearer and still correct.

## Understand what the machinery buys

Trace the behaviour and callers before removing or combining anything. Identify the actual burden: duplicated logic, unnecessary indirection, redundant checks, speculative configuration, or records that no longer communicate a useful decision.

Consider existing helpers, language and platform features, and installed dependencies before custom machinery. Choose the simplest adequate option for the real requirements. An extra dependency may reduce local code while increasing operational or maintenance cost.

Do not replace a requested feature with a smaller feature. Challenge a questionable requirement openly; preserve it unless the user agrees to a changed outcome.

## Make a scoped reduction

Consolidate duplicated responsibilities and remove demonstrated dead or speculative structure within the authorised scope. Prefer readable code over compressed expressions. Keep abstractions that explain real domain boundaries or isolate meaningful change.

For tests, compare their failure-detection roles before merging or removing them. A large suite is not automatically wasteful, and a rarely failing test may protect a severe failure. Preserve distinct risks and independent expectations.

For documentation, preserve decisions and reproduction details that future work needs. Avoid creating a new tracking system to administer every simplification.

Retain safeguards, data integrity, accessibility, and explicit compatibility constraints. If a proposed simplification introduces a real limit, explain it where maintainers need it; do not add ritual annotations to ordinary code.

Run checks appropriate to the affected behaviour. Report the concrete burden removed and the evidence that required behaviour remains. Do not invent token savings or productivity metrics. Finish when the scoped burden is reduced; do not expand a local cleanup into a repository-wide audit.
