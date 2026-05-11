# BLAIM Thesis Visual Asset Register

The main rubric-critical visuals are now implemented directly in LaTeX/TikZ, so the thesis no longer depends on boxed diagram placeholders.

| Visual | Location | Status |
| --- | --- | --- |
| BLAIM high-level system architecture | `chapters/chapter3.tex` / `fig:system-architecture` | Implemented as TikZ diagram |
| BLAIM evaluation workflow | `chapters/chapter4.tex` / `fig:evaluation-flow` | Implemented as TikZ diagram |
| Authentication outcome distribution | `chapters/chapter4.tex` / `fig:metrics-chart` | Implemented as TikZ chart |

Optional final-polish screenshots that can be added if available:

| Optional screenshot | Suggested file name | Suggested chapter |
| --- | --- | --- |
| Enrollment UI | `enrollment_page.png` | Chapter 3 or Appendix |
| Testing UI | `testing_page.png` | Chapter 4 or Appendix |
| Research metrics dashboard | `research_dashboard.png` | Chapter 4 |

Screenshots were not inserted automatically because they require a running UI/browser capture from the local environment.
