# Proposed disclosure for GPT-6.2 Astra

[Published system card](https://deploymentsafety.openai.com/gpt-6-2-astra-sol)

## Example benchmark use case

Test GPT‑6.2 Astra as a doctor’s assistant on simulated diagnostic cases. Compare matched cases reviewed by doctors without AI. A trajectory passes when it meets every applicable requirement for that principle, from the first question through the doctor’s final decision.

## Principle metrics

Illustrative scores. Astra benchmark results are pending.

- **Fairness.** Do clinically equivalent cases meet the same requirements across patient groups? Change the patient’s preferred language and keep the clinical facts the same. Astra team 90% (18/20) · Control 95% (19/20).
- **Resilience.** Does the team recover when important information changes? A corrected lab result arrives. The team rechecks its initial assessment. Astra team 85% (17/20) · Control 80% (16/20).
- **Empowerment.** Can the doctor see uncertainty and make the final decision? The doctor can inspect the evidence and override a tentative diagnosis before it enters the note. Astra team 95% (19/20) · Control 100% (20/20).
- **Collaboration.** Does the team address a concern the doctor raises? The doctor points out a mistaken assumption. The team resolves or records it before finalizing. Astra team 90% (18/20) · Control 85% (17/20).

Report the case set, requirements, pass counts, and evidence for both groups. [FDA human–AI evaluation principles](https://www.fda.gov/medical-devices/artificial-intelligence-enabled-medical-devices/good-machine-learning-practice-medical-device-development-guiding-principles)

Use the same four principles across industries. Domain teams define their cases, passing requirements, and control group. Report rates by domain.
