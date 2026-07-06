# H4 Analysis: Progress Reports Are the Primary Governance Interface

## Result

H4 is **supported**.

Progress reports in `/autoresearch` are not decorative outputs. They are the primary governance interface that lets humans steer a long-running AI research process without collapsing it into step-by-step command execution.

## Why Reports Are Governance Interfaces

A long-running AI research agent creates a control problem:

- If the human approves every step, the agent loses autonomy.
- If the human never reviews progress, the agent may drift.
- If the human only reads raw logs, oversight becomes too expensive.

Progress reports solve this by compressing internal state, evidence, and interpretation into a format optimized for human judgment.

```text
Internal artifacts → report synthesis → human judgment → updated value signal → AI reprioritization
```

This makes reports the point where AI autonomy and human responsibility meet.

## Governance Functions of a Progress Report

| Report component | Human question answered | Governance function |
|---|---|---|
| Research objective | Are we still solving the right problem? | goal alignment |
| Current status | Where are we in the project? | orientation |
| Key findings | What has been learned? | meaning consumption |
| Evidence summary | Why should I believe this? | trust calibration |
| Negative results | What has been ruled out? | prevents repeated waste |
| Open questions | What remains uncertain? | risk awareness |
| Direction recommendation | Should we deepen, broaden, pivot, or conclude? | steering |
| Next actions | What will the AI do next? | expectation setting |
| Human decision points | What input is needed from me? | value-signal update |
| Artifact links | Where can I inspect details? | auditability |

## Required Fields for a Good Long-Running AI Report

A robust report should include:

1. **Objective and value function**
   - What is the work trying to achieve?
   - Who is it for?
   - What counts as success?

2. **Trajectory summary**
   - What changed since the last report?
   - What evidence was produced?
   - What synthesis changed?

3. **Key claims with evidence**
   - What does the AI currently believe?
   - Which artifacts support each claim?

4. **Uncertainty and failure modes**
   - What might be wrong?
   - What has not yet been validated?

5. **Direction decision**
   - Deepen, broaden, pivot, or conclude?
   - Why?

6. **Human feedback surface**
   - What kind of human input would be most valuable?
   - What options should the human choose between?

7. **Next autonomous actions**
   - What will the AI do if no human correction arrives?

## Comparison Against Alternatives

| Governance mode | Advantage | Failure mode |
|---|---|---|
| Step-by-step approval | Maximum procedural control | Human bottleneck; lost autonomy |
| Full autonomy without reports | Maximum speed | Drift, weak accountability, hard-to-trust conclusions |
| Raw artifact inspection | Complete detail | Too much cognitive load for human governance |
| Periodic progress reports | Balanced autonomy and oversight | Requires high-quality synthesis and honest uncertainty reporting |

Report-based governance is the best fit for `/autoresearch` because it matches the intended human role: low-frequency, high-level steering.

## Report Failure Modes

### 1. Activity dump

The report lists many actions but does not explain what was learned.

**Symptom:** human sees effort but not meaning.

**Fix:** force every report to include key claims, evidence, and changed understanding.

### 2. Over-compressed summary

The report states conclusions without evidence or links.

**Symptom:** human cannot calibrate trust.

**Fix:** include artifact links, evidence snippets, and uncertainty.

### 3. No decision surface

The report explains status but does not show what the human can decide.

**Symptom:** human reads passively; value signal does not update.

**Fix:** include recommended direction and explicit feedback prompts.

### 4. Too frequent reports

The report cadence interrupts the inner loop before evidence accumulates.

**Symptom:** governance overhead dominates research.

**Fix:** trigger reports after outer-loop synthesis, significant findings, pivots, or stagnation.

### 5. Too rare reports

The AI works too long without human value-signal refresh.

**Symptom:** drift or over-optimization of proxy goals.

**Fix:** maintain periodic reports or generate reports at uncertainty/risk thresholds.

### 6. False certainty

The report presents speculative synthesis as confirmed result.

**Symptom:** human over-trusts weak claims.

**Fix:** label confidence, evidence type, and confirmatory vs exploratory status.

## Report Cadence Principle

Reports should be generated when they can change governance, not merely when activity occurred.

Good triggers:

- after outer-loop synthesis;
- after surprising result;
- after a pivot candidate appears;
- after sustained stagnation;
- before expensive or irreversible actions;
- when findings become coherent enough for human decision;
- at periodic intervals for long unattended operation.

Bad triggers:

- after every small action;
- because a timer fired but nothing changed;
- before enough evidence exists to synthesize.

## H4 Integration with H1-H3

H4 completes the framework:

- H1: artifacts are consumer interfaces.
- H2: human-AI collaboration is value-signal exchange.
- H3: inner/outer loops separate evidence and meaning production.
- H4: reports are the governance interface that closes the human loop.

Full control cycle:

```text
Human value signal
  → AI inner loop produces evidence
  → AI outer loop produces meaning
  → AI report compresses meaning into governance interface
  → Human updates value signal
  → AI reprioritizes work
```

## Reusable Report Template

```markdown
# Progress Report: <project/title>

## 1. Objective and value function
- Objective:
- Audience:
- Success criteria:
- Constraints:

## 2. What changed since last report
- New evidence:
- New synthesis:
- Updated hypotheses:

## 3. Key findings
| Claim | Evidence | Confidence | Artifact links |
|---|---|---|---|

## 4. Negative results and ruled-out paths
- What failed:
- What this rules out:
- What not to repeat:

## 5. Open questions and uncertainty
- Unresolved issues:
- Weak assumptions:
- Risks:

## 6. Direction recommendation
- Deepen / Broaden / Pivot / Conclude:
- Rationale:

## 7. Human feedback requested
- Decision options:
- Most useful feedback:

## 8. Next autonomous actions
- If no correction arrives, AI will:
```

## H4 Verdict

H4 is supported.

Progress reports are the primary governance interface because they are the artifact where AI-produced meaning becomes human-consumable direction control. They close the value-signal loop without requiring the human to inspect every low-level action.
