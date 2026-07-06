# Context Notes for H2: Producer-Consumer Human-AI Collaboration

## Purpose

These notes connect the H2 producer-consumer model to adjacent interaction and governance concepts. Network fetching was attempted for external sources, but page fetches were blocked by domain verification/network policy. The concepts below should be treated as contextual scaffolding, not as finalized citation notes. A later literature pass should verify and expand them with primary sources.

## Adjacent Concept 1: Mixed-Initiative Interaction

Mixed-initiative systems study how humans and machines share initiative during problem solving. This is directly relevant to `/autoresearch` because the human should not issue every step, and the AI should not unilaterally determine the value of the research.

### Relevance to H2

The producer-consumer model can be read as a specific mixed-initiative pattern:

- Human initiative dominates at the value, goal, and steering layers.
- AI initiative dominates at the execution, synthesis, and artifact-maintenance layers.
- Initiative shifts back to the human at report-review and direction-change moments.

This suggests that effective `/autoresearch` interaction is not fully autonomous and not fully human-directed. It is initiative partitioned by layer.

## Adjacent Concept 2: Human-on-the-Loop Governance

Human-on-the-loop governance differs from human-in-the-loop control. In the latter, the human intervenes in each decision or action. In the former, the system operates autonomously within constraints, while the human monitors, audits, and intervenes at higher-level control points.

### Relevance to H2

`/autoresearch` is closer to human-on-the-loop than human-in-the-loop:

- The continuity loop keeps the AI moving without waiting for every approval.
- `to_human/` reports give humans a monitoring and steering interface.
- `research-state.yaml` and `findings.md` make the AI's trajectory inspectable.
- Human intervention should focus on direction, value, risk, and conclusion quality.

This supports the claim that progress reports are not optional summaries; they are governance artifacts.

## Adjacent Concept 3: Provenance and Traceability

Research workflows need provenance: a record of what was done, why it was done, what data was used, and how conclusions were derived.

### Relevance to H1 and H2

`research-log.md`, `experiments/*/protocol.md`, `analysis.md`, and `data/` form a lightweight provenance system.

This matters for producer-consumer logic because downstream consumers need trust:

- The human reviewer consumes the decision trail.
- The AI consumes prior decisions to avoid repeating mistakes.
- The paper writer consumes protocol and result history to construct a credible narrative.
- A reproducibility reviewer consumes experiment artifacts to inspect whether claims are grounded.

## Adjacent Concept 4: Artifact-Mediated Collaboration

In complex collaboration, participants often coordinate through shared artifacts rather than direct real-time conversation. Examples include design docs, issue trackers, experiment dashboards, decision logs, and reports.

### Relevance to `/autoresearch`

`/autoresearch` is artifact-mediated collaboration between human and AI. The files are not merely outputs; they are the shared work surface.

This reframes good usage:

```text
Do not only ask: "What did the AI say?"
Ask: "What artifacts did the AI update, and what future decisions do those artifacts enable?"
```

## Implication for Skill Design

A long-running AI skill should explicitly define:

1. Human-produced value signals.
2. AI-produced evidence and synthesis artifacts.
3. Shared artifacts that preserve state and provenance.
4. Human-facing governance reports.
5. A cadence for switching initiative between AI execution and human steering.

## Follow-up Literature Targets

The next literature pass should verify and summarize primary sources in:

- mixed-initiative user interfaces;
- human-on-the-loop AI governance;
- scientific workflow provenance;
- experiment tracking and reproducibility;
- artifact-mediated collaboration and distributed cognition.
