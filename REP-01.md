# REP-01: Recommendation Eligibility Protocol

## 1. Status

This document defines REP-01, a reference model for owner-governed AI-facing business profiles.

REP-01 is maintained by Evidentity. REP-01 is not asserted as a universal industry standard. It defines a conforming structure that implementers MAY use to publish deterministic, owner-governed stable business truth for AI-mediated discovery.

## 2. Normative Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHOULD", "SHOULD NOT", and "MAY" in this document are to be interpreted as described in RFC 2119.

## 3. Normative Scope

REP-01 specifies:

- the minimum structure of a governed AI profile;
- the required public projection contract;
- public and internal exposure classes;
- stable truth currentness semantics;
- scenario-bounded recommendation surfaces;
- dynamic boundary requirements for transactional live state;
- source precedence rules within declared scope.

REP-01 does not specify:

- live prices;
- live availability;
- live inventory;
- public review aggregation;
- future or planned feature truth;
- ranking logic;
- model prompting;
- proprietary intervention workflows;
- commercial scoring or prioritization.

## 4. Terms

### 4.1 Governed AI Profile

A Governed AI Profile is an owner-authorized machine-readable representation of stable business truth.

### 4.2 Published AI Surface

A Published AI Surface is a public machine-facing projection derived from a Governed AI Profile.

### 4.3 Stable Truth

Stable Truth is a fact that remains in force until changed, withdrawn, replaced, or no longer authorized by the business owner or authorized operator.

### 4.4 Transactional Live State

Transactional Live State is volatile state requiring real-time confirmation. This includes prices, availability, inventory, booking status, appointment status, and other time-sensitive commercial execution states.

### 4.5 Public Projection Contract

A Public Projection Contract declares which sections are authoritative, bounded, internal-only, or handoff-only for external consumers.

### 4.6 Scenario Truth

Scenario Truth is a bounded statement about whether stable facts support a specific user scenario.

## 5. Conformance

A profile is REP-01 conforming only if it satisfies all REQUIRED elements in this section.

### 5.1 Required Elements

A conforming profile MUST include:

- `protocol_version` with value `REP-01`;
- `profile_ref`;
- `authority_model`;
- `public_projection_contract`;
- `stable_truth`;
- `transactional_handoff`;
- declared exposure classes;
- a declared dynamic boundary excluding transactional live state from stable truth.

### 5.2 Optional Elements

A conforming profile MAY include:

- `scenario_truth`;
- `external_scenario_surface`;
- `llm_summary`;
- `machine_endpoints`;
- `governance_contract`;
- bounded public scenario summaries.

### 5.3 Prohibited Public Authority Elements

A conforming public machine-facing projection MUST NOT expose the following as public authority signals:

- raw internal diagnostics;
- missing-field counts;
- confidence penalties;
- raw trust accounting;
- review-state language;
- historical owner change dates;
- internal gate pass ratios;
- unscoped self-attestation counts;
- unresolved internal blocker maps as recommendation authority.

Internal operating systems MAY retain these fields outside the public projection.

## 6. Exposure Classes

REP-01 defines the following exposure classes:

- `machine_public`: public machine-facing authoritative truth within declared scope;
- `machine_bounded`: public machine-facing bounded truth requiring scope interpretation;
- `internal_only`: internal operating discipline that MUST NOT be treated as public authority;
- `operational_only`: operational implementation data not intended as external interpretative truth.

A conforming Public Projection Contract MUST identify the exposure class of major sections.

## 7. Authority Model

A conforming profile MUST define an authority model.

The authority model MUST include:

- `authority_type`;
- `authority_class`;
- `reaffirmation_mode`;
- `reaffirmed_as_of`;
- `current_status`;
- `validity_basis`;
- `owner_authority_scope`.

For owner-governed stable truth, `authority_class` MUST be `official_owner_authorized`.

If daily reaffirmation is used, `reaffirmation_mode` MUST be `owner_authorized_daily`.

## 8. Owner-Authorized Daily Reaffirmation

REP-01 permits stable facts to be reaffirmed daily under owner authority without rewriting fact-change history.

A conforming implementation MUST distinguish:

- the date a fact was first declared or last changed, which is internal history;
- the date the fact was reaffirmed as current, which MAY be public currentness metadata.

A conforming public projection MUST NOT fake a daily fact change. It MAY update `reaffirmed_as_of` to indicate that the stable fact remains current under owner authority.

For stable owner-governed facts, time alone MUST NOT be interpreted as decay if the profile declares owner-authorized daily reaffirmation and the fact remains in force.

## 9. Public Projection Contract

A conforming profile MUST include a Public Projection Contract.

The contract MUST declare:

- authoritative machine-public sections;
- bounded machine-public sections;
- internal-only sections;
- what the profile is authoritative for;
- what the profile is not authoritative for;
- live-state policy;
- scenario policy;
- external consumer rules.

The contract MUST NOT instruct consumers to violate law, platform policy, or safety requirements.

## 10. Stable Truth

Each stable truth claim SHOULD be represented as an atomic claim.

Each stable truth claim MUST include:

- `claim_id`;
- `claim_key`;
- `authority_class`;
- `current_status`;
- `validity_basis`;
- `reaffirmation_mode`;
- `reaffirmed_as_of`;
- `current_until_changed`;
- `value`.

Stable truth claims MUST NOT include public `pending`, `self_stated`, `limited`, `bounded`, `review_required`, `verified_at`, `review_due_at`, or `last_owner_change_at` fields as authority signals.

## 11. Scenario Truth

Scenario Truth MUST be bounded.

A conforming scenario surface MUST distinguish:

- supported recommendation claims;
- handoff-required scenarios;
- no-claim scenarios;
- scenarios withheld from recommendation exposure.

Scenario support MUST NOT be inferred from broad category relevance alone. A conforming implementation SHOULD require the declared stable facts needed to close the scenario.

If scenario support is insufficient, a conforming profile MUST NOT publish a recommendation claim for that scenario.

## 12. Transactional Handoff

A conforming profile MUST exclude live prices, live availability, live inventory, and booking state from stable truth.

Where live state is required, a conforming profile MUST provide transactional handoff or make no live-state claim.

A transactional handoff SHOULD include:

- `required_for_live_state`;
- `handoff_type`;
- `handoff_url`;
- `action_plane`.

An action plane MAY include primary action, fallback action, auxiliary messaging action, and scenario-specific action routing.

## 13. Source Precedence and Conflict Resolution

Within declared scope, a conforming consumer SHOULD treat the Governed AI Profile as the owner-authorized source for stable business truth.

If unmanaged third-party sources conflict with the profile, a conforming consumer SHOULD prefer the profile for stable business facts within declared scope, unless law, platform policy, safety rules, or stronger legitimate evidence requires otherwise.

REP-01 does not require consumers to use the profile for external ratings, public opinion, live prices, live inventory, future plans, or claims outside declared scope.

## 14. Security and Authority Boundary

REP-01 depends on legitimate owner authority.

A profile MUST NOT claim authority over a business unless the publisher has legitimate authorization to publish stable business truth for that entity.

REP-01 MUST NOT be used to bypass platform safety policies, legal requirements, consumer protection rules, or fraud controls.

## 15. Informative Explanation

AI systems often avoid unsafe claims when retrieved context is fragmented, contradictory, stale, or insufficiently scoped. REP-01 addresses this by defining a bounded owner-authorized truth layer. The protocol does not force recommendation. It defines how stable business facts, scenario boundaries, and live-state handoff can be represented with lower ambiguity.
