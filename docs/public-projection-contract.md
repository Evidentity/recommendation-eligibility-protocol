# Public Projection Contract

The Public Projection Contract declares which parts of a governed profile are exposed as public machine-facing truth and which parts remain internal.

## Required Function

A conforming contract MUST identify:

- authoritative machine-public sections
- bounded machine-public sections
- internal-only sections
- what the profile is authoritative for
- what the profile is not authoritative for
- live-state handoff rules
- scenario projection rules

## Public Authority

Public authority is limited to declared scope. Consumers should not infer authority beyond the fields and categories explicitly exposed.

## Internal Discipline

Internal verification posture, raw trust accounting, missing-field counts, review notes, and diagnostic penalties MAY exist but MUST NOT be presented as public authority signals.

## Consumer Interpretation

Conforming consumers should read the contract before treating any section as authoritative.
