# Transactional Boundary

REP-01 requires a hard boundary between stable business truth and live commercial state.

## Stable Truth

Stable truth includes facts that can remain current until changed or withdrawn by the owner or authorized operator.

Examples include:

- identity
- location
- official contacts
- stable policies
- stable restrictions
- stable amenities
- direct booking endpoint references

## Live State

Live state includes facts that require real-time confirmation.

Examples include:

- prices
- availability
- room inventory
- time-sensitive offers
- booking completion status

## Handoff

Where live state is required, conforming consumers should use the declared transactional handoff and should not infer live state from stable truth.
