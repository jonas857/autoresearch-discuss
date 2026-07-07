# Stateful Value-Signal Research Loops: A Framework for Governable Long-Running AI Research Skills

## Abstract

Long-running AI work differs from single-turn question answering: goals evolve, evidence accumulates over time, intermediate results require interpretation, and human oversight must remain effective without reducing the AI system to a passive command executor. This paper develops the **Stateful Value-Signal Research Loop**, a conceptual framework derived from an analysis of the `/autoresearch` skill in Claude Code. The framework argues that governable long-running AI skills require four coupled mechanisms: (1) persistent artifacts designed as consumer interfaces, (2) human-AI collaboration organized as value-signal exchange, (3) separate inner and outer epistemic loops for evidence production and meaning production, and (4) progress reports as the primary human governance interface. We position the framework relative to mixed-initiative interaction, provenance standards, AI risk management, distributed cognition, cognitive artifacts, and scientific workflow provenance. The result is a reusable design template for AI systems that must autonomously make research progress while remaining inspectable, steerable, and accountable to human goals.

## 1. Introduction

Most interactive AI systems are still used through a question-answer pattern:

```text
Human asks → AI answers
```

This pattern is effective for bounded tasks such as summarization, code generation, explanation, and short analyses. It is insufficient for long-running research-like work. Research tasks are open-ended: the initial problem may be underspecified, the path is not known in advance, evidence can be noisy, and the value of intermediate results depends on later synthesis. A useful long-running AI skill therefore cannot merely answer a prompt. It must maintain state, accumulate evidence, revise understanding, expose uncertainty, and periodically return control-relevant information to a human reviewer.

The `/autoresearch` skill provides a concrete case of such a system. It initializes a research workspace, maintains `research-state.yaml`, `research-log.md`, `findings.md`, `literature/`, `experiments/`, `to_human/`, and `paper/`, and operates through a two-loop architecture: fast inner loops for evidence generation and slower outer loops for synthesis and direction setting.

This paper asks:

> How does `/autoresearch` mediate human-AI interaction through producer-consumer roles, stateful artifacts, and dual-loop research orchestration?

We answer by proposing the **Stateful Value-Signal Research Loop**:

```text
Human Value Signal
  → Artifact-Mediated State
  → Inner Loop Evidence
  → Outer Loop Meaning
  → Governance Report
  → Updated Value Signal
```

The framework's central claim is that long-running AI skills should be designed not as autonomous black boxes or step-by-step command executors, but as governable stateful systems where humans provide value signals and oversight while AI systems maintain artifacts, produce evidence, synthesize meaning, and return decision surfaces.

## 2. Related Work and Theoretical Grounding

This framework is not identical to any single prior tradition, but it is consistent with several established bodies of work.

### 2.1 Mixed-Initiative Interaction

Mixed-initiative interaction studies systems in which humans and computational agents share control over problem solving. Horvitz's work on principles of mixed-initiative user interfaces provides an important reference point for designing systems where initiative can shift between human and machine participants [@horvitz1999mixedinitiative]. The Stateful Value-Signal Research Loop applies this idea to long-running research tasks: humans hold initiative at the value, constraint, and governance layers, while the AI holds initiative at the routine evidence-production and synthesis layers. Reports become initiative-transfer surfaces, returning control-relevant context to the human.

### 2.2 Provenance and Traceability

The W3C PROV family provides a vocabulary for representing provenance through entities, activities, agents, and relations such as generation, use, derivation, attribution, and association [@w3cprov2013overview; @w3cprov2013dm; @w3cprov2013o]. This vocabulary directly supports the claim that research artifacts are not merely files. In a long-running AI workspace, artifacts such as protocols, results, findings, and reports are provenance-bearing objects. They help reconstruct what was done, what evidence was used, and how conclusions were derived.

### 2.3 AI Risk Management and Human Oversight

The NIST AI Risk Management Framework emphasizes governance, risk management, transparency, accountability, measurement, and socio-technical context [@nist2023airmf]. This supports the need for progress reports as governance interfaces. A long-running AI skill should not merely act; it should expose objective alignment, evidence, uncertainty, risk, and planned next actions so that human reviewers can monitor and steer the system.

### 2.4 Distributed Cognition and Cognitive Artifacts

Distributed cognition treats cognition as distributed across people, tools, representations, and environments [@hutchins1995cognition]. Norman's work on cognitive artifacts explains how external representations transform cognitive tasks [@norman1991cognitiveartifacts]. These ideas support the claim that the `/autoresearch` workspace is part of the cognitive system. Files such as `findings.md`, `research-state.yaml`, and progress reports do not merely store outputs; they structure memory, comparison, resumption, synthesis, and governance.

