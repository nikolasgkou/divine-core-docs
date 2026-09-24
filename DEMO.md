# Reproducing the interview demonstration

The public page is a **recorded replay**, not a live connection to a developer's
daemon. Its sanitized data is available in `demo-receipt.json`.

The executable harness belongs in the private local interview bundle alongside
the Divine Core source. It uses Java 25, the repository's cached Maven dependencies
and its pinned cached PostgreSQL container image. It requires a working local
Docker-compatible socket; no LLM account, inference call or artifact download is
part of the demonstration.

## Local commands

From the local bundle:

```sh
./run-demo /absolute/path/to/divine-core
```

The runner builds test dependencies offline, compiles the deterministic harness
into Maven test build artifacts, and runs the `VerificationDemoIT` integration
scenario. It does not edit repository source, launch workers or access the live
workstation database. Temporary database and HTTP server lifecycles belong to the
test harness. This isolated test application is not a second production daemon.

The output receipt is:

```text
target/interview/verification-baseline-demo.json
```

The scenario runs real Maven/JUnit checks three times: pass, deliberate
regression, repair. It also asserts stale-completion refusal and foreign-task
HTTP 403. The run must finish successfully before its receipt is used.

## What remains separate

`InterviewDemoIT.java` is the strict target scenario for the planned trusted
semantic evidence adapter. It currently fails because the semantic query remains
UNVERIFIED after a real verifier pass. The passing baseline demonstration does
not replace or satisfy that stricter acceptance requirement.

## During the interview

Open the recorded replay first and identify its capture time. If local preflight
passes, reproduce the run. If reproduction fails, describe that failure and use
the labeled saved run; do not present the replay as a live execution.
