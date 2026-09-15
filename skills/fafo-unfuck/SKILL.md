---
name: fafo-unfuck
description: Audit an existing codebase's tests and test-driven scaffolding for actual failure protection, independent expectations, and maintenance burden. Use when asked to unfuck a codebase or assess which tests to keep, rewrite, consolidate, or remove.
---

# Unfuck My Codebase

Find which tests earn their place and which machinery makes the codebase harder to change without protecting useful behaviour. A suite's size or whether it was written with TDD does not answer that question.

## Establish what is there

Use the requested scope. For a whole-codebase audit, map the test suites, runners, fixtures, mocks and relevant production boundaries. Follow representative cases into the code they exercise and expand where the evidence warrants it. State what was inspected, sampled or left unexamined; never present a sample as an exhaustive audit.

Look for existing requirements, examples, contracts and regression history. Their absence is an uncertainty, not proof that a test is useless. Ask about product intent only when it changes a consequential recommendation and cannot be established from available evidence.

## Assess the protection

For a test or a group with the same purpose, establish:

- What meaningful behaviour or failure it protects, and why that matters.
- Where its expected result comes from. An implementation copied into a test, an approved snapshot and an independently worked example provide different evidence.
- Whether it can expose the claimed failure. Check assertions, inputs and the exercised path; mocks may isolate useful logic or remove the very risk being claimed.
- What distinct protection would disappear if it were removed. Similar-looking tests may cover different boundaries or regressions.
- What burden is demonstrated: brittle implementation coupling, flaky dependencies, duplicated setup, expensive execution or changes spread across many files. Measure runtime or flakiness when making quantitative claims; otherwise label the observation or uncertainty.

A targeted run, a known-bug reproduction or a reversible fault in an isolated copy can clarify a doubtful test. Use these when they resolve a decision; do not manufacture a mutation-testing programme for every audit. Distinguish a test that failed for the intended reason from an unrelated setup failure. Passing after deletion proves nothing about lost protection.

Rare failures can be valuable protection. Internal tests, snapshots, mocks and generated tests each need assessment in context. If the expected result is wrong, propose correcting it rather than simply deleting the disagreement. Untested consequential behaviour is a gap even when the existing suite is large.

## Show the findings

Produce a table the user can inspect, with file or test references, protected behaviour, source of expectation, evidence of value or burden, recommendation, and uncertainty. Use keep, rewrite, consolidate, remove, or investigate as appropriate. Explain any replacement coverage needed before removal. Group repetitive findings without hiding distinct risks.

Lead with the changes most likely to reduce real maintenance work while preserving meaningful protection. Avoid invented quality scores, deletion targets and token savings. A small audit can be a short table. A large suite may benefit from a coverage map or measured runtime distribution; show the visual in the conversation when supported and identify sampled or unavailable data.

## Act within the request

An assessment request produces findings. An authorised cleanup includes implementing supported changes and checking affected behaviour; do not invent another approval gate when the user already asked for the work. Retain uncertain protections until enough evidence supports changing them. Do not expand test cleanup into unrelated architecture work or global skill configuration.

After changes, report the concrete burden removed, the protection preserved or added, what checks ran, and remaining gaps. A smaller green suite is an observation, not the success criterion.

This skill audits accumulated test debt. The optional fafo-verify skill helps investigate a specific correctness claim; fafo-simplify helps implement broader simplifications. Neither companion is required.
