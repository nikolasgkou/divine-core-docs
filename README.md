# Divine Core — project page

Source for <https://nikolasgkou.github.io/divine-core-docs/>.

A single-page technical overview of **Divine Core**: a control plane that runs
coding agents under recorded permissions, in isolated git worktrees, and closes
a builder task only on evidence the daemon measured itself and bound to one
exact source fingerprint.

The page covers the system architecture, the task lifecycle and its evidence
gate, how verification is frozen before launch, how a worker's effective tool
policy is composed and recorded, the fixed review checklist, the OpenRewrite
recipe chain of custody, and what the daemon does not claim. It includes an
interactive run panel contrasting an accepted completion with a refused one,
and figures read from the daemon's own database.

One hand-written HTML file, no framework and no build step. The implementation
lives in a separate, private repository.
