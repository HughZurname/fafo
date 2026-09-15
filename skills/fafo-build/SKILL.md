---
name: fafo-build
description: Implement a coherent product increment from emerging understanding, especially a working path through the system, while allowing evidence to revise the design. Use when the outcome is sufficiently clear to build.
---

# Build

Deliver the requested behaviour with a structure someone can understand and change. Requirements can become clearer while implementation proceeds.

## Start from the real flow

Inspect the relevant entry point, dependencies, state changes, and observable result. Reuse existing capabilities and conventions. Resolve essential product ambiguity; make ordinary reversible implementation choices yourself.

For a new capability, establish a steel thread: a narrow but real path from an initiating action through the necessary components to a useful observable result. For an existing feature or small fix, extend or repair its current flow rather than creating another demonstration.

Prefer existing helpers, standard libraries, platform capabilities, and installed dependencies when they fit. Minimise total complexity rather than line count. Preserve required error handling, accessibility, security, and data integrity.

## Let implementation teach you

Keep the increment coherent enough to exercise. Add structure when actual responsibilities or repeated use justify it. Do not build speculative extension points or force every increment into one-test/one-function units.

If a dependency or domain assumption proves wrong, pause only the dependent work, obtain the missing evidence, and revise the approach. Involve the user when the desired outcome or a consequential tradeoff changes. Do not silently lower the requirement to fit the implementation.

Choose the order of code and checks based on the uncertainty. An existing failing regression can be the best starting point; an unfamiliar interaction may require a probe first. Preserve meaningful checks and follow actual project requirements.

## Finish the useful increment

Exercise the user-visible result and consequential failure conditions. A working happy path alone is insufficient when retries, partial failure, permissions, or state transitions materially affect the outcome.

Replace temporary shortcuts that would invalidate the requested behaviour. Leave explicit, relevant limits when something remains outside scope. Refactor when the current structure obstructs the work; do not defer all design improvement to a later ceremony.

Report the behaviour delivered, evidence actually obtained, and material limitations. Continue the authorised task to completion rather than stopping after a successful prototype. For a genuine handoff, include reproduction and remaining assumptions without producing an exhaustive specification.
