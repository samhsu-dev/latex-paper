# latex-paper

> Structured LaTeX skeleton for academic papers — start writing, not configuring.

ACM CCS 2026 paper template with modular section layout, reusable package configs, and revision markup support.

## Install

Click **Use this template** on GitHub, or clone directly:

```bash
gh repo create my-paper --template samhsu-dev/latex-paper --public --clone
```

Requires a LaTeX distribution ([TeX Live](https://www.tug.org/texlive/) or [MacTeX](https://www.tug.org/mactex/)).

## Usage

```bash
pdflatex -output-directory=.output main.tex
bibtex .output/main
pdflatex -output-directory=.output main.tex
pdflatex -output-directory=.output main.tex
```

Or open `main.tex` in [VS Code + LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) — the `.vscode/settings.json` is pre-configured.

## Structure

```
main.tex                  # Entry point (ACM sigconf, CCS 2026)
references.bib            # Bibliography entries
softwares.bib             # Software/tool bibliography entries
Sections/
  sections.tex            # Section routing (Introduction → Conclusion)
  abstract.tex
  introduction.tex
  overall.tex             # Overview / Motivation
  approaches.tex
  implementations.tex
  evaluation.tex
  discussion.tex
  related_works.tex
  conclusion.tex
Packages/
  packages.tex            # Package loader
  __cobra.tex             # Project-specific macros (\sys, constants)
  codes.tex               # Code listing style
  formats.tex             # General formatting macros
  myart.sty               # Section/list spacing overrides
  revision.tex            # Revision markup (\revision, \review, \revisionenv)
Assets/
  figures/                # Figures (.pdf, .png, .drawio)
  tables/                 # Table .tex fragments
  results/                # Raw result data
Appendexies/
  appendexies.tex         # Appendix content
Revisions/
  revisions.tex           # Revision letter
  others/                 # Per-reviewer responses
Templates/
  ACM Conference.../      # ACM acmart class and samples
  USENIX 2023/            # USENIX template and samples
```

## Customization

1. Edit `main.tex` — update title, authors, conference metadata.
2. Edit `Packages/__cobra.tex` — rename `\sys` and add project-specific macros.
3. Write content in each `Sections/*.tex` file.
4. Add figures to `Assets/figures/`, table fragments to `Assets/tables/`.
5. Add references to `references.bib` and `softwares.bib`.

To switch to USENIX format, replace the `\documentclass` in `main.tex` and refer to `Templates/USENIX 2023/usenix.tex` for the entry point structure.

## License

MIT
