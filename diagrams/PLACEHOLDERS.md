# BLAIM Thesis Visual Asset Register

This file lists the visuals that can be added or replaced in the thesis. The rubric-critical diagrams are currently implemented directly in LaTeX/TikZ, so the thesis can compile without external image files. If you create polished images, use the same captions and labels already in the `.tex` files.

## Required / Rubric-Critical Visuals

| ID | Current thesis location | Suggested image file | What the image should show | Status |
| --- | --- | --- | --- | --- |
| `fig:system-architecture` | `chapters/chapter3.tex` | `system_architecture.png` | High-level BLAIM architecture: Next.js coding UI, BLAIM evaluator backend, keystroke FastAPI service, Redis session buffer, PostgreSQL database, TypeNet model, optional RabbitMQ, optional Gemini, and instructor/research dashboard. Show arrows for keystroke batches, REST API calls, model inference, database persistence, and dashboard retrieval. | Already implemented as TikZ; replace only if you create a cleaner diagram. |
| `fig:evaluation-flow` | `chapters/chapter4.tex` | `evaluation_workflow.png` | Real-user evaluation flow: enrollment capture -> template creation -> genuine/impostor coding tests -> verify/identify/monitor -> finalize/archive -> evaluator and keystroke databases -> metric snapshots and thesis evidence. | Already implemented as TikZ; replace only if you create a cleaner diagram. |
| `fig:metrics-chart` | `chapters/chapter4.tex` | `authentication_outcome_distribution.png` | Bar chart with authentication outcomes: true accepts = 14, true rejects = 6, false rejects = 3, false accepts = 1. Use clear labels and different colors for accepted/rejected/edge outcomes. | Already implemented as TikZ; replace only if you create a cleaner chart. |

## Strongly Recommended Screenshots

These are not currently inserted in the thesis, but adding them will improve the implementation demonstration marks.

| Suggested figure label | Suggested image file | Where to add | What the image should show |
| --- | --- | --- | --- |
| `fig:enrollment-ui` | `enrollment_page.png` | Chapter 3 after the multi-phase enrollment section, or Appendix A | BLAIM enrollment page with student ID/name, selected phase, coding editor, keystroke count, code length, and save enrollment action. Use a real or demonstration student record, but avoid exposing sensitive raw keystrokes. |
| `fig:testing-ui` | `testing_page.png` | Chapter 4 near authentication performance, or Appendix A | BLAIM testing page showing test submission controls, threshold field, captured keystrokes, verification result, similarity/risk, monitor status, and archive/finalize output if visible. |
| `fig:research-dashboard` | `research_dashboard.png` | Chapter 4 after the evaluation dataset section | Research dashboard showing enrollment count, test count, genuine/impostor summary, false positives/false negatives, average similarity/risk, and recent records. |
| `fig:student-records` | `student_records_table.png` | Appendix A | A table/list of saved enrollment and test records. This supports repeatability and shows that data was persisted. |
| `fig:api-docs` | `keystroke_api_docs.png` | Appendix A | FastAPI/OpenAPI documentation page for keystroke service endpoints such as capture, enroll, verify, identify, monitor, finalize, analytics, and users/enrolled. |

## Optional Technical Diagrams

Use these only if you want more visual detail.

| Suggested figure label | Suggested image file | Where to add | What the image should show |
| --- | --- | --- | --- |
| `fig:typenet-pipeline` | `typenet_pipeline.png` | Chapter 3 after feature extraction | Raw keystroke events -> HL/IL/PL/RL/keycode features -> 70x5 sequence -> TypeNet LSTM -> 128-dimensional embedding -> template comparison -> similarity/risk. |
| `fig:database-schema` | `database_schema.png` | Chapter 3 after database design | Tables: `user_biometrics`, `enrollment_progress`, `auth_events`, `keystroke_archives`, plus evaluator tables `enrollment_records`, `test_records`, `metrics_snapshots`, `auth_reruns`. |
| `fig:behaviour-analysis-flow` | `behaviour_analysis_flow.png` | Chapter 3 after behaviour analysis pipeline | Keystroke events -> session metrics -> friction points -> authenticity indicators -> cognitive/process scores -> instructor feedback. |

## How To Replace a TikZ Diagram With an Image

Replace the TikZ body in the relevant figure with:

```tex
\includegraphics[width=\textwidth]{system_architecture.png}
```

Keep the existing `\caption{...}` and `\label{...}` unchanged so cross-references continue to work.

Place image files inside:

```text
blaim_thesis/diagrams/
```

The LaTeX template already includes `diagrams/` in `\graphicspath`.
