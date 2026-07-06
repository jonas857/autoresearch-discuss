# H1 Analysis: Stateful Artifacts Are the Core Interaction Medium

## Result

H1 is **supported** by conceptual artifact mapping.

The `/autoresearch` skill's artifacts are not arbitrary project files. They form a layered interaction architecture in which each artifact serves a distinct producer-consumer function. The core mechanism is that long-running research cannot remain only in conversation: it must be externalized into durable, role-specific objects that different consumers can read at different levels of compression.

## Artifact Function Map

| Artifact | Producer | Primary Consumer | Compression Level | Uncertainty Reduced | Capability Lost If Absent |
|---|---|---|---|---|---|
| `research-state.yaml` | AI | AI | Operational state | "Where are we and what should happen next?" | Resumability, continuity across loop ticks, unambiguous next action selection |
| `research-log.md` | AI | Human auditor + AI | Chronological trace | "Why did we make this decision?" | Decision provenance, accountability, ability to reconstruct pivots |
| `findings.md` | AI | AI + human | Synthesized understanding | "What do we currently know?" | Cross-experiment learning, prevention of repeated mistakes, coherent narrative formation |
| `literature/` | AI | AI + paper writer | Source-backed context | "What is already known externally?" | Grounding, citation trail, avoidance of reinventing or hallucinating claims |
| `experiments/` | AI | AI + reproducibility reviewer | Evidence package | "What was tested and what happened?" | Confirmatory discipline, result traceability, reproducibility |
| `src/` | AI | AI developer/executor | Reusable code layer | "What utilities should be reused rather than duplicated?" | Code reuse, consistency, maintainability across experiments |
| `data/` | AI | AI analyst + paper writer | Raw or semi-structured evidence | "What measurements support the claims?" | Re-analysis, plotting, independent verification |
| `to_human/` | AI | Human | Human-facing synthesis | "What should the human know and decide?" | Human governance, strategic steering, trust calibration |
| `paper/` | AI + human | Publication audience | Final narrative | "What is the durable contribution?" | Final dissemination and contribution packaging |

## Key Finding: Artifacts Are Consumer Interfaces

The most important refinement to H1 is that artifacts should not be viewed as passive storage. They are **consumer interfaces**.

Each file or directory answers three design questions:

1. Who needs to consume this information?
2. At what level of compression do they need it?
3. What future action does this artifact enable?

For example:

- `research-state.yaml` is not a report. It is an operational control surface for the AI.
- `findings.md` is not a log. It is a cognitive compression layer shared by AI and human.
- `to_human/` is not archival storage. It is the governance interface through which humans steer without micromanaging.

## Why Conversation Alone Is Insufficient

A pure chat transcript fails as the primary medium for long-running research because it is:

1. **Linear** — hard to separate state, evidence, synthesis, and presentation.
2. **Context-window dependent** — earlier details may be compressed or lost.
3. **Consumer-undifferentiated** — the AI's next-action state and the human's progress summary are mixed together.
4. **Weakly auditable** — protocols, results, and pivots are harder to inspect as distinct objects.
5. **Hard to resume** — a future loop tick needs concise machine-readable state, not an entire conversation.

The artifact architecture solves this by creating a file-based external memory with specialized views.

## Producer-Consumer Interpretation

H1 strengthens the broader producer-consumer model:

```text
AI produces artifacts → each artifact becomes a consumable interface → AI or human consumes it for a specific next action
```

This means the workflow is not simply:

```text
AI does research → AI writes report
```

It is closer to:

```text
AI continuously manufactures state, evidence, synthesis, and governance surfaces for different downstream consumers
```

## Artifact Dependency Stack

The artifacts form a stack:

```text
Raw evidence layer:
  data/, experiment results, logs

Protocol and reproducibility layer:
  experiments/*/protocol.md, analysis.md

Operational state layer:
  research-state.yaml

Cognitive synthesis layer:
  findings.md

Governance and communication layer:
  to_human/*.html or *.pdf

Final contribution layer:
  paper/
```

Lower layers preserve evidence. Middle layers enable continuity and understanding. Upper layers enable human governance and dissemination.

## Design Principle Derived from H1

For long-running AI skills, every persistent artifact should have a declared consumer and decision function.

A useful template:

```text
Artifact: <name>
Producer: <who creates/updates it>
Consumer: <who reads it>
Compression level: <raw / operational / synthesized / presentation>
Decision enabled: <what action becomes possible because this artifact exists>
Failure if missing: <what breaks without it>
```

This can become a reusable design pattern for future AI skills.

## H1 Verdict

H1 is supported.

The evidence is conceptual but strong: the `/autoresearch` workflow depends on artifacts that map cleanly to different consumers, compression levels, and decision functions. The research system would lose continuity, auditability, synthesis, reproducibility, or governance if these artifacts were collapsed back into a single chat stream.

## New Questions Raised

1. Can we define a minimal artifact set for lighter-weight autoresearch?
2. When do too many artifacts create overhead rather than clarity?
3. Can artifact health be measured, e.g. stale state, missing protocol, weak findings, unreadable report?
4. Should every long-running AI skill declare its artifact schema upfront?
5. How should the AI decide when an artifact needs updating?
