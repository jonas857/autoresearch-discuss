# Citation Verification Checklist

This checklist tracks sources that can strengthen the Stateful Value-Signal Research Loop whitepaper. Current entries are candidate references and must be verified before academic submission.

## Verification status legend

- `candidate`: identified as relevant, metadata not fully verified.
- `metadata_verified`: title/authors/year/venue verified.
- `content_verified`: relevant claims checked against source text.
- `citation_ready`: BibTeX and claim usage ready for formal paper.

## Sources

| ID | Area | Source | Status | Needed verification | Framework relevance |
|---|---|---|---|---|---|
| horvitz1999mixedinitiative | Mixed-initiative interaction | Eric Horvitz, “Principles of Mixed-Initiative User Interfaces” | candidate | venue, pages, canonical BibTeX, exact principles | Supports H2: initiative sharing and value-signal exchange |
| w3cprov2013overview | Provenance | W3C PROV Overview | candidate | editors/authors, recommendation metadata, relationship to PROV-O/PROV-DM | Supports H1: artifacts as traceable entities in workflows |
| nist2023airmf | AI governance | NIST AI RMF 1.0 | candidate | report number, DOI, exact title, governance language | Supports H4: oversight, monitoring, risk disclosure |
| hutchins1995cognition | Distributed cognition | Hutchins, Cognition in the Wild | candidate | publisher metadata, relevant chapters | Supports workspace-as-cognitive-system framing |
| norman1991cognitiveartifacts | Cognitive artifacts | Norman, Cognitive Artifacts | candidate | venue, pages, exact definition | Supports artifact-as-interface framing |

## Claim-to-source map

| Framework claim | Candidate support | Verification need |
|---|---|---|
| Long-running AI work should share initiative by layer | Horvitz mixed-initiative UI | Verify exact principles around initiative transfer |
| Research artifacts encode provenance and dependency relationships | W3C PROV | Verify entity/activity/agent terminology |
| Human-facing reports should expose risk, uncertainty, status, and monitoring information | NIST AI RMF | Verify AI RMF functions and oversight language |
| Research workspace participates in cognition | Hutchins / Norman | Verify distributed cognition and cognitive artifact claims |
| Artifact design should be treated as interaction design | Norman + PROV + current H1 analysis | Verify external terminology and avoid overclaiming |

## Next steps for full citation verification

1. Fetch or manually download each source.
2. Extract canonical metadata and BibTeX.
3. Read relevant sections and record exact supporting claims.
4. Update `paper/references.bib` from candidate to citation-ready entries.
5. Replace whitepaper’s citation-status section with formal references.
6. Add in-text citation markers to `paper/stateful-value-signal-research-loop-whitepaper.md`.

## Current limitation

Direct WebFetch was blocked for several target domains in the current environment, so source claims must be verified through an alternative route before academic submission.
