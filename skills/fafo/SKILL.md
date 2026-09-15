---
name: fafo
description: Guide exploratory product development when the user asks for FAFO or needs to move between discovery and implementation as requirements emerge. Use a focused companion skill for a single known activity.
---

# FAFO

Choose an action that answers the question holding up the work or moves the product forward. Revise the approach as you learn.

## Orient briefly

Establish what the user wants, how the relevant code behaves now, and what is still unclear. Inspect available evidence before asking the user for facts. A clear, bounded request can go straight to implementation.

Treat assumptions as provisional. Distinguish a user requirement from an implementation guess and an observation from an explanation. Change the approach when evidence warrants it. Involve the user if that would change the outcome they asked for.

## Choose a useful mode

Move between these activities as needed and read only the guidance that helps now:

- Clarify: a product decision or conflicting expectation blocks progress. If installed, use `fafo-clarify`.
- Explore: behaviour, feasibility, or interface shape is uncertain. If installed, use `fafo-explore`.
- Build: enough is understood to deliver a useful increment. If installed, use `fafo-build`.
- Verify: a claim about the result needs evidence. If installed, use `fafo-verify`.
- Simplify: unnecessary code, tests, or process makes the result harder to understand. If installed, use `fafo-simplify`.

Companion skills are optional. Without them, perform the relevant activity directly: ask the consequential question, run a discriminating experiment, implement the useful path, challenge the claim, or remove demonstrated duplication. Do not require an installation or load the whole family.

## Keep the work moving

Use a visual when seeing a flow, state change, or alternative would help the user decide. Prefer an in-conversation diagram for a static relationship or a native interactive surface when changing an input would teach something. Check what the current host can render; fall back to a table or text sketch. A visual is optional and does not require a separate report or approval round. Label observed behaviour, assumptions, and proposals so a polished diagram cannot make a guess look established.

When the user explicitly asks to see a visual, render it on an available user-visible surface. Merely creating a file or describing the intended diagram does not satisfy that request. If the requested format is unavailable, explain that and show the clearest supported alternative.

Take a small enough step to understand its result. Reuse existing code and tools. A test, sketch, REPL session, short note, or prototype can each be the right instrument. Neither test-first nor test-after is mandatory.

When exploration settles the immediate uncertainty, continue authorised implementation. Revisit discovery when implementation exposes a consequential unknown. Do not manufacture an approval step between modes or automatically launch another task.

For a handoff, preserve only what the next worker needs: current outcome, evidence and how to reproduce it, decisions and their reasons, consequential unknowns, and the next useful action. Omit empty categories. Use the conversation or existing project record; create a document only when persistence or collaboration warrants one. A handoff records current understanding and grants no new permissions.

## Evidence and scope

Someone will have to understand and maintain what you generate. Keep tests that detect identifiable failures. Documents should preserve decisions worth remembering; abstractions should explain responsibilities the code already has. Do not impose quotas on tests, questions, files, or phases.

Code and tests can share a mistaken assumption. Ground expected results in user intent, independent examples, domain rules, or external contracts. Exercise the important behaviour across real boundaries where practical, and report which boundaries were simulated.

Scale verification to consequences and uncertainty. Preserve safeguards and explicit requirements. Experiments stay within authorised environments and side effects. Report actual observations and remaining limitations; passing checks do not prove the product is right.
