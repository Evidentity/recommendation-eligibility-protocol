# Exposure and Field Classes

This document is explanatory unless a consuming implementation explicitly adopts it as normative policy.

REP-01 requires an explicit split between what is public machine-facing truth and what remains internal operating discipline.

## Exposure Classes

`machine_public` means the section may be consumed as public, owner-authorized machine-facing truth.

`machine_bounded` means the section may be consumed only within declared scope and projection rules.

`internal_only` means the section is part of operating discipline and MUST NOT be treated as public authority.

`operational_only` means the section may be used by the system or operator but is not part of public machine authority.

## Field Classes

`stable_owner_governed` fields are stable business facts that can remain current until changed or withdrawn by the owner or authorized operator.

`stable_review_sensitive` fields are stable facts that may require internal review discipline but do not automatically decay solely because time passes.

`scenario_relevant_stable` fields are stable facts used to determine scenario support.

`transactional_live_state` fields require live handoff and MUST NOT be represented as canonical stable truth.

`internal_operating_discipline` fields are used for diagnostics, governance, review, or service operation and MUST NOT be exported as public authority.

## Prohibited Public Authority Signals

The following SHOULD remain internal:

- raw trust accounting
- missing-field counts
- historical owner change dates
- internal review states
- confidence penalties
- intervention status
- unpublished blocker maps
- commercial prioritization logic
