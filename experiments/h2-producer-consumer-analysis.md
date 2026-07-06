# H2 Analysis: Human-AI Collaboration as Asymmetric Producer-Consumer Exchange

## Result

H2 is **supported with refinement**.

The producer-consumer model explains `/autoresearch` better than three common alternatives: command-execution, delegation-only, and stepwise approval-flow. However, the model should be refined: humans and AI are not fixed producers or consumers. They alternate roles across layers. The asymmetry is that humans primarily produce **value signals** and consume **compressed meaning**, while AI primarily consumes **value signals** and produces **stateful research artifacts**.

## Model Compared Against Alternatives

| Model | Human Role | AI Role | Strength | Failure Mode for `/autoresearch` |
|---|---|---|---|---|
| Command-execution | Issues detailed instructions | Executes tasks | High human control | Collapses autonomy; human becomes bottleneck; no sustained research momentum |
| Delegation-only | Gives broad goal, waits for result | Works independently | Efficient for bounded tasks | Governance gap; human cannot inspect trajectory or correct drift early |
| Stepwise approval-flow | Approves each step | Requests permission frequently | Safer for irreversible actions | Interrupts research rhythm; converts research into queue of approvals |
| Producer-consumer exchange | Produces values/constraints, consumes syntheses | Produces artifacts/evidence/synthesis, consumes goals/feedback | Balances autonomy and steering | Requires good artifact hygiene and clear report cadence |

## Why H2 Explains `/autoresearch` Best

`/autoresearch` is designed for open-ended research, where the path is not known in advance. This makes command-execution insufficient: the human cannot specify all steps upfront because discovering the steps is part of the work.

Delegation-only is also insufficient because open-ended research can drift, overfit to easy metrics, or generate activity without insight. The human needs periodic interfaces for steering.

Stepwise approval-flow is too slow for exploratory research. It may be appropriate for high-risk actions, but it breaks the skill's core rhythm of autonomous inner loops and periodic outer-loop synthesis.

The producer-consumer model fits because it separates **control by value function** from **control by procedure**:

```text
Human controls what counts as valuable.
AI controls the routine production of evidence, state, and synthesis.
Human periodically consumes compressed meaning and updates the value signal.
```

## Layered Producer-Consumer Roles

| Layer | Human Produces | AI Consumes | AI Produces | Human Consumes |
|---|---|---|---|---|
| Goal layer | Research intent, desired contribution | Objective and constraints | Research question and plan | Framing for approval or correction |
| Value layer | Success criteria, audience, tradeoffs | Value function | Prioritized hypotheses | Decision options |
| Execution layer | Resource/risk boundaries | Constraints | Protocols, experiments, logs | Usually not consumed directly |
| Synthesis layer | Feedback on usefulness | Directional signal | `findings.md`, patterns, lessons | Understanding and confidence |
| Governance layer | High-level steering | Updated priorities | Reports, plots, recommendations | Progress and next-step choices |
| Dissemination layer | Publication/communication goals | Target format | Paper/report drafts | Final artifact |

## Key Mechanism: Control Without Micromanagement

The model's most important explanatory feature is **control without micromanagement**.

Humans retain control by defining:

- what matters;
- what is out of scope;
- what risks are unacceptable;
- what evidence would be convincing;
- what audience the work serves.

AI receives autonomy over:

- routine search;
- artifact updates;
- experiment design within constraints;
- synthesis;
- report generation;
- proposing pivots.

This division preserves human responsibility while avoiding human bottlenecks.

## Failure Modes Explained by H2

### 1. Under-specified value function

If the human only says "research this" without target audience, usefulness criteria, or constraints, AI may produce plausible but misaligned work.

**Symptom:** lots of output, unclear value.

**Fix:** ask for or infer a sharper value function and record it in `research-state.yaml`.

### 2. Human micromanagement

If the human directs every step, the AI cannot run the inner loop effectively.

**Symptom:** slow progress, shallow exploration, AI behaves like a passive executor.

**Fix:** move human intervention to report review and high-level steering.

### 3. Artifact neglect

If the AI produces results but does not update state, findings, and reports, the human cannot consume the work at the right abstraction level.

**Symptom:** work happened, but understanding did not accumulate.

**Fix:** treat artifact updates as first-class outputs, not afterthoughts.

### 4. Approval overuse

If every reversible research step requires approval, the system loses momentum.

**Symptom:** queue of small decisions; human becomes scheduler.

**Fix:** reserve approval for irreversible, expensive, external, or risky actions.

### 5. Autonomy without governance

If AI runs too long without synthesis, it may optimize activity rather than insight.

**Symptom:** many experiments, weak narrative.

**Fix:** enforce outer-loop reflection and human-facing reports.

## Design Principle Derived from H2

For long-running AI skills, design the interaction around **value-signal exchange**, not command transfer.

A reusable interaction contract:

```text
Human must provide or refine:
  - Objective
  - Audience
  - Success criteria
  - Constraints
  - Feedback cadence

AI must provide:
  - State updates
  - Evidence packages
  - Synthesis
  - Decision options
  - Human-facing reports
```

## H2 Verdict

H2 is supported.

The producer-consumer model explains both why `/autoresearch` can operate autonomously and why it still needs human governance. It also explains common misuse patterns: too little human value specification causes drift, while too much procedural control destroys the system's autonomy advantage.

## Refinement

The phrase "human as producer, AI as producer" should not be treated statically. The better formulation is:

> Humans primarily produce value signals and consume compressed meaning; AI primarily consumes value signals and produces stateful research artifacts.

This refined H2 should become central to the final framework.
