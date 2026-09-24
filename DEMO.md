# Evaluation method and results

This is a written account of the author’s evaluation of Divine Core. The interactive page presents a saved sequence; it does not connect to a running daemon. No source access, software installation or test environment is required to read it.

## Research question

Can a worker complete a task using an earlier passing result after its source has changed? A second probe asks whether a worker credential can query another task through MCP.

## Experimental setup

The author ran an isolated Spring Boot application with a disposable PostgreSQL database. A deterministic worker fixture supplied task and launch state. Real HTTP authorization, Maven/JUnit execution, source fingerprints and database records supplied the observations. No LLM process participated.

The synthetic Java policy accepts a candidate only when both conditions are true: checks passed and source is unchanged. Three tests cover acceptance and rejection. The checks remain unchanged during the experiment.

## Observed sequence

1. The original AND policy passes all three tests.
2. Changing AND to OR changes the source fingerprint. A completion request is refused, and the task remains CLAIMED.
3. Running the same tests against the changed policy produces two failures out of three tests.
4. Repairing the policy produces three passing tests and a fresh execution record. Completion succeeds.
5. A foreign-task request returns HTTP 403.
6. All three verification executions remain in the journal after completion.

## Interpretation

The result supports the specific freshness, regression, access-control and history behaviors exercised by this fixture. The worker’s claim of success is not sufficient to complete changed source with old evidence.

The run was captured on 24 September 2026 at 09:24 UTC. Its scenario body took 10.7 seconds, excluding application and database startup. This is one observation, not a benchmark. Eight observation groups were asserted before the record was exported.

## Scope

These are author-reported observations, not an independent external assessment. The experiment does not evaluate the quality of arbitrary LLM output, test adequacy, hostile-process isolation or production deployment.

Source-linked structural context resolves successfully. The semantic query reports UNVERIFIED evidence status throughout this run; the replay’s pass and failure labels describe the separate verifier gate.
