# Final Paper Package Plan and Submission Readiness Checklist

Project: **Stateful Value-Signal Research Loop**

Repository: <https://github.com/jonas857/autoresearch-discuss>

## 1. One-sentence contribution

This paper introduces the **Stateful Value-Signal Research Loop**, a framework for designing governable long-running AI skills in which humans provide value signals and oversight, AI maintains artifact-mediated state, inner loops produce evidence, outer loops synthesize meaning, and progress reports close the human steering loop.

## 2. Current paper artifacts

| Artifact | Path | Purpose | Status |
|---|---|---|---|
| Chinese methodology article | `paper/stateful-value-signal-research-loop-article.md` | Public-facing Chinese article | strong draft |
| Chinese whitepaper | `paper/stateful-value-signal-research-loop-whitepaper.md` | Citation-aware whitepaper | strong draft, citation caveats included |
| English formal paper | `paper/formal-paper-draft.md` | Formal paper-style structure | first formal draft |
| Chinese formal paper | `paper/formal-paper-draft-zh.md` | Chinese formal paper-style structure | first formal draft |
| References | `paper/references.bib` | Strengthened BibTeX metadata | metadata-verified, not quote-level verified |
| Citation checklist | `paper/citation-verification-checklist.md` | Tracks source readiness | active checklist |
| External validation notes | `literature/external-validation-notes.md` | Claim-to-literature grounding | citation-aware notes |

## 3. Recommended target framing

This is currently best framed as a **conceptual/design framework paper** rather than an empirical ML benchmark paper.

Best-fit venue categories:

1. Human-AI interaction / CSCW / CHI-style design theory venue.
2. AI agent systems workshop.
3. AI governance / socio-technical systems workshop.
4. Internal whitepaper / methodology report.
5. Blog/article publication supported by GitHub artifacts.

Less suitable without more experiments:

- NeurIPS/ICML/ICLR main conference empirical track.
- Systems conference main track.

## 4. Narrative check

### What

A reusable framework for governable long-running AI skills: **Stateful Value-Signal Research Loop**.

### Why

Single-turn AI chat and simple delegation fail for long-running open-ended tasks because they lack durable state, provenance, synthesis cadence, and scalable human governance.

### How

The framework is derived from a case analysis of `/autoresearch`, decomposed into four mechanisms:

1. Artifact interfaces.
2. Value-signal exchange.
3. Evidence/meaning loop separation.
4. Governance reports.

### So what

The framework gives AI skill designers a practical template for building agents that can continue autonomously while remaining inspectable, steerable, and accountable to human goals.

## 5. Figure 1 recommendation

A strong Figure 1 should show the complete loop:

```text
Human Value Signal
  ↓
Artifact-Mediated State
  ↓
Inner Loop Evidence
  ↓
Outer Loop Meaning
  ↓
Governance Report
  ↓
Updated Value Signal
```

Suggested caption:

> Figure 1: The Stateful Value-Signal Research Loop. Humans provide value signals and governance constraints. The AI maintains artifact-mediated state, produces evidence through inner loops, synthesizes meaning through outer loops, and returns progress reports that enable humans to update the value signal without micromanaging low-level actions.

## 6. Section readiness

| Section | Current status | Needed before formal submission |
|---|---|---|
| Abstract | good conceptual draft | sharpen for target venue |
| Introduction | coherent | add stronger problem motivation and contribution bullets |
| Related Work | adequate scaffold | quote-level citation verification needed |
| Method | acceptable conceptual method | clarify this is design analysis/case study |
| Framework | strong | add Figure 1 and possibly Figure 2 artifact stack |
| Design Implications | strong | connect to target audience |
| Limitations | honest | expand empirical validation limitations |
| References | metadata strengthened | full citation verification required |

## 7. Citation readiness

Current status: **metadata verified, not fully content verified**.

Do not submit academically until:

1. Full text is checked for each citation.
2. Claim-to-source mapping is verified.
3. Page numbers or section identifiers are added where useful.
4. Whitepaper/paper wording avoids overclaiming.

Safe wording:

- “This framework is consistent with...”
- “This source supports the design requirement that...”
- “This vocabulary helps describe...”
- “This tradition provides external grounding for...”

Avoid:

- “This source proves the framework.”
- “NIST endorses the framework.”
- “The AI RMF is the same lifecycle loop.”

## 8. Recommended next steps

### If publishing as GitHub methodology package

Ready now. Recommended actions:

1. Keep `README.md` as project landing index.
2. Optionally publish `to_human/stateful-value-signal-methodology.html` via GitHub Pages.
3. Share the Chinese article and whitepaper.

### If preparing an academic paper

Next actions:

1. Choose venue type: HCI/design, AI agents workshop, AI governance workshop, or systems workshop.
2. Convert `paper/formal-paper-draft.md` or `paper/formal-paper-draft-zh.md` into the target template.
3. Add Figure 1 and possibly an artifact-stack diagram.
4. Perform quote-level citation verification.
5. Add in-text citations and final reference formatting.
6. Add a stronger limitations section and future work.
7. Run final checklist for the target venue.

## 9. Submission blocker list

The following block formal academic submission:

- No target venue selected.
- Citations not quote-level verified.
- No publication-format LaTeX template yet.
- No figure files yet, only text diagrams.
- Framework not validated across multiple AI skills.

These do **not** block methodology/blog/GitHub publication.

## 10. Final recommendation

The project is complete as a **methodology package** and ready for public sharing on GitHub.

For academic submission, treat the current formal drafts as strong first drafts. The next research work should not be more conceptual expansion; it should be:

1. citation verification;
2. figure creation;
3. target-venue formatting;
4. optional validation on additional long-running AI skills.
