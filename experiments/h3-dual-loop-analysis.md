# H3 Analysis: Dual-Loop Architecture Separates Evidence Production from Meaning Production

## Result

H3 is **supported**.

The `/autoresearch` dual-loop architecture is not just a scheduling pattern. It separates two different forms of research production:

1. The **inner loop** produces evidence.
2. The **outer loop** produces meaning.

This distinction explains why `/autoresearch` can support open-ended research rather than merely execute a task list.

## Inner Loop: Evidence Production

The inner loop performs fast, local, bounded work:

```text
Pick hypothesis → write protocol → run experiment/analysis → sanity check → measure → record → update state
```

Its main products are evidence artifacts:

| Inner-loop step | Main output | Artifact target | Function |
|---|---|---|---|
| Pick hypothesis | selected test target | `research-state.yaml` | narrows action space |
| Write protocol | prediction and method | `experiments/*/protocol.md` | precommits expectation |
| Run experiment/analysis | observations and outputs | `experiments/*/results/`, `data/` | produces evidence |
| Sanity check | validity assessment | `analysis.md`, logs | filters bad evidence |
| Measure metric | comparable result | trajectory data | supports trend analysis |
| Record result | local interpretation | `experiments/*/analysis.md` | preserves what happened |
| Update state | next operational step | `research-state.yaml` | enables continuation |

The inner loop is optimized for throughput, concreteness, and local validity.

## Outer Loop: Meaning Production

The outer loop performs slower, global, interpretive work:

```text
Review results → cluster patterns → ask why → update findings → search literature if needed → generate new hypotheses → decide direction
```

Its main products are meaning artifacts:

| Outer-loop step | Main output | Artifact target | Function |
|---|---|---|---|
| Review results | cross-run comparison | `findings.md` | identifies signal across evidence |
| Cluster patterns | abstraction | `findings.md` | converts results into concepts |
| Ask why | mechanism hypothesis | `findings.md`, new protocols | creates explanation |
| Revisit literature | external grounding | `literature/` | prevents isolated speculation |
| Generate hypotheses | new research options | `research-state.yaml` | expands future search space |
| Decide direction | deepen/broaden/pivot/conclude | `research-log.md`, `research-state.yaml` | governs trajectory |
| Report to human | compressed meaning | `to_human/` | enables oversight and steering |

The outer loop is optimized for interpretation, prioritization, and narrative coherence.

## Why a Single Loop Is Insufficient

### Single evidence loop failure

If the system only runs inner-loop experiments, it may produce many results without a story.

```text
Symptom: many protocols and metrics, weak findings.md
Failure: activity substitutes for understanding
```

### Single reflection loop failure

If the system only reflects, it may produce elegant frameworks without grounding.

```text
Symptom: rich narrative, little evidence or traceability
Failure: speculation substitutes for research
```

### Mixed unstructured loop failure

If evidence and meaning are not separated, the workflow becomes hard to govern.

```text
Symptom: every result triggers a pivot or every reflection gets buried in logs
Failure: unstable direction or no synthesis layer
```

The dual-loop design avoids these by giving evidence production and meaning production different cadences.

## H3 and the Human-AI Interaction Model

H3 integrates with H1 and H2:

- H1 says artifacts are consumer interfaces.
- H2 says interaction is value-signal exchange.
- H3 says loops determine when artifacts are produced and when value signals are updated.

Together:

```text
Inner loop produces evidence artifacts.
Outer loop converts evidence into meaning artifacts.
Human consumes meaning artifacts and produces updated value signals.
AI uses value signals to prioritize the next inner loop.
```

This closes the full research control cycle.

## Direction Decisions Belong to the Outer Loop

The `/autoresearch` skill defines four direction choices:

| Direction | Meaning | Why outer-loop? |
|---|---|---|
| DEEPEN | supported result raises follow-up questions | requires cross-result interpretation |
| BROADEN | current result is solid but adjacent areas remain | requires map of unexplored space |
| PIVOT | assumptions failed or better question appeared | requires model revision |
| CONCLUDE | evidence supports a coherent contribution | requires narrative and sufficiency judgment |

These decisions should not be made after every individual result. They require synthesized understanding.

## Design Principle Derived from H3

For long-running AI skills, separate loops by epistemic function:

```text
Inner loop: produce valid local evidence.
Outer loop: produce global meaning and direction.
Human loop: evaluate compressed meaning and update value signals.
```

A useful diagnostic:

- If there is lots of output but no improving `findings.md`, the outer loop is weak.
- If there is lots of synthesis but little protocol/result evidence, the inner loop is weak.
- If reports exist but do not change priorities, the human governance loop is weak.

## H3 Verdict

H3 is supported.

The dual-loop architecture explains how `/autoresearch` avoids both blind experimentation and ungrounded reflection. It turns open-ended research into a rhythm: evidence accumulation, meaning synthesis, value-signal update, and renewed evidence production.

## New Questions Raised

1. What cadence should trigger the outer loop: number of experiments, time interval, surprise, or stagnation?
2. Can loop health be measured by artifact freshness and cross-link density?
3. Should different research types use different inner/outer loop ratios?
4. How should the AI detect that it is optimizing a metric but not increasing understanding?
