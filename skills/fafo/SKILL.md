---
name: fafo
description: Guide exploratory product development when the user asks for FAFO or needs to move between discovery and implementation as requirements emerge. Use a focused companion skill for a single known activity.
---

# FAFO

Choose the next action for the uncertainty it resolves and the outcome it advances. Preserve freedom to revise the solution as understanding improves.

## Orient briefly

Establish the intended outcome, relevant existing behaviour, and the uncertainty currently blocking useful progress. Inspect available evidence before asking the user for facts. A clear, bounded request can go straight to implementation.

Treat assumptions as provisional. Distinguish a user requirement from an implementation guess and an observation from an explanation. New evidence can change the approach; a change to the user's intended outcome needs their involvement.

## Choose a useful mode

These are capabilities, not sequential gates. Use only the guidance needed now:

- **Clarify:** a product decision or conflicting expectation blocks progress. If installed, use `fafo-clarify`.
- **Explore:** behaviour, feasibility, or interface shape is uncertain. If installed, use `fafo-explore`.
- **Build:** enough is understood to deliver a useful increment. If installed, use `fafo-build`.
- **Verify:** a claim about the result needs evidence. If installed, use `fafo-verify`.
- **Simplify:** unnecessary code, tests, or process makes the result harder to understand. If installed, use `fafo-simplify`.

Companion skills are optional. Without them, perform the relevant activity directly: ask the consequential question, run a discriminating experiment, implement the useful path, challenge the claim, or remove demonstrated duplication. Do not require an installation or load the whole family.

## Keep the work moving

Prefer the smallest coherent action with a meaningful result. Reuse existing code and tools. A test, sketch, REPL session, short note, or prototype can each be the right instrument. Neither test-first nor test-after is mandatory.

When exploration settles the immediate uncertainty, continue authorised implementation. Revisit discovery when implementation exposes a consequential unknown. Do not manufacture an approval step between modes or automatically launch another task.

For a handoff, preserve only what the next worker needs: current outcome, evidence and how to reproduce it, decisions and their reasons, consequential unknowns, and the next useful action. Omit empty categories. Use the conversation or existing project record; create a document only when persistence or collaboration warrants one. A handoff records current understanding and grants no new permissions.

## Evidence and scope

Generated artifacts consume future attention. Keep tests for identifiable failures, documents for consequential understanding, and abstractions for demonstrated responsibilities. Do not impose quotas on tests, questions, files, or phases.

Code and tests can share a mistaken assumption. Ground expected results in user intent, independent examples, domain rules, or external contracts. Exercise the important behaviour across real boundaries where practical, and report which boundaries were simulated.

Scale verification to consequences and uncertainty. Preserve safeguards and explicit requirements. Experiments stay within authorised environments and side effects. Report actual observations and remaining limitations; passing checks do not prove the product is right.