### 2.5 Scientific Workflow Provenance

Scientific workflow provenance research emphasizes the need to track data dependencies, execution context, parameters, outputs, and derivation histories [@davidson2008provenanceworkflows]. This strengthens the framework's claim that evidence loops need durable artifacts. Without provenance, a long-running AI research process cannot reliably compare results, explain decisions, or support later synthesis.

## 3. Method: Conceptual Analysis of `/autoresearch`

This work is a conceptual and design analysis rather than an empirical benchmark. We analyzed the `/autoresearch` skill as a structured human-AI workflow and tested four hypotheses through artifact mapping, interaction-model comparison, loop-function mapping, and governance-interface analysis.

The four hypotheses were:

- **H1:** Stateful artifacts are the core interaction medium.
- **H2:** Human-AI collaboration is an asymmetric producer-consumer exchange.
- **H3:** Dual-loop architecture separates evidence production from meaning production.
- **H4:** Progress reports are the primary governance interface.

The analysis proceeded by mapping each skill mechanism to its producer, consumer, epistemic function, and failure mode if absent. The result is a framework intended for design guidance rather than statistical generalization.

## 4. Framework

### 4.1 H1: Artifacts as Consumer Interfaces

The first mechanism is artifact-mediated state. `/autoresearch` uses a file workspace that includes state, logs, findings, literature, experiments, human reports, and final paper outputs. These artifacts are not passive storage. They are consumer interfaces.

| Artifact | Primary consumer | Function |
|---|---|---|
| `research-state.yaml` | AI | Operational state and next actions |
| `research-log.md` | AI + human auditor | Decision timeline and traceability |
| `findings.md` | AI + human | Accumulated understanding |
| `literature/` | AI + paper writer | External grounding |
| `experiments/` | AI + reproducibility reviewer | Protocols, evidence, results, analysis |
| `to_human/` | Human | Governance and steering interface |
| `paper/` | Publication audience | Final contribution packaging |

The design principle is:

> Do not design files first. Design consumers first.

Every persistent artifact should declare:

```yaml
producer:
consumer:
compression_level:
decision_enabled:
failure_if_missing:
update_cadence:
```

This makes artifact design a form of interaction design.

### 4.2 H2: Human-AI Collaboration as Value-Signal Exchange

The second mechanism is value-signal exchange. The human's most important role is not to decompose every step. It is to define what counts as valuable progress.

Humans primarily produce:

```yaml
objective:
audience:
success_criteria:
constraints:
risk_boundaries:
feedback_cadence:
```

AI primarily produces:

```yaml
state_updates:
evidence_packages:
synthesis:
decision_options:
governance_reports:
```

The interaction is:

```text
Human value signal
  → AI research production
  → compressed meaning
  → human steering signal
  → AI reprioritization
```

This model explains why pure command execution, pure delegation, and stepwise approval flows are all insufficient. Command execution makes the human a bottleneck. Pure delegation creates a governance gap. Stepwise approval protects control but destroys research momentum. Value-signal exchange preserves AI autonomy while retaining human direction-setting authority.

### 4.3 H3: Separating Evidence Production from Meaning Production

The third mechanism is epistemic loop separation. `/autoresearch` separates fast inner loops from slower outer loops.

| Loop | Function | Main product | Failure if weak |
|---|---|---|---|
| Inner loop | Produce evidence | protocols, measurements, local analyses | ungrounded reflection |
| Outer loop | Produce meaning | patterns, mechanisms, direction decisions | activity without understanding |
| Human loop | Update value signal | steering, constraints, priorities | drift |

The inner loop executes bounded work:

```text
Select hypothesis → write protocol → execute → sanity check → measure → record
```

The outer loop synthesizes:

```text
Review results → cluster patterns → explain → update findings → decide direction
```

This separation prevents two opposing failures: blind experimentation without understanding and elegant reflection without evidence.

### 4.4 H4: Progress Reports as Governance Interfaces

The fourth mechanism is report-based governance. Progress reports are not summaries for convenience. They are the primary human governance interface.

```text
Internal artifacts
  → report synthesis
  → human judgment
  → updated value signal
  → AI reprioritization
```

A useful report answers:

