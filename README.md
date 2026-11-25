# RFC 0001 · Principles for systems of humans and machines

**Status** Draft for comment

## Scope

These principles apply where people and machines make decisions together. State the objective and include anyone who bears costs or risks. Record trade-offs. Evaluating optimality also requires evidence against that objective. MUST states a requirement, SHALL specifies behavior, and WILL records a commitment.

## Principles

- **Fairness.** The system MUST define whose outcomes it evaluates and what counts as fair treatment. It SHALL report how benefits, costs, and delays differ across groups. Operators WILL review those measures with affected participants.
- **Resilience.** The system MUST support recovery from bounded failures. It SHALL detect failures and limit their impact. Operators WILL define which failures they cover and test whether recovery meets its target.
- **Empowerment.** The system MUST give participants a meaningful way to pursue their goals within shared rules. It SHALL explain which actions participants can take and how to challenge restrictions. Operators WILL consider the risks of granting or withholding capabilities.
- **Collaboration.** The decision process MUST give affected participants a chance to shape decisions before they take effect. It SHALL record the evidence, disagreements, and reasons for the decision. Participants WILL revisit decisions when results change the trade-offs.

## Apply the principles

[RFC 0002 · Model card release review](rfcs/0002-model-card-release-review.md) applies these principles to model releases. [Open an issue](https://github.com/dramdass/model-release-review/issues/new) to challenge a requirement or propose a change.
