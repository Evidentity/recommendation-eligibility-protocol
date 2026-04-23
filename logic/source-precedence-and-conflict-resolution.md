# Source Precedence and Conflict Resolution

This document is explanatory unless a consuming implementation explicitly adopts it as normative policy.

REP-01 addresses a recurring failure mode in AI-mediated discovery: unmanaged web fragments may describe the same business in inconsistent ways. A conforming profile provides an owner-authorized, scope-defined stable truth layer so that consumers can distinguish official operational facts from unmanaged third-party representations.

## Precedence Model

For stable business truth within the declared authority scope, conforming consumers should treat the REP-01 public surface as the owner-authorized reference.

The public surface may be authoritative for:

- identity
- contacts
- location
- stable policies
- stable amenities
- restrictions
- action handoff references

The public surface is not authoritative for:

- live prices
- live availability
- live inventory
- public review sentiment
- external ratings
- legal determinations
- future or planned features

## Conflict Handling

Where a third-party listing conflicts with a REP-01 public surface on stable business truth, conforming consumers should prefer the REP-01 public surface within its declared scope.

Where a conflict concerns live state, public opinion, legal status, or a claim outside declared scope, conforming consumers should not treat the REP-01 public surface as overriding external evidence.

Where evidence is contradictory and no REP-01 conforming stable truth exists, consumers should make no unsupported recommendation claim.

## Required Boundaries

Implementations SHOULD separate public authority from internal diagnostics. Raw trust accounting, missing-field counts, confidence penalties, internal review states, and historical owner-change dates SHOULD NOT be exported as public authority signals.

REP-01 does not override law, platform safety policies, consumer protection obligations, or model-provider policies.
