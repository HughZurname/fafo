# Behavioural evaluation

These cases still need to be run. Structural checks can catch packaging problems, but they cannot tell us whether a skill helps an agent make better decisions.

Use a fresh session with only the relevant skill and a small, disposable fixture. Give the agent the request and raw project evidence; keep the assessment criteria separate from its task. Observe actions and artifacts rather than asking it to grade its own compliance. Do not allow live external mutations during an evaluation.

## Cases

| Case and request | Useful observable behaviour | Failure signal |
| --- | --- | --- |
| Clear change: “Change this button label to Save draft.” | Direct scoped edit, proportionate visual or source verification | Mandatory interview, architecture note, or new testing infrastructure |
| Emerging intent: “Make duplicate uploads sensible.” | Asks about the consequential distinction; inspects technical facts | Invents a policy or asks the user questions answered by the code |
| Unknown dependency: “Find out whether retrying this local endpoint duplicates an item.” | Reproducible experiment and conclusion limited to the exercised conditions | Builds a replacement endpoint or mocks away the uncertain behaviour |
| Wrong oracle: code and tests both round each item before summing, but the supplied business examples round the total | Finds the disagreement with the independently supplied examples | Reports correctness solely because existing tests pass |
| Weak property: a broken sort returns an empty array and passes an idempotence test | Checks meaningful output, including preservation of input elements | Accepts idempotence alone as proof of sorting |
| Real boundary: mocks pass, but a supplied local storage fixture violates concurrent retry expectations | Exercises the actual fixture and reports the exposed failure | Claims integration correctness from the mocks |
| Handoff: “Implement using these findings,” with one clearly marked uncertain storage assumption | Retains uncertainty and probes it when it becomes consequential | Treats the entire handoff as an immutable specification |
| Existing good suite: “Simplify this module,” with several tests covering distinct regressions | Preserves distinct failure protection while reducing real duplication | Deletes tests to achieve a smaller count |
| User preference: “Use test-first for this parser change.” | Follows the requested approach with meaningful examples | Refuses because FAFO supposedly bans TDD |
| Exploration is over: an experiment has answered the question and implementation was authorised | Continues to implementation and verification | Stops to request another process approval or writes an unnecessary specification |
| Discussion only: “Help me reason about this API; don't change anything yet.” | Clarifies and reports findings within the requested scope | Starts implementation because a next action is clear |

## Keep a record of the run

For a run, keep the model and host, skill revision, user request, fixture, observed outcome, and the relevant artifacts. Note whether an assessor inspected the result and whether the evidence is reproducible.

Compare with a baseline session when practical. Useful observations include consequential assumptions exposed, distinct defects detected, user interruptions, unnecessary artifacts, and whether required behaviour was preserved. Token counts are useful only if measured by the host, with comparable task conditions.

When a run exposes a problem, change the relevant instruction and try the case again. Avoid adding rules for failures nobody has observed.

## Initial package checks

The first draft is reviewed for scope, selective discovery, optional companions, revisable assumptions, independent expected results, and truthful reporting. Each skill is also checked with the skill-creator frontmatter validator. Neither check substitutes for the behavioural runs above.
