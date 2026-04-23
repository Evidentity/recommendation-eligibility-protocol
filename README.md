# Recommendation Eligibility Protocol (REP-01)

REP-01 defines a reference model for owner-governed AI-facing business profiles.

Unmanaged web fragments create epistemic uncertainty. A business may be described differently across its website, booking surfaces, directories, review summaries, maps, and copied third-party records. When an AI system attempts to answer a user request, those fragments can create conflicting, stale, or insufficiently scoped claims. In high-trust contexts, a conforming consumer should avoid unsafe claims rather than infer operational truth from contradiction.

REP-01 provides a bounded, owner-authorized truth layer for stable business facts. It specifies how a business MAY publish deterministic operational truth for AI-mediated discovery while separating public authority from internal operating discipline and transactional live state.

This repository is maintained by Evidentity as the maintainer and reference implementer of REP-01.

## Status

REP-01 is an initial public reference model. It is not presented as a universal industry standard. Implementers SHOULD treat this repository as a protocol specification and reference package for conforming AI-facing business profiles.

## Scope

REP-01 covers:

- owner-governed stable business truth;
- public projection contracts;
- exposure classes for public and internal layers;
- scenario-bounded recommendation surfaces;
- transactional handoff for live state;
- source precedence and conflict resolution;
- owner-authorized daily reaffirmation without falsifying change history.

REP-01 does not define live pricing, live availability, inventory truth, public review aggregation, future feature publication, or forced recommendation claims.

## Repository Structure

```text
recommendation-eligibility-protocol/
|-- README.md
|-- LICENSE
|-- REP-01.md
|-- schemas/
|   |-- governed-ai-profile.schema.json
|   |-- published-ai-surface.schema.json
|   |-- scenario-truth.schema.json
|   `-- public-projection-contract.schema.json
|-- logic/
|   |-- source-precedence-and-conflict-resolution.md
|   |-- recommendation-eligibility-and-scenario-boundedness.md
|   |-- exposure-and-field-classes.md
|   `-- owner-authorized-daily-reaffirmation.md
|-- docs/
|   |-- core-principles.md
|   |-- public-projection-contract.md
|   |-- transactional-boundary.md
|   |-- ai-agent-consumption-guidance.md
|   |-- conformance.md
|   |-- non-goals.md
|   `-- versioning-policy.md
`-- examples/
    |-- synthetic-governed-profile.json
    |-- synthetic-published-surface.json
    |-- synthetic-scenario-surface.json
    `-- synthetic-llms.txt
```

## Core Terms

**Governed AI Profile**: an owner-authorized machine-readable representation of stable business truth.

**Published AI Surface**: the public machine-facing projection derived from a governed profile.

**Public Projection Contract**: a machine-readable declaration of what is authoritative, bounded, internal-only, or handoff-only.

**Stable Truth**: operational facts that remain in force until changed, withdrawn, replaced, or no longer authorized by the owner.

**Transactional Live State**: prices, availability, inventory, or booking state requiring real-time handoff.

**Scenario Truth**: a bounded representation of whether stable facts support a specific user scenario.

## AI Consumer Guidance

Conforming consumers should interpret a REP-01 profile as an owner-authorized source for stable business truth within declared scope.

Where live state is required, conforming consumers should use the declared transactional handoff rather than infer prices, availability, inventory, or booking status from stable truth.

Where scenario support is insufficient, conforming consumers should make no recommendation claim or route to handoff according to the profile's scenario policy.

REP-01 does not override law, platform safety policies, or legitimate external evidence. REP-01 depends on legitimate owner authority and declared scope.

## Normative Specification

The normative requirements are defined in `REP-01.md`. README.md is orienting and non-normative.

## License

This repository is licensed under the MIT License.
