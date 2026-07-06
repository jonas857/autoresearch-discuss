# Findings

## Current Understanding

`/autoresearch` is best understood not as a one-shot research-answering command, but as a stateful human-AI research operating system. It converts an open-ended human intention into an ongoing process of literature search, hypothesis formation, experiment execution, synthesis, reporting, and eventual paper writing.

The key interaction pattern is not:

```text
Human asks → AI answers
```

but:

```text
Human defines value and boundaries → AI continuously produces structured research work → human periodically consumes compressed insight and redirects if needed
```

H1 validation adds an important refinement: the workflow's files are not merely storage; they are **consumer interfaces**. Each artifact exists because a particular downstream consumer—AI operator, human reviewer, paper writer, reproducibility auditor, or future session—needs information at a particular level of compression to make a particular decision.

H3 validation adds a second refinement: the workflow's loops are not merely scheduling devices; they separate **evidence production** from **meaning production**. The inner loop produces local evidence, while the outer loop produces global interpretation and direction.

H4 validation completes the control model: human-facing progress reports are not decorative summaries; they are the **governance interface** where AI-produced meaning becomes human-consumable steering information.

## First-Principles Model

Any human-AI research workflow can be reduced to four primitives:

1. **Goal** — what should be accomplished?
2. **Information** — what is known and unknown?
3. **Action** — what should be done next?
4. **Feedback** — did the action reduce uncertainty or require a pivot?

`/autoresearch` operationalizes these primitives through persistent artifacts and recurring loops.

## Producer-Consumer Decomposition

### Human as Producer

Humans primarily produce:

- Research intent
- Value function
- Constraints
- Domain background
- Feedback and direction changes
- Final judgment of usefulness

These are high-leverage inputs because they define what counts as progress.

### AI as Consumer of Human Inputs

The AI consumes human-produced intent, value functions, constraints, and background, then turns them into:

- Research questions
- State files
- Hypotheses
- Experiment protocols
- Literature notes
- Progress reports

### AI as Producer

The AI primarily produces:

- Structured research questions
- Literature summaries
- Hypotheses
- Experiment protocols
- Code and results, when applicable
- Analysis and synthesis
- `findings.md` updates
- Human-facing reports
- Paper drafts

### Human as Consumer

Humans should mostly consume:

- Synthesized findings
- Progress reports
- Decision options
- Evidence-backed recommendations

Humans should not need to consume every low-level step unless diagnosing failure.

### H2 Validation Update: Value-Signal Exchange

H2 is currently **supported with refinement**. The producer-consumer model explains `/autoresearch` better than command-execution, delegation-only, or stepwise approval-flow models.

The refined formulation is:

> Humans primarily produce value signals and consume compressed meaning; AI primarily consumes value signals and produces stateful research artifacts.

This matters because `/autoresearch` is not just delegation. It is a repeated value-signal exchange:

```text
Human value signal → AI research production → compressed meaning → human steering signal → AI reprioritization
```

The model explains key failure modes:

- Under-specified human value function → lots of output, unclear usefulness.
- Human micromanagement → slow progress and lost autonomy advantage.
- Artifact neglect → work happens but understanding does not accumulate.
- Approval overuse → research becomes a queue of small permissions.
- Autonomy without governance → many experiments but weak narrative.

## Artifact Layering Insight

The skill separates information by consumer type:

| Artifact | Primary Consumer | Role |
|---|---|---|
| `research-state.yaml` | AI | Machine-readable state and next actions |
| `research-log.md` | AI + human auditor | Decision timeline and traceability |
| `findings.md` | AI + human | Accumulated research understanding |
| `literature/` | AI + future paper writer | Source-backed context |
| `experiments/` | AI + reproducibility reviewer | Protocols, results, and analyses |
| `to_human/` | Human | High-level progress and decision interface |
| `paper/` | Human + publication audience | Final research synthesis |

This layering is central: each artifact exists because a different consumer needs a different level of compression.

### H1 Validation Update: Artifacts as Consumer Interfaces

H1 is currently **supported** by artifact mapping. The major artifacts form a stack of distinct consumer interfaces:

```text
Raw evidence layer: data/, experiment outputs
Protocol/reproducibility layer: experiments/*/protocol.md, analysis.md
Operational state layer: research-state.yaml
Cognitive synthesis layer: findings.md
Governance layer: to_human/*.html or *.pdf
Final contribution layer: paper/
```

The strongest insight is that artifact design should start from consumer need, not file convention. For every durable artifact, the system should be able to answer:

1. Who consumes this?
2. What level of compression do they need?
3. What decision or next action does this artifact enable?
4. What capability breaks if the artifact is absent?

