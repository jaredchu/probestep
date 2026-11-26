---
name: probestep
description: Resolve a consequential uncertainty before committing to a direction or after work stalls. Use when a decision hinges on a testable assumption, attempts repeat without new evidence, or an acceptance check contradicts earlier results. Skip routine work, settled decisions, and verified outcomes.
license: MIT
---

# ProbeStep

## Decide whether to check

Name the decision within the current task and the uncertainty that could change it. Run a discretionary check only if a plausible result would change what you do. If the evidence already settles the decision, proceed within scope.

Claim completion only when evidence shows the effect the user requested. A receipt verifies the step it acknowledges. When evidence of the requested effect is missing, report what is confirmed and what remains pending or blocked.

Keep mandatory checks, including acceptance and safety checks, outside the discretionary stop rules. Satisfy each with applicable evidence or run it within authorization. If a required check fails or is blocked, report it and leave completion open. Apply these rules even when ProbeStep is invoked explicitly.

## Resolve the uncertainty

- **Before committing**, identify the assumption that could change the approach. Choose the smallest check that could resolve it.
- **After a stall**, carry forward what earlier attempts ruled out and under which conditions. Keep inconclusive results distinct. Compare conflicting checks and their conditions. When feasible, use a passing control to find where behavior first differs.
- **At an external blocker**, identify the exact evidence, access, or decision needed, who can provide it, and what their response would unlock. Continue any useful work within scope that does not depend on it.

When handing off, use the existing handoff to record each relevant tested hypothesis, its conditions, the observed result, and a retrievable evidence pointer. Treat inherited claims with inaccessible evidence as unverified.

Reuse saved evidence when the tested conditions match. Rereading the original input to confirm the same finding counts as a recheck. For discretionary work, recheck only if you can name a plausible result that would change the decision.

Before running a discretionary check, identify how its plausible outcomes would change the decision. Add a second discretionary check only if the first result leaves a material uncertainty open and a plausible result of the second would change the decision. Run authorized checks and act on the result within scope.

Count executed discretionary probes for the same decision, including retries and rechecks. Record the running count in the handoff and resume from it. If the decision is still open after three probes, pause discretionary probing. Report what remains uncertain and ask the user or responsible owner to decide whether to continue before running another probe. Continue authorized mandatory checks regardless of the count.

## Show a checkpoint when you make progress

Label the relevant update or final response **ProbeStep checkpoint** when you run or identify a decision-changing check, or isolate a material blocker. State the decision, what the evidence supports and under which conditions, and what the check changes. Include earlier ruled-out explanations when relevant.

If missing evidence leaves a material decision open, name the smallest next check and what its result would change. For a rerun, limit new work to the inputs, stages, and observations needed to distinguish the remaining explanations. Explain in the checkpoint why that scope is enough and which verified work can be reused or skipped. Say where to look or how to capture evidence that was never recorded. Name any access or approval needed.

For a repeated symptom, scope the first proposed check to one representative instance unless the decision depends on comparing instances. If comparison is necessary, say what difference would change the decision.

Mention a follow-up only if you can name which first result would leave the decision open, what finding the follow-up could produce, and what you would do differently if it did. Otherwise, end the checkpoint after the first check.

A discretionary check that settles the decision still gets a checkpoint. If the requested effect and required checks were already verified, give the result directly.
