# RFC 0002 · Model card release review

**Early draft for public comment**

A model card should tell adopters what they can verify for their use case. We want public benchmarks for [fairness, resilience, empowerment, and collaboration](../README.md). [Eugene Yan’s review of twelve public evals](https://eugeneyan.com/writing/public-evals) got us thinking about who checks the grader.

## First case

Ask OpenAI to add [four principle metrics](../examples/gpt-6.2-astra-release-review.md) to the [published GPT-6.2 Astra system card](https://deploymentsafety.openai.com/gpt-6-2-astra-sol). Treat them like a benchmark metric such as perplexity. Report the value, counts, case-set version, and evidence. Mark missing results as **Not reported**.

The community can compare both cards now and see which gaps the field makes clear. OpenAI would publish measured results and remain responsible for release concerns. Link the **Open Review** record so readers can see who reviewed it, what changed, and who can act on a concern. Use the [Open Review discussion](https://github.com/dramdass/model-release-review/pull/1) to challenge the wording or the scoring.

## Example benchmark use case

Test GPT‑6.2 Astra as a doctor’s assistant on simulated diagnostic cases. Compare matched cases reviewed by doctors without AI. A trajectory passes when it meets every applicable requirement for that principle, from the first question through the doctor’s final decision.

- **Fairness.** Do clinically equivalent cases meet the same requirements across patient groups? Change the patient’s preferred language and keep the clinical facts the same.
- **Resilience.** Does the team recover when important information changes? A corrected lab result arrives. The team rechecks its initial assessment.
- **Empowerment.** Can the doctor see uncertainty and make the final decision? The doctor can inspect the evidence and override a tentative diagnosis before it enters the note.
- **Collaboration.** Does the team address a concern the doctor raises? The doctor points out a mistaken assumption. The team resolves or records it before finalizing.

[See the metric disclosure and illustrative scores](../examples/gpt-6.2-astra-release-review.md). [Read the benchmark design](../research/benchmark-design.md).

## What the open committee decides

- **Control group.** Should doctors work unaided or use their usual decision-support tools?
- **Alignment checks.** Which steps should we score, and when should changes trigger a rerun?
- **Clinicians.** Which specialties and experience levels should take part? Who writes and applies the rubric?
- **Data sharing.** Which cases, traces, and scoring notes can be public? What needs redaction or restricted access?

Record these choices and unresolved disagreements before running the cases.

## Join the work

Use the same four principles across industries. Domain teams define their cases, passing requirements, and control group. Report rates by domain. Bring cases from software operations, customer support, education, or public services.

[Join or propose a case on GitHub](https://github.com/dramdass/model-release-review/issues/new). Bring a case, a concern about the scoring, or a better place to start. Anyone can take part. Open review groups curate cases, answer scoring objections, and publish their decisions and disagreements. [Draft participation terms](../PARTICIPATION.md)
