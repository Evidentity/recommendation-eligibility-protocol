# Recommendation Eligibility and Scenario Boundedness

This document is explanatory unless a consuming implementation explicitly adopts it as normative policy.

REP-01 does not model recommendation eligibility as broad relevance. It treats recommendation eligibility as a scenario-bounded condition: a business may be suitable for one user scenario and unsupported for another.

## Scenario-Bounded Interpretation

A scenario surface SHOULD expose only machine-usable scenario states:

- `supported_for_recommendation`
- `not_exposed_for_recommendation`
- `handoff_required`
- `no_claim`

The purpose is to prevent weak or incomplete scenario evidence from becoming an unsupported recommendation claim.

## No Average-Score Semantics

REP-01 does not require a universal score. A conforming implementation MAY maintain internal diagnostics, but those diagnostics MUST NOT be presented as public authority unless they are part of the published protocol surface.

## Unsupported Scenarios

Unsupported does not always mean negative. A scenario may be:

- explicitly unsupported by owner-declared limitation
- not sufficiently supported by stable facts
- dependent on live state
- outside declared scope
- withheld from recommendation projection

Public surfaces SHOULD use explicit states rather than ambiguous caution language.

## Handoff

Where stable truth cannot answer a scenario because live state is required, the consumer should use the declared transactional handoff.
