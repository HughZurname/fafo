---
name: fafo-explore
description: Resolve a concrete technical or product uncertainty with a REPL, small experiment, or prototype when behaviour or solution shape is not yet understood. Use for learning through execution rather than routine implementation.
---

# Explore

Produce useful knowledge at low cost. The experiment may change what you think the problem is.

## Make the uncertainty observable

Identify what is unknown and which observation would change the next decision. Prefer inspecting or exercising existing code before constructing a substitute.

Choose the cheapest adequate instrument: a REPL call, a tiny script, an API request against a permitted environment, a UI sketch, or a narrow integration slice. Use representative inputs. A prototype with fake storage cannot establish persistence or concurrency behaviour.

Keep the experiment bounded by a question and a reasonable effort limit. Use scratch resources for destructive trials. New spending, external publication, or production mutation is not authorised merely because the work is exploratory.

Make the relevant state and failures observable. Compare the result with the expectation; distinguish what happened from the proposed explanation. If several explanations remain, choose an experiment that distinguishes them rather than repeating the same probe.

## Turn observation into understanding

Observed behaviour is evidence about what happens, not automatically a requirement. Check an unexpected result against user intent or the relevant contract before preserving it as expected behaviour.

Tests and brief specifications are available instruments when helpful. Do not build permanent scaffolding for a transient question or ban a useful test because this is exploration.

Stop when the next implementation decision is justified, when the hypothesis is ruled out, or when further work requires unavailable evidence. State the remaining uncertainty instead of presenting repeated experimentation as progress.

Preserve the conclusion and the smallest useful reproduction. Keep a scratch artifact only if it aids reproduction or future decisions. If reusing prototype code in the product, inspect its assumptions and shortcuts first.

Continue authorised implementation when ready. Hand off the observation, its limits, and the next useful action when another session or person will continue; no mandatory specification phase is needed.
