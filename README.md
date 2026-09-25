# Divine Core — technical overview

A self-contained engineering publication at https://nikolasgkou.github.io/divine-core-docs/.

The overview explains the control-plane architecture and presents the author’s recorded evaluation of HTTP authorization, source-bound verification and completion refusal. Readers need no source access or local test environment.

`DEMO.html` / `DEMO.md` describe the evaluation question, setup, observations and interpretation. `VALIDATION.html` / `VALIDATION.md` document provenance and limitations. `demo-receipt.json` retains the sanitized captured data used by the replay. The application itself is private and is not distributed here.

The replay is recorded, not a live service or independent external assessment. Operational and architectural descriptions remain distinct from the measured observations.

Static HTML, CSS, JavaScript and SVG; no framework, remote fonts, analytics or daemon calls. Published independently through GitHub Pages from main at the repository root.

`SEMANTIC.html` explains the 25 September semantic documentation candidate: source-linked intent, inventory, document provenance, change-impact review and generated human/agent views. It records verified shared-runtime activation while distinguishing implementation from incomplete repository adoption. The explanation is editorial; the adoption ledger is a static projection of the Java-generated documentation view and recorded ordinary test evidence. The original recorded evaluation is unchanged.

`adoption-snapshot.json` is the compact public projection. It retains the Java view’s source snapshot, plan digest and source-manifest hash, inventory counts, authored adoption objectives, reviewed-claim counts and scoped ordinary test records, and sanitized isolated import/upgrade observations and shared-runtime activation checks. Source files and evidence records are fingerprinted; private repository identities and execution configuration are excluded.

To refresh the ledger, generate and check the candidate views with the core Java documentation-view commands, extract only the public fields into `adoption-snapshot.json`, and project those same values into the marked block in `SEMANTIC.html`. Use the current claim manifests and final ordinary test records for fields outside the Java view. Inspect the diff and retain unresolved obligations. The static page does not query or activate a daemon, and the snapshot is not a managed verification receipt.
