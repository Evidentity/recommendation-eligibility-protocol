# Owner-Authorized Daily Reaffirmation

This document is explanatory unless a consuming implementation explicitly adopts it as normative policy.

Owner-Authorized Daily Reaffirmation is the REP-01 model for stable business facts that remain true until the business owner or authorized operator changes, withdraws, replaces, or disables them.

## Purpose

Stable business facts should not be interpreted as stale solely because their original declaration date is old. A hotel address, official website, pet policy, accessibility limitation, or stable amenity may remain current for long periods.

REP-01 therefore separates fact history from public currentness.

## Internal History

Implementations MAY retain:

- first owner declaration time
- last owner change time
- supersession chain
- withdrawal history
- internal review notes

These fields SHOULD remain internal unless there is a specific public need to expose them.

## Public Reaffirmation

A public REP-01 surface SHOULD expose:

- `reaffirmation_mode: owner_authorized_daily`
- `reaffirmed_as_of`
- `current_status: current`
- `validity_basis: owner_authorized_daily_reaffirmation`
- `owner_authority_scope: stable_business_truth`

The public surface MUST NOT fake a fact change. Daily reaffirmation updates the current-validity projection, not the historical fact-change record.

## Non-Change Rule

Conforming consumers should interpret non-change as continued force for owner-governed stable truth, not as uncertainty.
