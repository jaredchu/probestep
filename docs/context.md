# ProbeStep project context

## Purpose

Give an agent a small, evidence-based way to choose its next action when a consequential decision is uncertain. The [skill source](../skills/probestep/SKILL.md) defines activation, the workflow, and when to stop. The [README](../README.md) covers use in Codex.

## Decisions

- The project name is **ProbeStep** and the skill invocation is `$probestep`, matching the `probestep.com` spelling.
- The owner approved a stopping rule that applies even to explicit invocation. A check should run only if a plausible result could change the decision. Verified completion ends the task.
- The existing `unblock-task` trial continues in parallel and serves as the baseline for the narrower stall-recovery workflow.

## Progress

- [x] Draft the [standalone skill](../skills/probestep/SKILL.md) for testing assumptions and recovering from stalls.
  - [x] Verify discovery and the stop rule in [isolated scenarios](#isolated-checks).
  - [x] Publish the [initial commit](https://github.com/jaredchu/probestep/commit/dee2b80b60a94d0a3045080744294170c1dd6cec) to the public [GitHub repository](https://github.com/jaredchu/probestep) on November 26, 2026.

**Proposed next step** is a field trial after the current baseline trial. Check whether ProbeStep finds a decision-changing test before the user has to ask and skips tasks that are already settled.

## Isolated checks

On November 26, 2026, fresh Codex CLI sessions exercised the draft with read-only synthetic fixtures.

- **Before commitment.** Codex selected the skill automatically, read the CMS contract, and used a checkpoint to explain why manual draft creation fit the requirement.
- **After a stall.** With `$probestep` requested, Codex found the first difference at a CSV filter and bounded what the writer swap ruled out to the isolated runs.
- **Already settled.** After reading the skill explicitly, Codex accepted matching row counts and ended without adding a check or checkpoint.
