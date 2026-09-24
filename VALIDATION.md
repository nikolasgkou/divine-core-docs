# Validation record — 24 September 2026

## What the recorded demonstration actually ran

The published replay is backed by `demo-receipt.json`, captured at
2026-09-24T09:24:14Z. It is a deterministic integration demonstration against an
isolated Spring Boot application and disposable cached PostgreSQL container.
The worker launch metadata is fixture setup; no LLM or tmux worker is launched.
The HTTP authorization, Maven/JUnit executions, verification journal and
completion gates are real application code. Verifier outcomes are never seeded.

1. A real source annotation resolves to the authored claim and plan step.
2. A frozen offline Maven check executes three JUnit tests and passes.
3. Editing `checked && unchanged` to `checked || unchanged` changes the source
   fingerprint. The real MCP `finish_task` call refuses stale verification,
   leaving the task CLAIMED.
4. The same frozen check executes again: three tests, two failures, no errors.
5. Repairing the expression and re-running produces three passing tests.
6. A real worker credential receives HTTP 403 when querying a foreign task.
7. The corrected task completes through MCP and its plan step records completion.
8. All three verifier executions remain in the journal.

The scenario body took 10.7 seconds on this workstation, excluding application
and database startup. This is one observation, not a performance benchmark.
The harness asserted the exact inner test and failure counts before exporting
the receipt. Export occurs only after all scenario assertions pass.

Core source fingerprint used by this run:
`0eb78adff250139f245218977c913d4b6e89c2df4118ad9ab77d486993414d2f`.
The demo harness was compiled separately into test build artifacts; it is not
part of that core fingerprint. Its source is retained in the local interview
bundle, with a checksum in the bundle manifest. This run is not a managed
integration READY receipt or a production release approval.

## Semantic integration is still incomplete

The symbol query returns structural context but currently supplies no trusted
verifier adapter. Its evidence status remains `UNVERIFIED` throughout this run.
The replay's large status badges describe the **verifier gate state**, while the
semantic status is shown separately in each stage. The HISTORICAL label describes
the observed changed fingerprint plus refusal, not a current semantic API result.

A separate strict end-to-end test requiring `CURRENT_PASS` from the semantic
query failed at that assertion, as expected from the missing adapter. This failure
is not counted as a pass and is not hidden by the baseline demonstration.

The planned adapter must bind persisted plan revisions, task/step relationships,
exact frozen checks and source fingerprints to immutable verifier executions.
General test-suite success must not automatically become claim evidence.

## Other implementation boundaries

1. Worktrees separate candidate source; they do not isolate hostile OS processes.
2. The local operating-system user and daemon are trusted. Recorded evidence is
   not an externally tamper-proof audit store.
3. Tests establish their assertions for measured inputs, not arbitrary prose
   truth, complete security or clinical safety.
4. Java semantic extraction currently parses syntax/Javadoc without full type
   attribution. Raw IDE/LSP hover is not automatically enriched.
5. The current pair/plan admission path still hardcodes three seats despite the
   separately configured general launch limit. Fixing that inconsistency is pending.
6. Cloud isolation, protected CI promotion, compliance-control mapping and
   operational retention are production extensions, not capabilities certified
   by this demonstration.

## Prior repository verification

The earlier semantic enablement record reports 779 unit tests (two skipped) and
19 selected integration tests with no remaining failures after its documented
correction. Those are historical results for that milestone; they are not
presented as a fresh full-suite run for this interview bundle.

## Presentation verification

The HTML uses local CSS, JavaScript and inline SVG, with no remote font or script
dependencies. Browser checks cover desktop/mobile layout, stage selection,
presenter mode and JavaScript errors. A recorded replay remains clearly labeled
and never calls a live daemon from the public website.
