# RFC 0002 · Model card release review

**Status** Draft for comment

## Problem

Downstream users need to know what changed across a model’s lifecycle, who reviewed those changes, and what evidence informed release decisions. Benchmark results describe part of that record.

## Proposal

Add an optional **Release review** section to the [annotated model card](https://huggingface.co/docs/hub/model-card-annotated) and link to it from the [release checklist](https://huggingface.co/docs/hub/model-release-checklist). Start with a proposed edit to one existing model card. State the baseline, intended use, release decision, and criteria set before testing.

### Model lifecycle

Record one line per stage. Link evidence. For restricted material, publish a summary and say who reviewed the underlying evidence.

- **Scope.** Intended users, intended use, limits, and criteria.
- **Data and training.** Data sources and exclusions, base model, and changes in training or fine-tuning.
- **Evaluation.** Results against the baseline, gaps in coverage, and known failures.
- **Release.** Approved scope, rollout plan, and how to revert or alert downstream users.
- **Monitoring.** What the team watches, when it will intervene, and who responds.
- **Retirement.** Notice, migration, and what support ends.

### Open Review

Link a public thread for the model version. Anyone can raise a concern or propose a change. Publish responses, changes, and unresolved concerns. Provide a private reporting path and publish a summary for issues involving confidential material. For each principle below, record the evidence and reviewer roles.

- **Fairness.** Who gets worse results than with the previous version? Whose experience did the tests leave out?
- **Resilience.** What happens when a common input or dependency fails? When would you pause the rollout, roll back, or warn downstream users?
- **Empowerment.** Can users correct a result or finish the task another way? What can downstream users inspect, run, or adapt?
- **Collaboration.** Who affected by the release reviewed it? What changed because of their input?

## Establish community benchmarks

Pin the case-set revision and pass criteria before evaluation. Publish each rate with its numerator, denominator, and baseline. Identify required cases that were not run. Mark a rate inapplicable when its denominator is zero.

- **Fairness · Group pass rate.** In-scope groups that meet an agreed outcome target / all in-scope groups.
- **Resilience · Recovery pass rate.** Fault cases that meet their recovery target / required fault cases.
- **Empowerment · User control pass rate.** Workflows where people can complete, correct, or exit within agreed limits / required control workflows.
- **Collaboration · Response coverage.** Material concerns publicly addressed before sign-off / material concerns in scope.

Anyone can contribute or challenge a case. A case records its ID, principle, affected population or workflow, lifecycle stage, reproducible procedure, pass criterion, and evidence. Four open groups curate and version the case set. Recruit participants across regions, languages, and roles. Hold weekly public reviews at rotating times, take asynchronous proposals, and publish decisions and dissent.

### First benchmark · Model lifecycle

The first case compares the published [OLMo 2 7B Instruct card](https://huggingface.co/allenai/OLMo-2-1124-7B-Instruct) with the same card plus the proposed **Release review** field. Two reviewers apply the same six lifecycle questions to the [pinned baseline](https://huggingface.co/allenai/OLMo-2-1124-7B-Instruct/tree/470b1fba1ae01581f270116362ee4aa1b97f4c84) and the [proposed patch](../examples/olmo-2-7b-instruct-release-review.patch). Mark each stage evidence linked, gap stated, missing, or inapplicable. Count evidence when a source supports the card’s claim. Record disagreements and publish both scores. Ai2 maintainers review the documentation edit. The four principle rates require separate model or workflow tests.

## Governance

The publisher owns the decision. In the pilot, one open committee with four review groups sets criteria and signs off on the proposed scope. Anyone can [open an issue to join](https://github.com/dramdass/model-release-review/issues/new). Participation in Open Review is open to readers as well as members.

Name one signer per group and the criteria each group owns. The group responsible for a criterion records how it resolved any objection and what evidence it used. The release owner records approval, a narrowed scope, or a hold. Missing evidence or sign-off holds the affected scope. Operators can pause the rollout. Record new sign-offs for material updates and retirement.

- **Fairness** pairs affected users with evaluation leads to choose comparisons and review gaps.
- **Resilience** pairs operators with downstream deployers to review failure tests and recovery plans.
- **Empowerment** pairs end users with maintainers to try correction and fallback paths and review release terms.
- **Collaboration** pairs affected users with a facilitator outside the model team to review whose input changed the decision and which concerns remain open.

A small team can hold one review meeting with the four roles represented. Expand the pilot if both reviewers can verify more lifecycle stages from the changed card.

## Upstream proposal

Start with a pull request to the OLMo model card. Use feedback from the first case to propose the optional section in [Hub Docs](https://github.com/huggingface/hub-docs/blob/main/docs/hub/model-card-annotated.md). Keep the decision in the card readers already consult. Link longer evidence records and use the checklist to point publishers to the section. The publisher owns its review policy. If the section proves useful, propose adding it to the [default model card template](https://github.com/huggingface/huggingface_hub/blob/main/src/huggingface_hub/templates/modelcard_template.md).
