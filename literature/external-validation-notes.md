# External Literature Validation Notes

## Purpose

This note strengthens the **Stateful Value-Signal Research Loop** framework by connecting it to adjacent research and standards traditions. Web search identified relevant primary-source targets, but direct page fetching was blocked by network/domain verification policy, so these notes should be treated as preliminary literature grounding pending full citation extraction.

## 1. Mixed-Initiative Interaction

Target source: Eric Horvitz, “Principles of Mixed-Initiative User Interfaces” (Microsoft Research, 1999).

URL: https://www.microsoft.com/en-us/research/publication/principles-of-mixed-initiative-user-interfaces/

### Relevance

Mixed-initiative interaction studies systems where humans and computational agents share control over problem solving. This supports the H2 finding that `/autoresearch` is neither pure command execution nor full autonomy. Instead, initiative shifts by layer:

- Human initiative: goals, values, constraints, feedback, direction changes.
- AI initiative: search, artifact maintenance, local execution, synthesis, report generation.

### Connection to framework

The Stateful Value-Signal Research Loop can be understood as a specialized mixed-initiative architecture for long-running research tasks. It partitions initiative not by individual action, but by epistemic layer:

```text
Human controls value and governance.
AI controls routine evidence and synthesis production.
Reports transfer initiative back to the human at decision points.
```

## 2. Provenance and Traceability

Target source: W3C PROV Overview.

URL: https://www.w3.org/TR/prov-overview/

### Relevance

The W3C PROV model centers on provenance relationships among entities, activities, and agents. This directly supports the H1 finding that research artifacts are not merely files; they encode a traceable relationship between who/what produced something, what action produced it, and what downstream claim depends on it.

### Connection to framework

`/autoresearch` implements a lightweight provenance architecture:

| PROV-like concept | `/autoresearch` equivalent |
|---|---|
| Entity | artifact, result file, report, findings entry |
| Activity | experiment, literature search, outer-loop synthesis |
| Agent | AI assistant, human reviewer, domain skill |
| Derivation | result → analysis → findings → report |

This strengthens the claim that `research-log.md`, `experiments/*/protocol.md`, `analysis.md`, and `data/` are governance infrastructure, not housekeeping.

## 3. AI Risk Management and Human Oversight

Target source: NIST AI Risk Management Framework.

URL: https://www.nist.gov/itl/ai-risk-management-framework

### Relevance

AI governance frameworks emphasize monitoring, risk management, accountability, and human oversight. This supports H4: progress reports are governance interfaces. A long-running AI system needs mechanisms for humans to understand status, uncertainty, evidence, and risk without inspecting every low-level operation.

### Connection to framework

The H4 governance report template maps naturally to risk-management concerns:

- Objective and constraints → scope and intended use.
- Evidence summary → basis for trust calibration.
- Open questions and risks → uncertainty disclosure.
- Direction recommendation → human oversight point.
- Next autonomous actions → expectation setting and monitoring.

## 4. Distributed Cognition and Artifact-Mediated Work

Potential source family: distributed cognition and artifact-mediated collaboration literature.

### Relevance

The framework's H1 result aligns with the idea that cognition in complex work is distributed across humans, tools, representations, and artifacts. In `/autoresearch`, durable files externalize memory and make reasoning inspectable.

### Connection to framework

The research workspace is a cognitive system:

```text
human values + AI operations + artifact memory + reports + feedback
```

This gives theoretical support to the claim that the workspace itself is part of the intelligence of the research process.

## Synthesis

The external context supports the four-part framework:

| Framework element | External grounding |
|---|---|
| H1 Artifact interfaces | Provenance, traceability, distributed cognition |
| H2 Value-signal exchange | Mixed-initiative interaction |
| H3 Evidence/meaning loops | Scientific workflow and iterative inquiry traditions |
| H4 Governance reports | AI risk management and human oversight |

## Next literature tasks

For academic paper development, the next step should be full source verification and citation extraction for:

1. Horvitz, mixed-initiative user interfaces.
2. W3C PROV documents.
3. NIST AI RMF.
4. Distributed cognition / external representations.
5. Scientific workflow provenance and experiment tracking.
