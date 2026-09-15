---
name: fafo-clarify
description: Clarify product intent and challenge assumptions when a user wants to think through an idea or a consequential product decision blocks development. Avoid turning an already clear task into an interview.
---

# Clarify

Ask enough to agree on the next action. Leave decisions that depend on later discoveries open.

## Find what needs deciding

Read the conversation and relevant existing behaviour. Separate facts available by inspection from preferences or tradeoffs only the user can resolve. Investigate facts yourself within the available scope.

Use a concrete example to expose ambiguity: who is trying to accomplish what, what happens today, and what would make the result useful? Distinguish a desired outcome from the user's proposed mechanism without dismissing that mechanism.

Ask the smallest useful set of questions whose answers would change the next action. Explain the tradeoff; offer a recommendation when grounded in evidence. Ask dependent questions after their prerequisites are resolved. Do not enumerate every hypothetical branch.

Where an experiment can answer more cheaply than discussion, propose or perform it within the authorised task. Do not ask the user to predict technical behaviour that can be observed.

When a relationship or tradeoff is hard to describe, show a small flow, state diagram, comparison, or interface sketch in the conversation. Use domain language and distinguish assumptions from observations. Show only the detail needed for the current decision. Ask about the decision it exposes, not whether the user approves the diagram. Use a table or text sketch if the host cannot render it; a standalone HTML report is optional.

If the user asks to see something, display it on an available user-visible surface. A file path or spoken description alone is insufficient. Explain any format limitation and provide the clearest supported alternative.

## Preserve room to learn

Write down the current outcome, constraints that must hold, and assumptions that could change the work. Mark tentative choices as tentative. Do not turn an inferred preference into an acceptance criterion.

Stop asking once you know enough to proceed. If the user requested discussion only, return the understanding and unresolved decision. If implementation is already authorised, continue without a new process approval. Return to clarification when new evidence changes a product decision.

For example, duplicate uploads might mean accidental retries or intentional new versions. Ask which user outcome is intended; inspect retry behaviour yourself. Naming a deduplication service can wait until that distinction matters to implementation.
