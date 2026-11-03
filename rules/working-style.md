# Working style

- **Confirm before commits and production runs.** The user reviews changes before two kinds of action: a git
  commit, and a production run or production plots (a full or expensive regeneration of real outputs, as opposed to
  a small test run that checks a change). Ask for a go-ahead before each, even after a series of changes that
  "should" be ready. When a change affects how plots look, the plan includes a few rendered test images, shown
  before any batch job.
- **Follow the step order the user sets.** When the user lays out steps with ordering or gating ("commit after the
  smoke test and before the production run"), each gate is a hard stop: finish the gated step first, or stop and
  ask, rather than go on because an earlier step succeeded. Approving a plan in principle is not permission to run
  ahead of its order.
- **Verify before a speculative fix.** For intermittent or environment-level problems, gather direct evidence
  before changing code: application and extension logs, the state of the live process, a direct connection to the
  component in question, installed vs. latest software versions. Don't build a fix on one plausible piece of
  evidence or call a hypothesis confirmed after one good run; say what a test does and doesn't prove.

**Why:** all three came up in `bnf_wrf_eval`. The user stopped a notebook re-run they had approved too hastily and
asked to review changes before commits and production runs/plots, with test images first (2026-09-01). A
production job array went out right after a smoke test, before the commit the user had asked for in between
(2026-08-30). Two code changes for an intermittent Jupyter hang rested on one plausible clue each; the cause, an
outdated VS Code Jupyter extension, turned up only from logs and from inspecting the live kernel (2026-08-27).
