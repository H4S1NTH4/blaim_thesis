# Thesis Rewrite Completion Report

## Summary

The `blaim_thesis` dissertation has been rewritten around the requested priority topic:

**Continuous Keystroke Authentication and Behaviour Analysis Using Keystroke Data for Programming Assessments.**

The rewrite aligns the thesis with the supplied marking rubric, the SLIIT dissertation structure guide, the BLAIM testing data evidence pack, and the actual GradeLoop/BLAIM implementation in the project root.

## Updated Structure

| Area | Status |
| --- | --- |
| Front matter | Updated title, abstract, acknowledgement, abbreviations, and formatting references. |
| Chapter 1 | Rewritten with background, research gap, problem, objectives, novelty, scope, methodology overview, and structure. |
| Chapter 2 | Rewritten as a literature review with related-work comparison and explicit knowledge gap. |
| Chapter 3 | Rewritten with methodology, requirements, architecture, feature pipeline, database/API design, tools, testing, and commercialization. |
| Chapter 4 | Rewritten with real evaluation data, confusion matrix, metrics, monitoring/archive results, discussion, limitations, ethics, and contribution. |
| Chapter 5 | Added conclusion, objective achievement, recommendations, and future work. |
| Appendix | Rewritten with technical evidence references and endpoint summary. |
| Diagrams | Added `diagrams/PLACEHOLDERS.md` and boxed placeholders in LaTeX chapters. |

## Key Evidence Integrated

From `BLAIM_TESTING_DATA_AND_METRICS.md`:

| Metric | Value |
| --- | --- |
| Evaluator enrollment records | 32 |
| Evaluator test records | 31 |
| Keystroke biometric templates | 32 |
| Enrollment progress rows | 15 |
| Keystroke archives | 34 |
| Authentication timeline events | 12 |
| Distinct observed users | 16 |
| Genuine labelled records | 17 |
| Impostor labelled records | 7 |
| True accepts | 14 |
| False rejects | 3 |
| True rejects | 6 |
| False accepts | 1 |
| Genuine accept rate | 82.35% |
| False positive rate | 14.29% |

## Diagram Placeholder Register

Created: `blaim_thesis/diagrams/PLACEHOLDERS.md`

Required images:

1. `system_architecture.png`
2. `evaluation_workflow.png`
3. `authentication_metrics_chart.png`

The LaTeX currently compiles without external image files because the chapters contain boxed placeholders.

## Verification Attempt

Attempted local build commands:

```bash
latexmk -xelatex -interaction=nonstopmode main.tex
xelatex -interaction=nonstopmode main.tex
```

Both commands are unavailable in the local environment (`command not found`). The thesis should be compiled in Overleaf or another environment with XeLaTeX installed.

## Final Notes

The thesis now foregrounds rubric-critical material: literature comparison, proven gap, novelty, architecture, technology justification, functional and non-functional requirements, real testing metrics, ethical limitations, and commercialization potential.
