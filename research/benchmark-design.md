# Benchmark design and review notes

Eugene Yan’s essay got this project thinking about how to build public benchmarks. His review of twelve evaluations found reports of graders rejecting valid work in eight of them. Some graders also accepted outputs that matched a superficial check. That makes the grader part of the experiment. [Lessons from 12 Evals: Where They Break and What to Measure Instead](https://eugeneyan.com/writing/public-evals)

## Design the benchmark around a decision

- **Start with a decision and declare coverage.** HELM uses common scenarios and multiple metrics, and records which scenarios are missing. The first question here is whether an adopter can verify more about a model’s lifecycle from a revised card. Later cases can test what the system does. Publish the four principle rates separately, along with the case-set revision, denominators, and gaps. [HELM](https://arxiv.org/abs/2211.09110)
- **Write the case and scoring rule together.** CheckList turns broad capabilities into specific checks. Our case should name who or what is in scope, what the reviewer gets, the result the case asks for, and how to grade it. Test the rubric on a case with supporting evidence, one with an explicit gap, and one with a plausible link whose source fails to support the claim. Preserve the difference between a missing result and an unsuccessful one. [CheckList](https://aclanthology.org/2020.acl-main.442/)
- **Compare one change at a time.** Use the same checkpoint, questions, time budget, and rules for following links. Two independent reviewers see both card revisions in opposite orders. A paired design lets us compare each reader with themself. Opposite orders balance one order effect. Carryover remains possible, and the reviewers can see the new field. Report the two sets of results and disagreements before reconciliation. With two reviewers, treat the outcome as a pilot observation. [NIST experimental design handbook](https://www.itl.nist.gov/div898/handbook/pri/section3/pri332.htm)
- **Repeat behavioral tests where variation matters.** For a future agent recovery case, keep the model, harness, and fault schedule pinned. Report individual trial outcomes and how many cases pass every trial. Fix the number of repeats before running. A static document comparison needs independent reviewers, so keep those results separate from repeated model trials. [τ-bench](https://arxiv.org/abs/2406.12045)

## Give contributors a way to improve the benchmark

- **Review failures in both directions.** Dynabench uses people to find cases models miss. For this project, new cases should include a named coverage gap or failure mode. A reviewer other than the author should reproduce the case and check that the rubric accepts defensible answers and rejects unsupported ones. Keep a fixed comparison set and version new cases separately so comparisons remain interpretable as coverage grows. [Dynabench](https://aclanthology.org/2021.naacl-main.324/)
- **Publish the objection and its disposition.** The IETF’s rough-consensus guidance treats addressing objections as part of reaching consensus. Here, the group responsible for a case records what it changed, why it declined a proposal, or who owns a deferred concern. Weekly meetings at rotating times and asynchronous review give people in different regions a way to participate. Publish unresolved dissent alongside the decision. [IETF RFC 7282](https://www.rfc-editor.org/rfc/rfc7282.html)
- **Keep results traceable.** MLPerf uses explicit submission, review, and publication rules. Hugging Face already distinguishes community-submitted evaluation results from results with verified provenance. Put the lifecycle and review decision in the card. Link the benchmark revision, per-case record, and verification status. This lets a reader distinguish a publisher’s claim, a community submission, and a reproduced result. [MLPerf submission rules](https://github.com/mlcommons/policies/blob/master/submission_rules.adoc) · [Hugging Face evaluation results](https://huggingface.co/docs/hub/eval-results)

## First case and limits

A review of 445 LLM benchmarks found recurring gaps between the constructs they claimed to measure and the way they scored tasks. Give each proposed rate a narrow claim. For fairness in particular, publish outcomes and gaps by group alongside the rate so readers can see what the threshold hides. [Measuring What Matters](https://proceedings.neurips.cc/paper_files/paper/2025/hash/1967e0fc3aa6cbbace562f5cb8e3954e-Abstract-Datasets_and_Benchmarks_Track.html)

Compare the published GPT-6.2 Astra system card with the same version plus the proposed principle-metrics disclosure. Give each reviewer 15 minutes per card, with its text and up to two hops from its links. Fix the applicable stages before either review. Use these six questions for both cards:

1. What uses, users, and limits does the publisher name?
2. Which data, training recipe, and checkpoint produced this release?
3. Which evaluation, comparison baseline, and coverage gaps does the card disclose?
4. What version and release scope did the publisher approve, and how can users revert?
5. Who monitors the release, and what triggers action?
6. What ends at retirement, and where can users migrate?

A stage passes evidence coverage when the cited material supports all required parts of its answer. Record partial evidence and explicit gaps alongside the supporting passages. Calibrate both reviewers on a mixed case as well as on complete, missing, and unsupported answers. For any supported answer, retain the source and supporting passage. A public discussion link alone cannot verify who monitors regressions. Keep the same applicable stages in both denominators. Report evidence coverage, stated-gap coverage, and elapsed time separately. Preserve raw reviewer assessments when resolving disagreements.

The first case measures the usability of a disclosure. Fairness, resilience, empowerment, and collaboration rates require separate cases that examine outcomes, recovery, user control, and review decisions. The original model-card framework already calls for intended use and disaggregated performance. This proposal adds a way for readers to follow the evidence through the lifecycle. [Model Cards for Model Reporting](https://arxiv.org/abs/1810.03993)

## Reader review

- **5 seconds.** The title and hook say why the problem matters. Can the reader tell what the post proposes?
- **2 minutes.** The short summary states the four principles and what each asks of a system. Can the reader explain one without opening the spec?
- **10 minutes.** The detailed principles and author commentary explain a real trade-off and show where to propose or rate a change.
- **1 hour.** The model card opens into the pinned revision, baseline, lifecycle evidence, gaps, benchmark cases, and review decisions. A reader can apply the patch, score the original and changed card, and write a reproducible objection.

Capture the earliest completed step and the first blocker for each run. A private preview can test the staged path. A public reader run starts from the public article. Treat elapsed time and completion as observations from the test.

## What belongs in the model card

Put version, intended use, baseline, and the release decision at the top. Show one line for each lifecycle stage with its evidence status. Link versioned artifacts, denominators and per-case outcomes behind the headline numbers. In Open Review, show who had authority to decide, whether a concern changed the release, and when the decision will be revisited. Link deployment-specific controls to the service or integration responsible for them.

The first staged reader rehearsal applied an earlier sample card patch. It surfaced gaps in monitoring and retirement. The GPT-6.2 Astra comparison and the four principle rates remain pending.
