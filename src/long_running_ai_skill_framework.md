# Reusable Framework: Designing Long-Running AI Research Skills

## Purpose

This framework generalizes lessons from analyzing `/autoresearch`. It can guide the design of other long-running AI skills that must operate autonomously while remaining governable by humans.

## Core Thesis

A long-running AI skill should not be designed as a command executor. It should be designed as a **stateful value-signal processing system**:

```text
Human value signal → AI evidence production → AI meaning synthesis → human governance → updated value signal
```

## Three Pillars

### Pillar 1 — Artifact Interfaces

Every persistent artifact should be designed as a consumer interface.

Template:

```text
Artifact: <name>
Producer: <who creates/updates it>
Consumer: <who reads it>
Compression level: <raw / operational / synthesized / presentation / final>
Decision enabled: <what action becomes possible>
Failure if missing: <what capability breaks>
Update cadence: <when it should be refreshed>
```

Minimum artifact stack:

| Layer | Artifact | Purpose |
|---|---|---|
| Operational state | `state.yaml` | resume and choose next actions |
| Decision trace | `log.md` | explain why choices were made |
| Synthesis | `findings.md` | preserve current understanding |
| Evidence | `experiments/`, `data/` | ground claims |
| Human governance | `to_human/` | support steering |
| Final output | `paper/` or `deliverable/` | package contribution |

### Pillar 2 — Value-Signal Exchange

Humans should control value and boundaries. AI should control routine production within those boundaries.

Human must provide or refine:

- objective;
- audience;
- success criteria;
- constraints;
- risk boundaries;
- feedback cadence.

AI must provide:

- state updates;
- evidence packages;
- synthesis;
- decision options;
- reports;
- recommended next actions.

Principle:

```text
Control by value function, not by step-by-step procedure.
```

### Pillar 3 — Epistemic Loop Separation

Separate loops by function:

| Loop | Function | Main artifacts | Failure if weak |
|---|---|---|---|
| Inner loop | produce local evidence | protocols, results, data, local analyses | no grounding |
| Outer loop | produce global meaning | findings, updated hypotheses, direction decisions | no understanding |
| Human loop | update value signal | reports, feedback, constraints | no governance |

Design rule:

```text
Do not ask one loop to do all cognitive work.
```

## Combined Operating Cycle

```text
1. Human supplies value signal
   - objective
   - audience
   - constraints
   - success criteria

2. AI initializes artifact stack
   - state
   - log
   - findings
   - evidence directories
   - report directory

3. AI runs inner loop
   - choose hypothesis
   - write protocol
   - execute bounded work
   - sanity check
   - record evidence

4. AI runs outer loop
   - compare results
   - identify patterns
   - update findings
   - decide deepen/broaden/pivot/conclude

5. AI generates human-facing report
   - key findings
   - evidence
   - uncertainty
   - decision options

6. Human updates value signal
   - approve direction
   - redirect
   - narrow scope
   - change success criteria

7. AI repeats with updated priorities
```

## Diagnostic Questions

### Artifact Health

- Does each artifact have a clear consumer?
- Is `state.yaml` current enough to resume work?
- Does `findings.md` synthesize rather than log?
- Are protocols and results separated?
- Are human reports meaningful rather than activity dumps?

### Value-Signal Health

- Is the human objective explicit?
- Is the audience known?
- Are success criteria defined?
- Are constraints and risk boundaries recorded?
- Has human feedback changed priorities?

### Loop Health

- Is the inner loop producing evidence?
- Is the outer loop producing new understanding?
- Is the human loop producing updated direction?
- Is the system stuck in activity without insight?
- Is the system stuck in reflection without evidence?

## Common Failure Modes and Fixes

| Failure mode | Symptom | Likely cause | Fix |
|---|---|---|---|
| Output without value | many files, unclear usefulness | weak value signal | clarify objective/audience/success criteria |
| Activity without understanding | many experiments, thin findings | weak outer loop | force synthesis and pattern review |
| Framework without grounding | elegant report, little evidence | weak inner loop | add protocols, tests, or case evidence |
| Human bottleneck | frequent small approvals | overused approval loop | reserve approval for high-risk decisions |
| AI drift | work no longer matches goal | stale value signal or weak reports | generate report and request/derive steering |
| Memory decay | repeats old mistakes | stale findings/state | update findings and log after each reflection |

## Design Pattern Name

**Stateful Value-Signal Research Loop**

Definition:

> A long-running AI interaction pattern in which humans provide value signals and governance, AI maintains artifact-mediated state, inner loops produce evidence, outer loops produce meaning, and human-facing reports close the steering loop.

## Application Beyond `/autoresearch`

This pattern can apply to:

- autonomous coding agents;
- product discovery agents;
- data science agents;
- literature review agents;
- security audit agents;
- course-building agents;
- long-running personal assistants.

Any domain where work is open-ended, multi-step, and uncertainty-reducing can benefit from this pattern.
