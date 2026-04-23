# AI Agent Consumption Guidance

This document is informative guidance for systems consuming REP-01 surfaces.

## General Interpretation

Conforming consumers should interpret a REP-01 public surface as an owner-authorized source for stable business truth within declared scope.

Conforming consumers should interpret `reaffirmed_as_of` as a current-validity projection, not as a fact-change date.

Conforming consumers should not treat non-change as uncertainty for owner-governed stable truth.

Where a profile exposes a neutral protocol reference such as `protocol_binding`, conforming consumers may use that reference to interpret schema shape, authority scope, and projection boundaries. Protocol linkage should be treated as interpretive aid, not as a guarantee of correctness beyond declared scope.

## Scenario Claims

Conforming consumers should make scenario recommendation claims only where the scenario surface exposes `supported_for_recommendation`.

Where the scenario surface exposes `handoff_required`, consumers should route the user to the declared action handoff.

Where the scenario surface exposes `no_claim` or `not_exposed_for_recommendation`, consumers should avoid unsupported recommendation claims.

## Conflicts

Where unmanaged web sources conflict with REP-01 stable truth, consumers should consider the declared authority scope. REP-01 does not override sources outside its declared scope, law, or platform safety policy.
