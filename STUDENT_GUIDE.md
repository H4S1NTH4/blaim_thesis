# BLAIM Dissertation Guide

## Current Thesis Topic

**Continuous Keystroke Authentication and Behaviour Analysis Using Keystroke Data for Programming Assessments**

The thesis is now structured to match the supplied marking rubric and SLIIT dissertation structure. It focuses on BLAIM: a Behaviour Learning Analytics and Identity Monitoring module implemented inside GradeLoop Core.

## Main Files

| File | Purpose |
| --- | --- |
| `main.tex` | Master LaTeX document. Compile this file. |
| `custom.sty` | SLIIT formatting, margins, fonts, headings, page numbering, bibliography setup. |
| `frontmatter/titlepage.tex` | Title page. Update supervisor/date fields if required. |
| `frontmatter/abstract.tex` | Final abstract under 300 words. |
| `chapters/chapter1.tex` | Introduction, gap, problem, objectives, scope, novelty. |
| `chapters/chapter2.tex` | Literature review and comparison of related work. |
| `chapters/chapter3.tex` | Methodology, architecture, implementation, requirements, testing, commercialization. |
| `chapters/chapter4.tex` | Evaluation results, metrics, discussion, limitations, ethics, contribution. |
| `chapters/chapter5.tex` | Conclusion, recommendations, future work. |
| `appendices/appendixA.tex` | Supporting technical evidence and endpoint summary. |
| `references.bib` | Bibliography entries. |
| `BLAIM_TESTING_DATA_AND_METRICS.md` | Evidence pack generated from the local BLAIM databases. |
| `diagrams/PLACEHOLDERS.md` | Checklist of image placeholders to replace later. |

## Diagram Placeholders to Create

See `diagrams/PLACEHOLDERS.md`.

The thesis currently uses boxed LaTeX placeholders for:

1. BLAIM high-level system architecture.
2. BLAIM evaluation workflow.
3. Authentication outcome distribution chart.

After creating final images, replace the placeholder boxes in `chapter3.tex` and `chapter4.tex` with `\includegraphics` while keeping the same captions and labels.

## Build Notes

Use XeLaTeX because the template uses `fontspec` and Times New Roman.

Suggested build sequence in Overleaf:

1. Set compiler to XeLaTeX.
2. Compile `main.tex`.
3. Recompile if references or lists need another pass.

The local container used for this rewrite does not have `latexmk` or `xelatex` installed, so final PDF compilation should be done in Overleaf or a TeX-enabled machine.

## Rubric Coverage

| Rubric area | Where it is covered |
| --- | --- |
| Literature survey and comparison | Chapter 2 |
| Research gap and novelty | Chapter 1 and Chapter 2 |
| Architecture and design | Chapter 3 |
| Tools and technology justification | Chapter 3 |
| Functional and non-functional requirements | Chapter 3 |
| Testing and evaluation metrics | Chapter 4 |
| Social, security, ethics, limitations | Chapter 4 |
| Commercialization potential | Chapter 3 |
| Conclusion and recommendations | Chapter 5 |

## Final Manual Checks Before Submission

1. Add final diagrams/screenshots and remove the boxed placeholders if desired.
2. Confirm supervisor name and date on the declaration/title page.
3. Compile in Overleaf with XeLaTeX.
4. Check list of figures and list of tables after images are added.
5. Review references formatting after PDF generation.
