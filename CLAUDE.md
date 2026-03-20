# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Wuhan University PhD Dissertation Template (武汉大学博士学位论文模板). The thesis uses XeLaTeX for compilation with the custom `WHUPhd.cls` document class.

## Build Commands

**Compile with XeLaTeX:**
```bash
xelatex PhdTemplate.tex
```

**Full build with bibliography:**
```bash
xelatex PhdTemplate.tex
bibtex PhdTemplate.tex
xelatex PhdTemplate.tex
xelatex PhdTemplate.tex
```

**Clean auxiliary files:**
```bash
rm -f *.aux *.bbl *.blg *.log *.out *.toc *.synctex.gz
```

## Project Structure

```
PhdTemplate.tex          # Main document entry point
WHUPhd.cls               # Custom document class (page layout, theorems, formatting)
settings.clo             # Custom macros and math notation
ref.bib                  # BibTeX bibliography
chapter1.tex             # Chapter 1 (Introduction)
chapter2.tex             # Chapter 2
chapter3.tex             # Chapter 3
chapter4.tex             # Chapter 4
figures/                 # Chapter 1 figures
figures1/                # Additional chapter 1 figures
figures2/                # Chapter 2 figures
figures3/                # Chapter 3 figures
includefile/
  frontmatter.tex        # Innovation points, table of contents
  midmatter.tex          # Chinese/English abstracts
  backmatter.tex         # Acknowledgements, publications
```

## Key Configuration

**Document class options (PhdTemplate.tex):**
- `[forprint]` - Remove colored links for printing
- `[forlib]` - Library submission version (removes blank pages and colored links)

**Thesis metadata:** Set in `PhdTemplate.tex` using commands like `\fenleihao{}`, `\miji{}`, `\title{}`, `\author{}`, etc.

**Math notation:** `settings.clo` defines extensive vector/matrix notation (`\vx`, `\mA`, etc.), calligraphic, blackboard bold, and Fraktur alphabets.

**Figures:** Stored in `figures/`, `figures1/`, `figures2/`, `figures3/` subdirectories. The class file sets `\graphicspath{{figures/}}`.

## Chapter Management

Chapters are included via `\input{}` in `PhdTemplate.tex`. To enable/disable chapters, comment/uncomment the corresponding lines:
```latex
\input{chapter1.tex}
\input{chapter2.tex}
```
