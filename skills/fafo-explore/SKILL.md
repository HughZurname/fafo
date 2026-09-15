---
name: fafo-explore
description: Resolve a concrete technical or product uncertainty with a REPL, small experiment, or prototype when behaviour or solution shape is not yet understood. Use for learning through execution rather than routine implementation.
---

# Explore

Use a small experiment to answer a question. Its result may change your understanding of the problem.

## Choose what to try

Identify what you need to learn and what result would change your next decision. Prefer inspecting or exercising existing code before constructing a substitute.

Choose the cheapest adequate instrument: a REPL call, a tiny script, an API request against a permitted environment, a UI sketch, or a narrow integration slice. Use representative inputs. A prototype with fake storage cannot establish persistence or concurrency behaviour.

Keep the experiment bounded by a question and a reasonable effort limit. Use scratch resources for destructive trials. New spending, external publication, or production mutation is not authorised merely because the work is exploratory.

Make the relevant state and failures observable. Compare the result with the expectation; distinguish what happened from the proposed explanation. If several explanations remain, choose an experiment that distinguishes them rather than repeating the same probe.

Show the behaviour when that helps the user reason about it. A sequence diagram can expose where a retry repeats work; a state diagram can show a transition the initial idea missed. Use the host's in-conversation display when available. Add interaction only when varying an input or stepping through events answers the question more clearly. A simulation illustrates its assumptions and does not count as evidence that the real system behaves the same way. Keep a text explanation of the finding, and update or discard a visual when its assumptions change.

An explicit request to see a visual requires visible output, not just a file path or description. Display the supported representation and explain any limitation of the requested format.

## Work out what the result means

An observation tells you what happened. Check whether that behaviour matches the requirement. Check an unexpected result against user intent or the relevant contract before preserving it as expected behaviour.

Tests and brief specifications are available instruments when helpful. Do not build permanent scaffolding for a transient question or ban a useful test because this is exploration.

Stop when the next implementation decision is justified, when the hypothesis is ruled out, or when further work requires unavailable evidence. State the remaining uncertainty instead of presenting repeated experimentation as progress.

Preserve the conclusion and the smallest useful reproduction. Keep a scratch artifact only if it aids reproduction or future decisions. If reusing prototype code in the product, inspect its assumptions and shortcuts first.

Continue authorised implementation when ready. Hand off the observation, its limits, and the next useful action when another session or person will continue; no mandatory specification phase is needed.
