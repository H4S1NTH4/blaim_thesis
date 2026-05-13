# BLAIM Final Report Marking Rubric Justification

Generated for the dissertation compiled at `blaim_thesis/main.pdf`.

This is an evidence-based self-assessment against the supplied `llm_guide/marking rubric.pdf`. It is not an official mark, but it estimates the marks that are realistically achievable from the current thesis content.

## Final Verification Summary

| Check | Status | Evidence |
|---|---:|---|
| Thesis compiles | Passed | `latexmk -xelatex -interaction=nonstopmode main.tex` completed successfully |
| Main PDF generated | Passed | `main.pdf` generated successfully |
| Chapter structure | Passed | Introduction, literature review, methodology/design, evaluation/discussion, conclusion, appendix |
| Literature gap stated | Passed | Chapter 1 research gap; Chapter 2 identified knowledge gap |
| Novelty emphasized | Passed | Live coding keystrokes for both continuous authentication and behaviour analytics |
| System design included | Passed | Chapter 3 architecture diagram, data flow, external interfaces, API design |
| Evaluation evidence included | Passed | Chapter 4 dataset, confusion matrix, metrics, scenario coverage, requirement validation |
| Ethics/security/social issues included | Passed | Chapters 2, 4, and 5 |
| Commercialization included | Passed | Chapter 3 commercialization plan and evidence table |
| Remaining technical weakness | Minor | Some table overfull/underfull warnings remain, mostly formatting warnings, not compile blockers |
| Threshold calibration explained | Passed | Chapter 3 threshold selection and calibration; Chapter 4 threshold interpretation |
| Commercial positioning strengthened | Passed | Chapter 3 competitor-positioning table, MVP path, SaaS/on-premise model |

## Estimated Marks

| Rubric area | Weight | Estimated score | Weighted mark |
|---|---:|---:|---:|
| Proven gap / creative solution, LO1 | 10 | 88 / 100 | 8.8 |
| Application of specialized knowledge, LO2 | 10 | 86 / 100 | 8.6 |
| Solution implementation, LO3 | 45 | 88 / 100 | 39.6 |
| Effective communication, LO4 | 20 | 85 / 100 | 17.0 |
| Commercialization / entrepreneurship, LO5 | 15 | 88 / 100 | 13.2 |
| **Estimated final mark** | **100** |  | **87.2 / 100** |

**Achievable final mark: approximately 87 / 100.**  
Since the final report contribution is 19%, this corresponds to approximately **16.6 / 19**.

## LO1: Proven Gap / Creative Solution

**Weight: 10%**  
**Estimated: 88 / 100, weighted 8.8 / 10**

### Literature survey with comparison of similar work

The thesis has a strong literature review based on credible sources across keystroke biometrics, continuous authentication, TypeNet/deep sequence models, programming trace analytics, remote proctoring, ethical biometric deployment, and microservice architecture. Chapter 2 compares classical keystroke biometrics, TypeNet, continuous authentication, programming trace analytics, and BLAIM in a dedicated related-work comparison table.

Evidence:

- Chapter 2: `Keystroke Dynamics as Behavioural Biometrics`
- Chapter 2: `Continuous Authentication`
- Chapter 2: `Programming Trace Analytics`
- Chapter 2: `Academic Integrity in Online Assessment`
- Chapter 2: `Comparison of Related Work`
- `references.bib` contains 40+ bibliography entries, including recent keystroke, programming trace, stress/cognitive-load, and architecture references.

Justification: This reaches the excellent band because the thesis does not merely list studies; it uses them to identify a gap between continuous keystroke authentication and programming-process analytics.

### Research problem and knowledge gap

The research problem is clearly stated in Chapter 1:

> How can keystroke data captured during programming assessments be used to continuously authenticate student identity while also producing interpretable behaviour analysis?

The novelty is clearly positioned as the integration of continuous identity assurance and process-aware behaviour analysis during source-code production. Chapter 2 also states that the underexplored area is the combined use of live coding keystrokes for continuous student authentication and interpretable behaviour analysis within a deployable programming-assessment service.

Evidence:

- Chapter 1: `Research Gap`
- Chapter 1: `Research Problem`
- Chapter 1: `Novelty and Contribution`
- Chapter 2: `Identified Knowledge Gap`
- Chapter 5: `Conclusion`

Reason it is not scored 95+: The thesis has strong novelty justification, but the evaluation sample is still relatively small, so the gap is proven more by literature synthesis and prototype evidence than by large-scale longitudinal validation.

## LO2: Application of Specialized Knowledge

**Weight: 10%**  
**Estimated: 86 / 100, weighted 8.6 / 10**

