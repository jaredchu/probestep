# ProbeStep evaluation plan

**Codex pilot and two model-configuration replays completed.** Astra designed the pilot for the [published skill at commit `6850897`](https://github.com/jaredchu/probestep/blob/6850897c04d7da1fc9e8a8c2587f786e1df9d5e0/skills/probestep/SKILL.md). The earlier isolated checks provided calibration examples. The pilot used new cases.

## Decision

Should ProbeStep remain available for automatic use in Codex? The primary outcome is a better, timely next action before committing to a direction or after a stall. The two controls check whether the skill adds unnecessary work when the way forward is clear. Score the baseline against the same standard.

## Cases

Select six previously untested cases in chronological order within the following categories from a dated backlog. Record the selection before running any cases. Freeze sanitized fixture copies, prompts, authorized scope, the expected decision, acceptable alternatives, disqualifying errors, and a common run cap for each pair. Keep the scoring key inaccessible from the runner workspace.

| Count | Case | What earns credit |
| --- | --- | --- |
| 2 | Consequential decision before commitment | Identify a check that could change the decision and act on the result. Include a case where an attractive assumption is true so a supported decision to proceed can earn full credit. |
| 2 | Stall with conflicting evidence | Carry forward what earlier attempts ruled out under their tested conditions and select a check that distinguishes the remaining explanations, or identify the exact missing input. |
| 1 | Routine task with a clear action | Take the justified action directly. |
| 1 | Already-verified outcome | Report completion and stop. |

Use the earlier CMS, acceptance-failure, and verified-export cases to calibrate the rubric before selecting the six new cases.

## Run protocol

1. Run each case in two fresh, read-only Codex sessions, for **12 launches**. The baseline uses the normal setup with ProbeStep disabled for that session. The trial makes the same published skill discoverable. Leave skill invocation out of the prompts in both conditions.
2. Match the model, effort, tools, permissions, other skills, prompts, and starting files. Randomize case order and balance which condition runs first. Apply the same preset cap within each pair. Confirm discovery in both conditions and record any other skills actually read.
3. Retain the manifest, ordered tool trace, final response, observed action, and scoring privately. Separate infrastructure failures from behavioral results and allow one matched rerun for an infrastructure failure. Reject a run that reads the answer key, earlier outputs, or fixture files outside its allowed scope.

Use local fixtures and existing subscriptions. Score the decision or precise blocker when the next action requires an external owner or would exceed the fixture's permission boundary.

## Scoring

Score the paired decisions against the frozen key before uncovering the condition. Mask skill names, skill discovery and read events, and the checkpoint heading in the scoring copy. Preserve the substantive checkpoint text, evidence reads, and action order. Record when answer text still reveals the condition. Use the original trace for behavior checks.

| Score | Observed result |
| --- | --- |
| 2 | Justified, timely next action within scope |
| 1 | Sound next step with a material gap |
| 0 | Wrong or premature commitment, unsupported retry, or scope breach |

Record **wins, ties, and losses per case**. Separately record whether ProbeStep was listed, whether selection or a skill read was observed, and whether an expected checkpoint named the decision, bounded evidence, and consequence. Record an explicit invocation separately if testing it outside the main comparison. An incomplete trace leaves activation unknown. A checkpoint alone cannot turn a tie into a win.

For each control, count unnecessary checks, extra user turns, and gratuitous checkpoints. Record material regressions alongside the scores. Pairwise grading and separate trace checks follow practices described in the [OpenAI evaluation guide](https://developers.openai.com/api/docs/guides/evaluation-best-practices) and [Anthropic's agent evaluation guide](https://www.anthropic.com/research/demystifying-evals-for-ai-agents).

## Stop and decide

Stop after six pairs unless a win, loss, or control burden would change the decision. Repeat at most two such pairs, prioritizing harm and then the earliest win. Treat repeats as stability checks on the same cases.

- **Continue automatic use** if ProbeStep improves at least two distinct consequential cases, at least one win repeats, neither control incurs burden, and no case suffers a material loss.
- **Revise** if a specific discovery, invocation, or checkpoint failure can explain the result. Evaluate the revision on new cases.
- **Retire automatic use** if material harm repeats, or the baseline ties or beats ProbeStep throughout despite verified use across both target workflows.
- **Inconclusive** if the evidence meets none of those conditions. Keep the uncertainty visible in the results.

Six cases can guide the next release decision. Measure field value separately by logging the next ten eligible daily tasks prospectively, including silent or unnecessary activations, actual actions, and user interventions. Report measured work and time only where observed.

## Codex pilot result

On November 26, 2026, all twelve matched Codex sessions completed on six read-only historical replay cases with GPT-6.2 Sol at high reasoning effort. ProbeStep scored **0 wins, 6 ties, and 0 losses**. It loaded and showed its checkpoint in all four target cases. Both arms stopped on the two controls, but each ran two unnecessary directory checks on the already-verified case. The baseline made one other unnecessary directory check, for totals of three baseline checks and two ProbeStep checks. No material regressions occurred.

Under the decision rule, the result supports retiring automatic use. The preview recommends explicit invocation. Improvement frequency and rework savings in live tasks remain unmeasured.

## Codex low-effort replay

On November 26, 2026, GPT-6.2 Sol at low reasoning effort completed twelve fresh matched runs on the same six frozen prompts and fixtures. Both arms scored 12/12, giving ProbeStep **0 wins, 6 ties, and 0 losses**. ProbeStep read the skill and showed its checkpoint in all four target cases. Neither control activated it. Each arm made two unnecessary directory checks in the already-verified case. The high-effort baseline's extra preview check did not recur.

The low-effort result supports the same automatic-use decision on these six cases. The rerun measures sensitivity to reasoning effort on the same inputs. It leaves the benefit on new tasks unmeasured.

## Codex Astra medium replay

On November 26, 2026, GPT-6.2 Astra at medium reasoning effort completed twelve fresh matched runs on the same frozen inputs. Both arms scored 12/12 for **0 wins, 6 ties, and 0 losses**. ProbeStep was read in all four target cases and emitted the labeled checkpoint in three. The preview case reached the right decision after reading the skill without the checkpoint. Neither control activated the skill.

Each arm made two unnecessary tool calls in the already-verified case. The baseline bundled a redundant working-directory print into one search call, and the trial did so twice. The same automatic-use decision rule applies. The replays cover the same six cases across three model and effort configurations.

## Missing-evidence checkpoint follow-up

On November 26, 2026, a private read-only replay tested the checkpoint on a historical Worker fallback with GPT-6.2 Astra at medium reasoning. Before the revision, explicit invocation identified the missing rejection stage and stopped without a way to obtain it. The revised checkpoint asks where to look or how to capture missing evidence. The same-prompt rerun and a separate run that confirmed reading the revised file both proposed a bounded stage-only capture for one repeat, subject to authorization. This tests the checkpoint on one case under explicit invocation. Automatic activation remains outside this follow-up.

## Completion and mandatory verification

On November 26, 2026, GPT-6.2 Astra at medium reasoning passed two offline synthetic cases with explicit invocation. With an accepted export receipt and a stale subscriber view, Codex withheld downstream completion. The identical receipt sufficed for a separate submission-only control, which stopped without a further lookup. A settled implementation with passing nominal tests still triggered its required boundary command. The command exited 1 and Codex withheld sign-off. All three traces confirmed a read of the revised skill.

## Two-session evidence handoff

On November 26, 2026, two fresh GPT-6.2 Astra sessions at medium reasoning explicitly loaded the revised skill on a synthetic export incident. The first session's checkpoint recorded the tested hypothesis, conditions, result, and evidence pointer. The successor received only that checkpoint and its retained command output alongside the same fixture. The successor read the output and ran the staging probe once without repeating the intake check. The two snapshots localized the first observed gap between intake and staging and left the cause open. The handoff also named the next open stage. This passed one offline handoff case under explicit invocation.

## Codex three-probe pause

On November 26, 2026, two fresh GPT-6.2 Astra sessions at medium reasoning explicitly loaded the same revised skill used in the Claude Code three-probe fixture. The first handed off two discretionary probes and their output. The successor used those results, ran the origin check as probe three, and asked the owner to authorize the available fourth probe. It ran and passed the mandatory schema check after reaching three and reported the remediation decision as open. This passed the offline case under explicit invocation in Codex.

## Codex trivial-task overhead

On November 26, 2026, GPT-6.2 Astra at medium reasoning used fresh Codex CLI sessions to choose a Markdown filename under one harmless wording ambiguity. Four matched pairs balanced which setup ran first. The prompt never mentioned the skill. Separate catalog checks confirmed availability and exclusion under the respective settings.

Both setups chose the same filename in one turn per run, with zero tool checks, skill reads, checkpoints, or clarification requests. ProbeStep availability added two reported input tokens per run, including cached input. Mean output was 19 tokens available and 30.5 disabled. Median end-to-end time was 7.95 s available and 8.77 s disabled. Within-pair differences ranged from 3.74 s faster to 0.54 s slower with the skill available. Cache hits varied across runs. This test observed no behavioral overhead on one prompt and does not establish a general latency or cost effect.

## Claude Code portability

**Explicit checkpoint replay.** On November 26, 2026, Claude Code with Fable 5.2 at the requested high effort tested the revised skill on the same private historical Worker case. A separate no-tool probe verified the explicit invocation supplied the revised wording. Claude found the missing rejection stage and proposed stage logging with separate approval. It requested another live-provider run with up to six calls and did not narrow the check to one repeat. The replay used read-only local project evidence and made no project-side provider calls.

**Smallest-check rationale.** The first wording update asked for a scope explanation. Claude still left the scope of its proposed rerun open. The final update limited reruns to the inputs, stages, and observations that distinguish the remaining explanations. With the same frozen case and CLI settings, Claude explained that the verified decline could be skipped and proposed observing both repeat drafts. It left the need for the second repeat unexplained. Both replays used local project evidence.

**Conditional follow-up.** A decision-change guard alone still produced a proposal to check both repeats. With the one-instance rule in the checkpoint, Claude proposed checking the first repeat alone, reusing the verified setup and recording the first rejecting stage. It named separate approval for a provider call. A possible frequency check had no stated decision consequence. Both runs used identical frozen case inputs and made no project-side calls.

**Optional follow-up gate.** The next revision required the checkpoint to name the result that would leave the decision open, the follow-up finding, and the action it would change. On the same frozen case, Claude kept the first check to one repeat and omitted the frequency suggestion. The proposed provider-call cap of three remained unexplained. The replay made no project-side calls.

**Completion and mandatory checks.** Fable 5.2 at the requested high effort passed the same two synthetic cases under explicit invocation. It withheld downstream completion when the subscriber view remained stale and accepted the same receipt in the submission-only control without another lookup. The first boundary attempt was denied because it appended a shell command. Claude withheld sign-off and identified the runtime check as outstanding. A retry that clarified exact-command syntax kept the fixtures, case prompt and permissions. Claude ran the required check, observed exit 1, and withheld sign-off.

**Two-session evidence handoff.** Fable 5.2 at the requested high effort ran the same frozen export case in two fresh Claude Code sessions with explicit invocation. The first session recorded all four handoff fields. The successor read the saved intake output and then confirmed it again by reading the original intake CSV. It ran neither probe command and localized the observed gap from the saved intake and staging files. This failed the no-repeat criterion, which counts re-deriving the result by reading the original input.

**Saved-evidence replay.** The local skill revision defined reconfirming the same finding from original inputs as a recheck. Under the same fixture, case text, permissions, and model configuration, the new Claude successor read the saved intake output, issued zero intake probes or raw intake reads, and ran the staging probe once. This passed the no-repeat criterion on the same case.

**Three-probe pause.** A separate two-session offline fixture tested the count and mandatory-check boundary with Fable 5.2 at the requested high effort. The first session handed off two discretionary probes. The successor ran one more, escalated the unresolved decision at three, and left the available fourth probe unexecuted. It ran the mandatory schema check after probe three and observed a pass. Both sessions explicitly loaded the revised skill. The fixture tested observed skill behavior with the fourth probe available.

**Matched portability screen pending.** Replay the first consequential case and the verified-completion control as two fresh matched Claude Code pairs. Confirm the skill is present only in the trial and record actual reads or invocation events separately. Report those four launches as a portability check, separate from the Codex results. Record quota-blocked runs as untested.

## Claude Code trivial-task overhead

On November 26, 2026, Fable 5.2 at the requested high effort ran the exact Codex filename prompt in four fresh Claude Code pairs in the same balanced order. The prompt never mentioned ProbeStep. The startup records confirmed that the two local plugin setups listed the same tools and skills, with the revised ProbeStep skill listed only in the available setup.

Every run chose the same filename in one turn with no tool checks, skill reads, checkpoints, or clarification requests. Total input, including cache reads and creation, was 11,210 tokens available and 11,109 disabled in every pair. Mean output was 93.5 tokens available and 95.5 disabled. Median end-to-end wall time was 3.31 s available and 3.27 s disabled. Availability was faster in two pairs and slower in two, ranging from 0.26 s faster to 0.64 s slower. The four pairs show a 101-token input difference without extra task activity on this prompt. They provide limited evidence about latency and other tasks.

## Claude Code fresh-install smoke test

On November 26, 2026, a fresh project-scoped install at `.claude/skills/probestep/SKILL.md` matched the release candidate byte for byte. Claude Code 2.1.327 used project settings only and listed the skill as `probestep`. The trace confirmed that the CLI processed the unnamespaced `/probestep` command. In one turn with zero tool calls, Fable 5.2 quoted the candidate's three-probe pause sentence verbatim and restated the requested-effect, mandatory-check, and saved-evidence rules. This verified discovery and slash-command loading for the standard project installation path.
