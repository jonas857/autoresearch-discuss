# External Literature Validation Notes

## Purpose

This note strengthens the **Stateful Value-Signal Research Loop** framework by connecting it to adjacent research and standards traditions. A deep-research workflow verified and synthesized candidate citations across mixed-initiative interaction, provenance standards, AI governance, distributed cognition, and scientific workflow provenance.

Important caveat: the adversarial verification pass produced the strongest vote-verified evidence for NIST AI RMF 1.0. The other sources below are primary, authoritative, or seminal and are citation-ready, but their mapping to this project remains an interpretive literature-grounding claim. Do not claim that these authors or institutions endorse this project's framework; claim only that their work supports the framework's design requirements.

## Citation-Verified Findings

### 1. Mixed-Initiative Interaction

**Primary citation**

Horvitz, Eric. "Principles of Mixed-Initiative User Interfaces." *Proceedings of CHI 1999: ACM Conference on Human Factors in Computing Systems*, Pittsburgh, PA, 1999, pp. 159-166. DOI: [10.1145/302979.303030](https://doi.org/10.1145/302979.303030).

Supporting URLs:

- https://www.microsoft.com/en-us/research/publication/principles-of-mixed-initiative-user-interfaces/
- https://doi.org/10.1145/302979.303030
- https://dl.acm.org/doi/10.1145/302979.303030

**Relevance**

Mixed-initiative interaction studies systems where humans and computational agents share control over problem solving. This supports H2: `/autoresearch` is neither pure command execution nor full autonomy. Instead, initiative shifts by layer:

- Human initiative: goals, values, constraints, feedback, risk boundaries, direction changes.
- AI initiative: search, artifact maintenance, local execution, synthesis, report generation.

**Connection to framework**

The Stateful Value-Signal Research Loop can be framed as a specialized mixed-initiative architecture for long-running research tasks. It partitions initiative by epistemic layer rather than by every individual action:

```text
Human controls value and governance.
AI controls routine evidence and synthesis production.
Reports transfer initiative back to the human at decision points.
```

This strengthens H2 and secondarily H4: governance reports are initiative-transfer surfaces where the AI returns control-relevant context to the human reviewer.

### 2. Provenance and Traceability

**Primary standards citations**

- W3C PROV Working Group. *PROV-Overview: An Overview of the PROV Family of Documents*. W3C Working Group Note, 30 April 2013. https://www.w3.org/TR/prov-overview/
- W3C PROV Working Group. *PROV-DM: The PROV Data Model*. W3C Recommendation, 30 April 2013. https://www.w3.org/TR/prov-dm/
- W3C PROV Working Group. *PROV-O: The PROV Ontology*. W3C Recommendation, 30 April 2013. https://www.w3.org/TR/prov-o/

**Relevance**

The W3C PROV family defines provenance around entities, activities, and agents, with relationships such as generation, use, derivation, attribution, association, and responsibility. This directly supports H1: research artifacts are not merely files; they are provenance-bearing state objects.

**Connection to framework**

`/autoresearch` can be interpreted as a lightweight provenance architecture:

| PROV-like concept | `/autoresearch` equivalent |
|---|---|
| Entity | artifact, result file, report, findings entry |
| Activity | experiment, literature search, outer-loop synthesis |
| Agent | AI assistant, human reviewer, domain skill |
| Generation | protocol/result/report creation |
| Use | evidence consumed by analysis or report |
| Derivation | result -> analysis -> findings -> report |
| Attribution/association | human value signal, AI execution, skill/tool role |

This strengthens H1. It also supports H3 and H4 by giving a standards vocabulary for auditability, decision reconstruction, and governance review across loop iterations.

### 3. AI Risk Management and Human Oversight

**Primary citation**

National Institute of Standards and Technology. *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*. NIST AI 100-1, January 2023. DOI: [10.6028/NIST.AI.100-1](https://doi.org/10.6028/NIST.AI.100-1).

Supporting URLs:

- https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- https://doi.org/10.6028/NIST.AI.100-1
- https://www.nist.gov/itl/ai-risk-management-framework

**Verification status**

This was the strongest result from the deep-research run. Four NIST-related claims were adversarially verified 3-0. One over-specific wording was refuted: avoid saying that the AI RMF Core is "explicitly organized as a lifecycle risk-management loop." Safer wording: NIST AI RMF provides cross-cutting governance and risk-management functions that support continuous socio-technical oversight.

**Relevance**

NIST AI RMF 1.0 supports treating the Stateful Value-Signal Research Loop as governance and risk-management infrastructure rather than as a mere productivity loop. The framework emphasizes trustworthy AI considerations, accountability, transparency, explainability, risk management, socio-technical context, and the cross-cutting role of governance.

**Connection to framework**

The H4 governance report template maps naturally to risk-management concerns:

- Objective and constraints -> scope and intended use.
- Evidence summary -> basis for trust calibration.
- Open questions and risks -> uncertainty disclosure.
- Direction recommendation -> human oversight point.
- Next autonomous actions -> expectation setting and monitoring.

NIST also supports other hypotheses:

- H1: artifacts and provenance records are evidence for accountability and transparency.
- H2: human value signals correspond to stakeholder, context, intended-use, and risk-boundary mapping.
- H3: measurement and management require ongoing evidence loops.
- H4: reports are governance, monitoring, risk communication, and human oversight interfaces.

### 4. Distributed Cognition and Cognitive Artifacts

**Seminal citations**

- Hutchins, Edwin. *Cognition in the Wild*. MIT Press, 1995. ISBN 9780262581462. https://mitpress.mit.edu/9780262581462/cognition-in-the-wild/
- Norman, Donald A. "Cognitive Artifacts." In John M. Carroll, ed., *Designing Interaction: Psychology at the Human-Computer Interface*, Cambridge University Press, 1991, pp. 17-38. DOI: [10.1017/CBO9780511809472.005](https://doi.org/10.1017/CBO9780511809472.005).

**Relevance**

Distributed cognition treats cognition as distributed across people, artifacts, tools, representations, and environments. Cognitive-artifact theory explains how external representations transform cognitive tasks. Together, these sources support the claim that durable research artifacts are active reasoning media, not passive storage.

**Connection to framework**

The research workspace is a cognitive system:

```text
human values + AI operations + artifact memory + reports + feedback
```

This supports:

- H1: files, logs, dashboards, and reports are active reasoning interfaces.
- H2: human value signals must be represented in artifacts, not only remembered conversationally.
- H3: evidence/meaning loops depend on stable external representations that can be re-read, compared, and revised.

### 5. Scientific Workflow Provenance and Experiment Tracking

**Recommended citations**

- Davidson, Susan B., and Juliana Freire. "Provenance and Scientific Workflows: Challenges and Opportunities." *Proceedings of SIGMOD 2008*, pp. 1345-1350. DOI: [10.1145/1376616.1376772](https://doi.org/10.1145/1376616.1376772).
- Moreau, Luc, et al. "The Open Provenance Model Core Specification (v1.1)." *Future Generation Computer Systems* 27, no. 6, 2011, pp. 743-756. DOI: [10.1016/j.future.2010.07.005](https://doi.org/10.1016/j.future.2010.07.005).
- Zaharia, Matei, et al. "Accelerating the Machine Learning Lifecycle with MLflow." *IEEE Data Engineering Bulletin* 41, no. 4, 2018. https://sites.computer.org/debull/A18dec/p39.pdf

**Relevance**

Scientific workflow provenance and experiment tracking show why reproducible research systems need to capture execution context, data dependencies, parameters, code versions, outputs, and interpretive metadata. This validates the project-level claim that evidence production must be stateful and auditable.

**Connection to framework**

These sources support:

- H1: experiment protocols, run histories, and analysis artifacts should preserve provenance.
- H3: inner-loop evidence production and outer-loop interpretation require durable run metadata and dependency records.
- H4: governance reports depend on experiment metadata and run histories as raw material for human review.

## Synthesis Across H1-H4

| Framework element | External grounding | Citation confidence |
|---|---|---|
| H1 Artifact interfaces | W3C PROV; distributed cognition; scientific workflow provenance | High for PROV, medium for theoretical mapping |
| H2 Value-signal exchange | Horvitz mixed-initiative interaction; NIST stakeholder/context mapping | Medium |
| H3 Evidence/meaning loops | Scientific workflow provenance; experiment tracking; distributed cognition | Medium |
| H4 Governance reports | NIST AI RMF 1.0; mixed-initiative initiative-transfer points | High for NIST, medium for Horvitz mapping |

## Safe Claims for Paper Drafting

Use these formulations:

1. "The framework is consistent with mixed-initiative interaction: human and AI initiative are allocated by epistemic layer rather than by every micro-action."
2. "The artifact architecture can be interpreted through W3C PROV concepts such as entity, activity, agent, derivation, generation, and use."
3. "NIST AI RMF 1.0 supports treating progress reports as governance and risk-communication interfaces for socio-technical AI systems."
4. "Distributed cognition and cognitive-artifact theory support the claim that durable workspace artifacts participate in the research cognition system."
5. "Scientific workflow provenance and experiment tracking support the need for reproducible, auditable evidence loops."

Avoid these formulations:

1. "NIST AI RMF endorses the Stateful Value-Signal Research Loop." It does not.
2. "The AI RMF Core is explicitly a lifecycle loop identical to this framework." This wording was refuted.
3. "Horvitz/W3C/Hutchins prove this framework." They provide external grounding, not proof.

## Next Literature Tasks

For a formal academic paper, the next step is to convert the above into the target citation style and, if needed, add direct quotations/page references from accessible PDFs or library copies. Highest-priority additions would be:

1. Direct page references for Horvitz's CHI 1999 mixed-initiative design principles.
2. Exact W3C PROV definitions for Entity, Activity, Agent, Generation, Use, and Derivation.
3. Direct NIST AI RMF quotations for GOVERN, MAP, MEASURE, MANAGE, socio-technical risk, and trustworthy AI characteristics.
4. Page references for Hutchins and Norman on distributed cognition/cognitive artifacts.
5. Additional modern references for Research Objects, RO-Crate, or MLflow if the project adopts an explicit artifact schema.