The thesis applies specialized knowledge from several relevant areas:

- Keystroke dynamics: dwell time, flight time, hold latency, inter-key latency, press/release latency.
- Behavioural biometrics: verification, identification, continuous monitoring, template variance.
- Deep learning: TypeNet-inspired 70 by 5 sequences and 128-dimensional embeddings.
- Programming analytics: pauses, deletion rate, burst typing, friction points, cognitive load, debugging behaviour.
- Software engineering: FastAPI microservice, PostgreSQL, Redis, REST API, WebSocket monitoring, Docker Compose.
- Ethical biometric deployment: consent, retention, human review, fairness, accessibility, security hardening.

Evidence:

- Chapter 3: `Feature Extraction and Authentication Pipeline`
- Chapter 3: `Multi-Phase Enrollment Design`
- Chapter 3: `Behaviour Analysis Pipeline`
- Chapter 3: `Database Design`
- Chapter 3: `API Design`
- Chapter 4: `Monitoring and Archive Results`
- Chapter 4: `Behaviour Analysis Results`

Justification: This is excellent because the implementation applies the theory directly in an operational artifact. It is not just a conceptual design. The main reason for not awarding full marks is that model training/fine-tuning and fairness calibration are not fully completed at production scale.

## LO3: Solution Implementation

**Weight: 45%**  
**Estimated: 88 / 100, weighted 39.6 / 45**

### High-level system design

**Subweight: 25% of LO3**  
**Estimated: 88 / 100**

Chapter 3 includes a high-level architecture diagram showing the Next.js coding UI, evaluator backend, keystroke FastAPI service, Redis, PostgreSQL, TypeNet model, optional RabbitMQ, optional Gemini, and dashboard. It also explains capture, intelligence, and consumption layers.

Evidence:

- Chapter 3: `System Architecture`
- Figure: `BLAIM High-Level System Architecture`
- Chapter 3: `Capture Layer`, `Intelligence Layer`, `Consumption Layer`
- Chapter 3: `GradeLoop Integration Boundary`
- Chapter 3: `Data Flow`
- Chapter 3: `External Interfaces`

Justification: Excellent system design demonstration. The major components and relationships are visible and explained. External communication is also covered.

### Use of tools, technologies, and design techniques

**Subweight: 35% of LO3**  
**Estimated: 88 / 100**

The thesis justifies FastAPI, PyTorch, PostgreSQL, Redis, Next.js/React, Docker Compose, optional RabbitMQ, and optional Gemini. The implementation is described as a microservice with clear service boundaries and API contracts.

Evidence:

- Chapter 3: `Technology Choices and Justification`
- Chapter 3: `API Design`
- Chapter 3: `Database Design`
- Chapter 3: `Rule-Based and LLM-Assisted Analysis`
- Appendix A: endpoint summary

Justification: Excellent. The technology choices are appropriate and well explained. The API and appendix endpoint tables have also been formatted to improve readability. It could be even stronger with screenshots of Swagger/OpenAPI, deployment logs, or an architecture-to-code mapping.

### Completeness of functional and non-functional requirements

**Subweight: 35% of LO3**  
**Estimated: 88 / 100**

The thesis lists 10 functional requirements and non-functional requirements, then maps them to implementation artifacts and evaluation evidence. Chapter 4 validates the requirements using real testing data.

Evidence:

- Chapter 3: `Functional Requirements`
- Chapter 3: `Non-Functional Requirements`
- Chapter 3: `Testing Strategy`
- Chapter 3: `Requirement Traceability Matrix`
- Chapter 4: `Scenario-Based Test Coverage`
- Chapter 4: `Requirement Validation Summary`
- `BLAIM_TESTING_DATA_AND_METRICS.md`

Evaluation evidence includes:

- 32 enrollment records
- 31 test records
- 32 biometric templates
- 34 archives
- 12 authentication timeline events
- 16 observed users
- Labelled genuine/impostor results

Justification: Strong coverage of functional and non-functional requirements. The thesis now includes a dedicated threshold selection and calibration subsection, which improves the explanation of the evaluation configuration and future production-readiness path. It loses a few marks because some production-grade controls are still identified as future work, such as encryption hardening and broader fairness validation.

### Social, security, ethical aspects, and limitations

**Subweight: 5% of LO3**  
**Estimated: 90 / 100**

The thesis includes informed consent, data minimization, access control, retention, fairness, accessibility, human review, and limitations. It clearly states that BLAIM should be decision-support evidence rather than an automatic disciplinary engine.

Evidence:

