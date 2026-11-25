# RFC 0002 · Model card release review

**Status** Draft for comment

## Problem

A model card can list benchmarks and limitations without showing who reviewed the release, what they found, or what changed before publication. Downstream users need that record to decide whether to adopt the version.

## Proposal

Add a **Release review** section to the [Hugging Face model card template](https://huggingface.co/docs/hub/model-card-annotated) and [release checklist](https://huggingface.co/docs/hub/model-release-checklist). Pilot it in one publisher’s model card while the Hub documentation maintainers review the template change. Record the version, baseline, and criteria set before testing. For each answer, link the evidence and record the reviewer roles and decision.

- **Fairness.** Who gets worse results than with the previous version? Whose experience did the tests leave out?
- **Resilience.** What happens when a common input or dependency fails? When would you pause the rollout, roll back, or warn downstream users?
- **Empowerment.** Can users correct a result or finish the task another way? What can downstream users inspect, run, or adapt?
- **Collaboration.** Who affected by the release reviewed it? What changed because of their input?

The release owner publishes after all four groups sign off. Missing evidence, missing required reviewers, or unresolved objections hold the release. The groups can sign off on a narrower scope and publish why. Mark questions that do not apply. Update the card after rollout, after material changes, and at retirement.

## Open committee

Form one open committee with four review groups. Anyone can [open a GitHub issue to join or propose a change](https://github.com/dramdass/model-release-review/issues/new). You can comment without joining.

- **Fairness** pairs affected users with evaluation leads to choose comparisons and review gaps.
- **Resilience** pairs operators with downstream deployers to review failure tests and recovery plans.
- **Empowerment** pairs end users with maintainers to try correction and fallback paths and review release terms.
- **Collaboration** pairs affected users with a facilitator outside the model team to review whose input changed the decision and which concerns remain open.

Set criteria during scoping. A small team can hold one review meeting with all four roles represented. Expand the pilot if a downstream maintainer can use the card to explain what shipped, who reviewed it, and why.
