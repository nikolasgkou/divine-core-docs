# Evaluation record — 24 September 2026

This technical companion records the author’s evaluation method, reported results and implementation boundaries. It is intended to be read without access to the private application. The observations are not an independent external assessment.

## Reported observations

The captured scenario used an isolated Spring Boot application and disposable PostgreSQL database. Worker launch metadata was fixture setup; no LLM or tmux worker was launched. HTTP authorization, Maven/JUnit checks, verification history and completion gates used real application code. Verifier outcomes were not seeded.

1. A source annotation resolved to its authored claim and covering plan step.
2. A frozen Maven check executed three JUnit tests and passed.
3. A source change invalidated the prior evidence. The real MCP completion request was refused, leaving the task CLAIMED.
4. The same check then executed three tests with two failures and no errors.
5. Repair and re-verification produced three passing tests.
6. A worker credential received HTTP 403 when querying a foreign task.
7. The repaired task and its plan step recorded completion.
8. All three verifier executions remained in the journal.

## Method and provenance

The record was captured at 2026-09-24T09:24:14Z. Assertions checked exact executed-test and failure counts before exporting the results. The scenario body took 10.7 seconds, excluding application and database startup; this is not a performance benchmark.

The application snapshot included uncommitted work. Its source fingerprint identifies that evaluation snapshot, rather than a clean tagged release. The fixture was compiled separately. Source identities and execution IDs link the recorded observations within the author’s environment; they do not substitute for independent access or review.

This scenario evaluates the task verification and completion path. It is not a separately verified integration candidate or a production release approval.

## Structural context and measured evidence

The symbol query returns linked structural context. Its evidence status remains UNVERIFIED throughout the run because this version does not project trusted verifier executions into that query.

The replay’s status badges describe the separate verifier gate. HISTORICAL represents the changed source fingerprint and observed completion refusal; it is not the semantic API’s returned status. A separate strict test requiring CURRENT_PASS from that API failed at that assertion and is not counted among the passing observations.

## Operating boundaries

1. Worktrees separate source candidates; they do not isolate hostile OS processes.
2. The local OS user and daemon are trusted. The database is not an external tamper-proof audit authority.
3. Tests establish the declared assertions for measured inputs, not arbitrary prose truth or complete security.
4. Java context extraction parses syntax and Javadoc without full type attribution. It does not automatically enrich raw IDE/LSP hover.
5. The reviewed pair/plan admission path uses a three-seat limit distinct from the general configured launch limit. Nonterminal stale launches require explicit recovery.
6. The recorded experiment does not evaluate cloud isolation, organizational release controls or compliance.

## Historical verification context

An earlier repository milestone reported 779 unit tests, two skipped, and 19 selected integration tests without remaining failures after its documented correction. These are historical counts, not a fresh full-suite result for this publication.

## Reading the interactive presentation

The replay displays a saved sequence and makes no calls to a live daemon. Its recorded data is retained with the publication. Architecture and operational sections describe implementation mechanisms; only the observations listed above are attributed to this experiment.
