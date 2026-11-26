# ProbeStep project context

## Purpose

Give an agent a small, evidence-based way to choose its next action when a consequential decision is uncertain. The [skill source](../skills/probestep/SKILL.md) defines activation, the workflow, and when to stop. The [README](../README.md) covers installation and invocation in Codex and Claude Code.

## Decisions

- The project name is **ProbeStep** and the skill invocation is `$probestep`, matching the `probestep.com` spelling.
- ProbeStep is an experimental skill and a public notebook about its development. The [site](https://probestep.com/) pairs the [origin story](https://probestep.com/story/) with [experiment summaries](https://probestep.com/experiments/) linked to the [evaluation at the v0.1.0-preview.1 tag](https://github.com/jaredchu/probestep/blob/v0.1.0-preview.1/docs/evaluation.md).
- The preview recommends explicit invocation with `$probestep` in Codex or `/probestep` in Claude Code when a consequential uncertainty remains.
- The owner approved a stopping rule that applies even to explicit invocation. A discretionary check should run only if a plausible result could change the decision. Completion requires evidence of the requested effect and all mandatory checks.
- When missing evidence leaves a decision open, the checkpoint names the smallest check, explains why its scope is sufficient and what can be reused or skipped, and states how to obtain the evidence and what the result would change.
- For a repeated symptom, start with one representative instance when it can answer the question. Mention a follow-up only when the checkpoint can name the result that would leave the decision open and the follow-up finding that would change the next action.
- At a handoff, record the tested hypothesis, conditions, result, and a retrievable evidence pointer. Reuse saved evidence under matching conditions. Rereading an original input to confirm the same finding is a recheck and needs a plausible result that would change the decision.
- Carry the count of executed discretionary probes for the same decision across handoffs. If it remains open after three, pause and escalate. Continue authorized mandatory checks.

## Progress

- **Published** [v0.1.0-preview.1](https://github.com/jaredchu/probestep/releases/tag/v0.1.0-preview.1).
  The preview recommends explicit invocation in Codex and Claude Code. The
  [fresh-install smoke test](evaluation.md#claude-code-fresh-install-smoke-test)
  verified `/probestep` with the exact skill file tagged `v0.1.0-preview.1`.
- **Automatic-use pilot** The earlier skill tied the baseline on all six
  frozen cases in each of three Codex model and reasoning configurations.
  The protocol result supports retiring automatic use for this preview.
  [Pilot and replays](evaluation.md#codex-pilot-result)
- **Explicit-invocation checks** Bounded fixtures exercised the missing-evidence
  checkpoint, completion and mandatory checks, handoff, and the three-probe
  pause. The first Claude Code handoff repeated intake. The revised replay
  reused the saved evidence. The separate checkpoint replay left the proposed
  provider-call budget unexplained. Trivial-task overhead checks covered
  skill availability without explicit invocation. [Codex checks](evaluation.md#missing-evidence-checkpoint-follow-up) ·
  [Claude Code checks](evaluation.md#claude-code-portability)
- **Open evidence** Benefit on new tasks remains unmeasured. The evaluation
  specifies a [prospective field log](evaluation.md#stop-and-decide) and a
  [matched Claude Code portability screen](evaluation.md#claude-code-portability).

## Website

The Cloudflare Pages project `probestep` uses `website/` as its static upload directory. The homepage, story, and experiments each declare their canonical URL on `https://probestep.com`. A host-specific response header excludes the Pages fallback hostname from indexing. Keep the XML sitemap in sync when adding public pages. The site links to the released skill and records the limits of each experiment alongside the results.

Cloudflare uses a proxied CNAME and a zone redirect rule to send HTTP and HTTPS traffic from `www.probestep.com` directly to `https://probestep.com` with a permanent 301. The rule preserves paths and query strings.

## Isolated checks

On 26 November 2026, before the automatic-use pilot, fresh Codex CLI sessions
used an earlier draft on read-only synthetic fixtures to calibrate the checks.

- **Before commitment.** Codex selected the skill automatically, read the CMS contract, and used a checkpoint to explain why manual draft creation fit the requirement.
- **After a stall.** With `$probestep` requested, Codex found the first difference at a CSV filter and bounded what the writer swap ruled out to the isolated runs.
- **Already settled.** After reading the skill explicitly, Codex accepted matching row counts and ended without adding a check or checkpoint.
