# A development session: retrying an upload

This is a fictional session showing how the skills fit together. The observations below are illustrative; no system was run to produce them.

## The starting request

“People occasionally get duplicate items when uploading. Make retries behave sensibly.”

The code can reveal how requests are retried. It cannot establish whether two deliberate uploads of the same file should create separate items. That distinction needs the user's intent.

## Ask what the user means

The user explains that a network retry should return the existing result, while a deliberate second upload should create another item. File content alone is therefore insufficient to identify an accidental retry.

With that distinction settled, the agent can explore the request flow. The rest of the API, storage model, and future versioning feature can remain open.

## Try the request flow

A small experiment in a scratch environment exercises the current upload flow. In this example, it reveals that a client can lose the response after the server has created the item. Retrying the request then creates a second item.

The client cannot tell whether the server created the item. The next implementation decision concerns identifying the same logical request, rather than detecting identical file content.

## Build the retry behaviour

The implementation introduces an identity for one logical upload request using the project's existing mechanisms where possible. The client retains it across retries; a successful retry returns the prior outcome.

While building, inspection reveals that two requests could arrive concurrently. This sends the work back to a small experiment about the storage mechanism's actual guarantees. The final implementation follows that evidence rather than assuming sequential requests.

## Challenge the result

The expected behaviour comes from the user's distinction between a retry and a deliberate new action.

Useful evidence would include:

- One successful upload produces a retrievable item.
- A retry after the response is lost returns the same outcome without a second item.
- A deliberate second upload creates a distinct item.
- Concurrent retries preserve the single logical result.

The appropriate test layer depends on the system. A fake storage object cannot demonstrate the real database's concurrency guarantee. It might still help verify a separate mapping rule.

Choose a test layer that catches these failures without unnecessary maintenance work. There is no reason to add a test for every helper just because it exists.

## Simplify and hand off

Suppose the initial implementation introduced a general retry framework, but the existing request machinery already handles transport retries. The extra framework can be removed if it adds no distinct responsibility, while preserving the request identity and storage guarantees.

A useful handoff would state:

> A logical upload keeps its identity across network retries. Repeated attempts return its existing outcome; a deliberate new action gets a new identity. The implementation and verification cover response loss and concurrent retries. Offline queue restoration remains unverified because it is outside this change.

An actual handoff would also point to the relevant change and reproducible checks. It would claim those checks passed only after execution.