- Chapter 2: `Ethical, Security, and Fairness Considerations`
- Chapter 2: `Security Requirements for Biometric Templates`
- Chapter 4: `Limitations`
- Chapter 4: `Social, Security, and Ethical Considerations`
- Chapter 5: `Recommendations`

Justification: Excellent. The ethical stance is clear and repeated in multiple chapters.

## LO4: Effective Communication

**Weight: 20%**  
**Estimated: 85 / 100, weighted 17.0 / 20**

### Idea delivery

**Subweight: 50% of LO4**  
**Estimated: 86 / 100**

The report explains the idea clearly: keystroke data is reused for continuous identity monitoring and behaviour analytics in programming assessments. The introduction, methodology, evaluation, and conclusion are consistent.

Evidence:

- Chapter 1: background, gap, problem, objectives, novelty
- Chapter 3: methodology and implementation
- Chapter 4: answer to research problem
- Chapter 5: conclusion and future work

### Structure and mechanics of language

**Subweight: 30% of LO4**  
**Estimated: 83 / 100**

The thesis has a logical structure and meaningful chapters. The writing is generally clear. Tables and diagrams support the explanation. The API and appendix endpoint tables were improved to prevent endpoint paths from overlapping adjacent columns.

Reason for not scoring higher: The LaTeX build still reports some overfull/underfull box warnings in dense tables. These are formatting warnings, not content failures, but they can slightly affect presentation polish.

### Referencing

**Subweight: 20% of LO4**  
**Estimated: 84 / 100**

The thesis uses citations throughout Chapters 1 and 2 and includes IEEE-style bibliography handling through BibTeX. The references cover both older foundations and recent work.

Evidence:

- `references.bib`
- Chapter 1 background and gap citations
- Chapter 2 literature review citations
- Chapter 3 multi-phase enrollment citations

Reason for not scoring higher: A few entries are weaker `@misc` or internal documentation references. Replacing them with full publication metadata where available would improve referencing quality.

## LO5: Commercialization / Entrepreneurship

**Weight: 15%**  
**Estimated: 88 / 100, weighted 13.2 / 15**

The thesis includes a commercialization plan, potential customer groups, deployment model, differentiators, commercial readiness requirements, competitor-positioning evidence, and a two-tier revenue model.

Evidence:

- Chapter 3: `Commercialization Plan`
- Chapter 3: `Commercial Positioning Against Existing Integrity Approaches`
- Table: `Commercialization Evidence`
- Chapter 5: future work and production hardening

Strengths:

- Clear customer groups: universities, online degree providers, coding bootcamps, certification providers, LMS vendors.
- Clear product value: privacy-conscious alternative/complement to webcam proctoring.
- Clear integration path: REST APIs, WebSocket monitoring, PostgreSQL, Redis, optional RabbitMQ.
- Clear revenue model: SaaS subscription or institution-hosted deployment.
- Clear competitor-positioning against webcam proctoring, lockdown browsers, code similarity checking, login authentication, and learning analytics.
- Clear MVP/pilot path through LMS adapter, policy configuration, threshold calibration, staff training, and consent workflow.

Reason for not scoring higher: The commercialization section is now strong, but it still does not include market sizing, competitor pricing, a detailed cost model, or an IP plan. Adding those would push this closer to the top of the excellent band.

## Key Strengths

- Strong, current novelty claim: continuous authentication during live source-code production plus behaviour analytics.
- Literature gap is explicit and defensible.
- Implementation is not just theoretical; it includes architecture, endpoints, database design, testing, metrics, and real-user evidence.
- Multi-phase enrollment is now well justified using stress, emotion, device, and cognitive-load research.
- Ethical framing is mature: decision support, not automatic punishment.
- Commercialization is included, connected to the implementation, and compared with competing integrity approaches.
- Threshold calibration is now explained as a prototype setting with a production calibration pathway.

## Remaining Improvement Opportunities

These are not blockers, but they could improve the final mark:

1. Add 2-3 screenshots of the actual evaluator UI or API docs in Appendix A.
2. Reduce remaining table formatting warnings, especially long endpoint/path tables in Appendix A and traceability tables.
3. Add actual UI screenshots or API documentation screenshots to Appendix A.
4. Add market sizing or a simple cost model to strengthen entrepreneurship evidence further.
5. Replace weak `@misc` references with full venue details where possible.

## Final Estimate

The current thesis is realistically in the **excellent band** under the provided rubric.

**Estimated final report mark: 87 / 100**  
**Weighted final report contribution: 16.6 / 19**

With UI/API screenshots, final table polish, and a small market-sizing or cost-model addition, the thesis could plausibly move toward **88-90 / 100**. Reaching 90+ would likely require stronger production-scale validation, broader user testing, fairness calibration, and richer commercialization evidence.
