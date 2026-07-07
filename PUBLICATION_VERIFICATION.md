# Publication Verification Report

## GitHub Pages

Status checked via GitHub API.

- URL: <https://jonas857.github.io/autoresearch-discuss/>
- Status: `built`
- Source: `master` branch, repository root `/`

A root `index.html` redirects to the visual methodology page:

- `to_human/stateful-value-signal-methodology.html`

Direct page fetching from this environment was blocked by domain verification policy for `jonas857.github.io`, but GitHub's Pages API reports the site as built.

## LaTeX package

LaTeX package location:

- `paper/latex/main.tex`
- `paper/latex/references.bib`

Local environment check:

- `latexmk`: not installed
- `pdflatex`: not installed
- `pandoc`: available at `/d/AI/PPT/tools/pandoc/pandoc`

Because no TeX compiler is installed, a full PDF compile could not be performed locally. A basic source sanity check passed:

- `\begin{document}` present
- `\end{document}` present
- `\bibliography{references}` present
- key citations present
- simple brace-balance check passed

Pandoc successfully generated an HTML preview from the LaTeX source:

- `paper/latex/main-preview.html`

## Remaining verification before submission

For formal paper submission:

1. Install a TeX distribution such as TeX Live or MiKTeX.
2. Run `latexmk -pdf main.tex` inside `paper/latex/`.
3. Resolve any package or bibliography warnings.
4. Convert to a target venue template if needed.
5. Perform quote-level citation verification before academic submission.
