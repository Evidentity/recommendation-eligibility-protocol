# Conformance

This document summarizes conformance requirements. REP-01.md is the normative source.

## Required

A REP-01 conforming profile MUST include:

- protocol version
- entity reference
- authority model
- owner-authorized daily reaffirmation semantics
- public projection contract
- stable truth claims
- transactional handoff for live state

## Optional

A REP-01 conforming profile MAY include:

- bounded scenario surface
- public machine rules
- auxiliary action references
- human-readable continuity statement

## Prohibited

A REP-01 public surface MUST NOT export the following as public authority:

- live prices
- live availability
- inventory truth
- public review aggregation
- future or planned features
- raw trust accounting
- missing-field counts
- internal confidence penalties
- internal review-state language
- unsupported recommendation claims

## Internal Allowance

Internal systems MAY maintain diagnostics, review states, owner-change history, supersession chains, intervention notes, and trust accounting if those fields are not projected as public authority.