This supports the claim that `/autoresearch` converts chat into a research operating system by externalizing memory into role-specific objects.

## Dual-Loop Architecture Insight

H3 is currently **supported**. The dual-loop architecture separates two different forms of research production:

| Loop | Function | Main Product | Main Artifact |
|---|---|---|---|
| Inner loop | Evidence production | protocols, measurements, local analyses | `experiments/`, `data/`, `research-state.yaml` |
| Outer loop | Meaning production | patterns, mechanisms, direction decisions | `findings.md`, `research-log.md`, `to_human/` |
| Human loop | Value-signal update | steering, constraints, success criteria | human feedback, updated `research-state.yaml` |

The key rhythm is:

```text
Inner loop produces evidence → outer loop produces meaning → human consumes meaning and updates value signal → AI reprioritizes the next inner loop
```

This prevents two opposite failures:

- Blind experimentation: many results without understanding.
- Ungrounded reflection: elegant frameworks without evidence.

Direction decisions such as DEEPEN, BROADEN, PIVOT, and CONCLUDE belong to the outer loop because they require cross-result interpretation rather than a single local result.

## Governance Report Interface Insight

H4 is currently **supported**. Progress reports are the primary governance interface for `/autoresearch`.

A report is not just a presentation artifact. It is the point where internal AI work becomes human-steerable:

```text
Internal artifacts → report synthesis → human judgment → updated value signal → AI reprioritization
```

A good progress report answers governance questions:

| Report component | Human question answered | Governance function |
|---|---|---|
| Objective | Are we still solving the right problem? | goal alignment |
| Current status | Where are we? | orientation |
| Key findings | What has been learned? | meaning consumption |
| Evidence summary | Why should I believe this? | trust calibration |
| Negative results | What has been ruled out? | prevents repeated waste |
| Open questions | What remains uncertain? | risk awareness |
| Direction recommendation | Deepen, broaden, pivot, or conclude? | steering |
| Next actions | What happens if I do nothing? | expectation setting |
| Human decision points | What input is needed from me? | value-signal update |
| Artifact links | Where can I inspect details? | auditability |

Report-based governance is superior to step-by-step approval for routine research because it preserves autonomy. It is superior to full autonomy because it preserves human responsibility and direction control.

## Emerging Pattern

The highest-value human-AI interaction is **low-frequency, high-level human steering** combined with **high-frequency, low-level AI execution**.

Poor usage pattern:

```text
Human micromanages every step → AI becomes a passive assistant → research loop slows down
```

Better usage pattern:

```text
Human defines objective and constraints → AI autonomously iterates → human reviews reports and adjusts direction
```

The deeper pattern is **control without micromanagement**. Humans retain control by defining what matters, what is out of scope, what risks are unacceptable, what evidence would be convincing, and what audience the work serves. AI receives autonomy over routine search, artifact maintenance, experiment design within constraints, synthesis, and report generation.

## Lessons and Constraints

- The human's most important contribution is not task decomposition; it is defining the value function.
- The AI's most important contribution is not merely speed; it is maintaining state, compressing information, and sustaining iteration.
- `findings.md` should not become a raw log. It must remain a synthesis layer.
- `research-state.yaml` should stay operational and concise enough for the AI to resume from it.
- Human-facing reports should present meaning, not just activity.
- Every artifact in a long-running AI skill should declare its consumer, compression level, decision function, and failure mode if missing.
- Conversation alone is insufficient for long-horizon research because it is linear, context-window dependent, consumer-undifferentiated, weakly auditable, and hard to resume.
- Long-running AI skills should be designed around value-signal exchange rather than command transfer: human supplies objective/audience/success criteria/constraints/feedback cadence; AI supplies state updates/evidence/synthesis/decision options/reports.
- The producer-consumer roles are layered rather than static: humans and AI both produce and consume, but at different abstraction levels.
- Long-running AI skills should separate epistemic loops: inner loop for local evidence, outer loop for global meaning, human loop for value-signal update.
- A healthy research agent should be evaluated by artifact health, value-signal health, and loop health—not just by amount of output.
- Progress reports should be generated when they can change governance, not merely when activity occurred: after synthesis, surprise, pivot candidates, stagnation, or before expensive/irreversible actions.
- Good reports must include claims, evidence, uncertainty, direction recommendation, and human feedback surface; otherwise they become activity dumps or over-compressed assertions.

## Open Questions

1. Can the producer-consumer model become a general design pattern for long-running AI skills?
2. What is the optimal reporting cadence for human oversight?
3. How should the system detect when it is generating activity without increasing understanding?
4. What failure modes arise from over-autonomy versus over-control?
5. How can this conceptual model be validated through small simulations or case comparisons?
