# Citation Verification Checklist

This checklist tracks sources that strengthen the Stateful Value-Signal Research Loop whitepaper. Several entries now have strengthened bibliographic metadata, but content-level verification should still be completed before formal academic submission.

## Verification status legend

- `candidate`: identified as relevant, metadata not fully verified.
- `metadata_verified`: title/authors/year/venue/DOI or canonical URL verified enough for draft use.
- `content_verified`: relevant claims checked against source text.
- `citation_ready`: BibTeX and claim usage ready for formal paper.

## Sources

| ID | Area | Source | Status | Needed verification | Framework relevance |
|---|---|---|---|---|---|
| horvitz1999mixedinitiative | Mixed-initiative interaction | Eric Horvitz, “Principles of Mixed-Initiative User Interfaces,” CHI 1999, pp. 159-166, DOI: 10.1145/302979.303030 | metadata_verified | Check full paper text for exact initiative-transfer principles and quote-level claims | Supports H2: initiative sharing and value-signal exchange |
| w3cprov2013overview | Provenance | W3C PROV-Overview, 30 Apr 2013 | metadata_verified | Confirm preferred editor list if style requires named editors | Supports H1: artifacts as traceable entities in workflows |
| w3cprov2013dm | Provenance | W3C PROV-DM, 30 Apr 2013 | metadata_verified | Extract exact definitions of Entity, Activity, Agent, Generation, Use, Derivation | Supports H1/H3: artifact provenance and evidence derivation |
| w3cprov2013o | Provenance ontology | W3C PROV-O, 30 Apr 2013 | metadata_verified | Verify ontology terminology if used in formal schema | Supports H1: formal artifact/provenance vocabulary |
| nist2023airmf | AI governance | NIST AI RMF 1.0, NIST AI 100-1, DOI: 10.6028/NIST.AI.100-1 | metadata_verified | Check PDF for exact GOVERN/MAP/MEASURE/MANAGE language and avoid overclaiming lifecycle-loop equivalence | Supports H4: oversight, monitoring, risk disclosure |
| hutchins1995cognition | Distributed cognition | Hutchins, *Cognition in the Wild*, MIT Press, 1995 | metadata_verified | Add page-specific support for distributed cognition claims | Supports workspace-as-cognitive-system framing |
| norman1991cognitiveartifacts | Cognitive artifacts | Norman, “Cognitive Artifacts,” in *Designing Interaction*, 1991, pp. 17-38, DOI: 10.1017/CBO9780511809472.005 | metadata_verified | Verify exact cognitive artifact definition and page references | Supports artifact-as-interface framing |
| davidson2008provenanceworkflows | Scientific workflow provenance | Davidson & Freire, “Provenance and Scientific Workflows,” SIGMOD 2008, DOI: 10.1145/1376616.1376772 | metadata_verified | Check paper for exact workflow provenance challenges/opportunities | Supports H1/H3/H4 evidence-loop auditability |

## Claim-to-source map

| Framework claim | Candidate support | Verification need |
|---|---|---|
| Long-running AI work should share initiative by layer | Horvitz mixed-initiative UI | Verify exact principles around initiative transfer and user control |
| Research artifacts encode provenance and dependency relationships | W3C PROV Overview/DM/O | Verify entity/activity/agent and generation/use/derivation terminology |
| Human-facing reports should expose risk, uncertainty, status, and monitoring information | NIST AI RMF | Verify governance/risk-management language in PDF |
| Research workspace participates in cognition | Hutchins / Norman | Verify distributed cognition and cognitive artifact claims with page references |
| Scientific evidence loops require durable metadata and provenance | Davidson & Freire; W3C PROV | Verify workflow-specific provenance claims |
| Artifact design should be treated as interaction design | Norman + PROV + current H1 analysis | Verify external terminology and avoid saying external authors endorse this framework |

## Safe wording rules

Use:

1. “This framework is consistent with...”
2. “This source supports the design requirement that...”
3. “This vocabulary helps describe...”
4. “This tradition provides external grounding for...”

Avoid:

1. “This source proves the framework.”
2. “This institution endorses the framework.”
3. “NIST AI RMF is the same lifecycle loop.”
4. “Mixed-initiative theory directly prescribes this artifact schema.”

## Next steps for full citation verification

1. Fetch or manually download each source.
2. Extract canonical metadata and BibTeX from publisher pages.
3. Read relevant sections and record exact supporting claims.
4. Add page numbers or section identifiers where possible.
5. Replace whitepaper’s citation-status section with formal references.
6. Add in-text citation markers to `paper/stateful-value-signal-research-loop-whitepaper.md` or convert to a formal LaTeX paper.

## Current limitation

Some direct WebFetch calls were blocked for target domains in the current environment. Metadata has been strengthened using known DOI/standards/report identifiers and available search targets, but quote-level content verification remains required for academic submission.
