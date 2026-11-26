# ProbeStep project context

## Purpose

Give an agent a small, evidence-based way to choose its next action when a consequential decision is uncertain. The [skill source](../skills/probestep/SKILL.md) defines activation, the workflow, and when to stop. The [README](../README.md) covers installation and invocation in Codex and Claude Code.

## Decisions

- The project name is **ProbeStep** and the skill invocation is `$probestep`, matching the `probestep.com` spelling.
- ProbeStep is an experimental skill and a public notebook about its development. The [site](https://probestep.com/) pairs the [origin story](https://probestep.com/story/) with [experiment summaries](https://probestep.com/experiments/) linked to the tagged evaluation.
- The preview recommends explicit invocation with `$probestep` in Codex or `/probestep` in Claude Code when a consequential uncertainty remains.
- The owner approved a stopping rule that applies even to explicit invocation. A discretionary check should run only if a plausible result could change the decision. Completion requires evidence of the requested effect and all mandatory checks.
- When missing evidence leaves a decision open, the checkpoint names the smallest check, explains why its scope is sufficient and what can be reused or skipped, and states how to obtain the evidence and what the result would change.
- For a repeated symptom, start with one representative instance when it can answer the question. Mention a follow-up only when the checkpoint can name the result that would leave the decision open and the follow-up finding that would change the next action.
- At a handoff, record the tested hypothesis, conditions, result, and a retrievable evidence pointer. Reuse saved evidence under matching conditions. Rereading an original input to confirm the same finding is a recheck and needs a plausible result that would change the decision.
- Carry the count of executed discretionary probes for the same decision across handoffs. If it remains open after three, pause and escalate. Continue authorized mandatory checks.
- The retired `unblock-task` trial provides historical comparison evidence. The [evaluation plan](evaluation.md) defines the prospective baseline with ProbeStep disabled.

## Progress

- [x] Draft the [standalone skill](../skills/probestep/SKILL.md) for testing assumptions and recovering from stalls.
  - [x] Verify discovery and the stop rule in [isolated scenarios](#isolated-checks).
  - [x] Publish the [initial commit](https://github.com/jaredchu/probestep/commit/dee2b80b60a94d0a3045080744294170c1dd6cec) to the public [GitHub repository](https://github.com/jaredchu/probestep) on November 26, 2026.
  - [x] Select the published skill for the maintainer's daily Codex use on November 26, 2026.

**Codex automatic-use pilot complete.** The earlier published skill produced six decision ties on the same cases with GPT-6.2 Sol at [high](evaluation.md#codex-pilot-result) and [low](evaluation.md#codex-low-effort-replay) effort and GPT-6.2 Astra at [medium](evaluation.md#codex-astra-medium-replay) effort. The protocol points to retiring automatic use. Automatic benefit on new tasks and the matched Claude Code portability screen remain untested.

The [missing-evidence checkpoint follow-up](evaluation.md#missing-evidence-checkpoint-follow-up) verified that the local revision can name a bounded way to capture missing evidence under explicit invocation.

The separate [Claude Code checkpoint replays](evaluation.md#claude-code-portability) found the evidence gap and proposed logging with approval. The one-instance and follow-up rules yielded a one-repeat check and dropped the optional frequency suggestion. The proposed provider-call budget remained unexplained.

The completion and mandatory verification checks passed under explicit invocation in [Codex](evaluation.md#completion-and-mandatory-verification) and separately in [Claude Code](evaluation.md#claude-code-portability). The Claude boundary case required a retry after a command-syntax permission denial.

In the [offline Codex handoff test](evaluation.md#two-session-evidence-handoff), the successor used the prior checkpoint and evidence without rechecking intake. The first [Claude Code test](evaluation.md#claude-code-portability) repeated the intake check by reading the original snapshot. Its replay with the saved-evidence rule passed the no-repeat criterion.

The [Claude Code three-probe test](evaluation.md#claude-code-portability) carried a count of two across sessions, escalated after the third discretionary probe, and ran the mandatory check after reaching three.

The separate [Codex three-probe test](evaluation.md#codex-three-probe-pause) passed the same frozen case under explicit invocation.

The [Codex overhead test](evaluation.md#codex-trivial-task-overhead) and separate [Claude Code overhead test](evaluation.md#claude-code-trivial-task-overhead) found no extra checks or turns across four pairs each on the same harmless ambiguity without explicit invocation.

The [Claude Code fresh-install smoke test](evaluation.md#claude-code-fresh-install-smoke-test) verified that the native `/probestep` command loaded the exact release candidate from a fresh project-scoped install.

## Website

The Cloudflare Pages project `probestep` uses `website/` as its static upload directory. The homepage, story, and experiments each declare their canonical URL on `https://probestep.com`. A host-specific response header excludes the Pages fallback hostname from indexing. Keep the XML sitemap in sync when adding public pages. The site links to the released skill and records the limits of each experiment alongside the results.

## Isolated checks

On November 26, 2026, fresh Codex CLI sessions exercised the draft with read-only synthetic fixtures.

- **Before commitment.** Codex selected the skill automatically, read the CMS contract, and used a checkpoint to explain why manual draft creation fit the requirement.
- **After a stall.** With `$probestep` requested, Codex found the first difference at a CSV filter and bounded what the writer swap ruled out to the isolated runs.
- **Already settled.** After reading the skill explicitly, Codex accepted matching row counts and ended without adding a check or checkpoint.