| Report component | Human question | Governance function |
|---|---|---|
| Objective | Are we still solving the right problem? | goal alignment |
| Current status | Where are we? | orientation |
| Key findings | What has been learned? | meaning consumption |
| Evidence summary | Why should I believe this? | trust calibration |
| Negative results | What has been ruled out? | avoids repeated waste |
| Open questions | What remains uncertain? | risk awareness |
| Direction recommendation | Deepen, broaden, pivot, or conclude? | steering |
| Next actions | What happens if I do nothing? | expectation setting |
| Human decision points | What input is needed from me? | value-signal update |
| Artifact links | Where can I inspect details? | auditability |

Report-based governance is superior to step-by-step approval for routine research because it preserves autonomy. It is superior to full autonomy because it preserves human responsibility and direction control.

## 5. The Stateful Value-Signal Research Loop

Combining H1-H4 yields the final framework:

```text
Human Value Signal
  → Artifact-Mediated State
  → Inner Loop Evidence
  → Outer Loop Meaning
  → Governance Report
  → Updated Value Signal
```

The framework can be defined as:

> A long-running AI interaction pattern in which humans provide value signals and governance, AI maintains artifact-mediated state, inner loops produce evidence, outer loops produce meaning, and governance reports close the human steering loop.

This framework is useful because it clarifies the difference between autonomy and governability. The AI may autonomously execute many low-level actions, but the system remains governed because value signals, artifacts, evidence, synthesis, and reports are structured for human inspection and steering.

## 6. Design Implications

### 6.1 Design the Artifact Schema Explicitly

Every long-running AI skill should specify the artifacts it will maintain. At minimum, such systems need:

- operational state;
- decision log;
- findings/synthesis document;
- evidence directory;
- human report directory;
- final deliverable directory.

### 6.2 Separate Control by Value from Control by Procedure

Human reviewers should not be forced to approve every step. They should define objectives, constraints, success criteria, and risk boundaries. AI systems should expose their planned next actions and seek approval only for high-risk, irreversible, expensive, or externally visible actions.

### 6.3 Treat Synthesis as a Required Operation

A long-running AI skill should not equate activity with progress. It should periodically update a synthesis artifact that explains what has been learned, what failed, what remains uncertain, and what direction is recommended.

### 6.4 Make Reports Decision-Oriented

Reports should include a decision surface. A report that lists actions without claims, evidence, uncertainty, or options is an activity dump, not a governance interface.

## 7. Failure Modes

| Failure mode | Symptom | Cause | Fix |
|---|---|---|---|
| Output without value | many artifacts, unclear usefulness | weak value signal | clarify objective, audience, success criteria |
| Activity without understanding | many experiments, thin findings | weak outer loop | force synthesis and direction decisions |
| Framework without grounding | elegant narrative, little evidence | weak inner loop | add protocols, cases, measurements |
| Human bottleneck | frequent small approvals | overused procedural control | reserve approval for high-risk decisions |
| AI drift | work diverges from goal | stale value signal or weak reports | generate governance report and update priorities |
| False certainty | speculative claims look confirmed | missing confidence/evidence labels | label evidence type and confidence |

## 8. Limitations

This paper is a conceptual analysis of one AI skill rather than a controlled empirical study. The framework is grounded in artifact mapping, workflow analysis, and external theoretical alignment, but it has not yet been validated across multiple independently designed long-running AI systems.

The citation package includes strengthened metadata for relevant sources, but several claims still require quote-level verification and page-specific support before academic submission. In particular, the framework should not claim that external standards or authors endorse it. The safe claim is that these sources support design requirements that the framework synthesizes.

Future work should test the framework against other long-running AI skills, compare alternative artifact schemas, and measure whether report-based governance improves alignment, efficiency, or human trust calibration.

## 9. Conclusion

`/autoresearch` demonstrates that advanced AI skills should not be understood merely as better prompts or larger tool collections. They can be designed as governable stateful systems.

In such systems:

```text
Humans define value.
AI produces evidence.
Artifacts preserve state.
Outer loops generate meaning.
Reports enable governance.
Feedback updates direction.
```

The Stateful Value-Signal Research Loop provides a reusable vocabulary for designing these systems. It helps explain how an AI agent can continue making autonomous progress while remaining inspectable, steerable, and accountable to human goals.

## References

See `paper/references.bib` for the current citation package. Key references include Horvitz on mixed-initiative user interfaces, W3C PROV standards, NIST AI RMF 1.0, Hutchins on distributed cognition, Norman on cognitive artifacts, and Davidson & Freire on scientific workflow provenance.
