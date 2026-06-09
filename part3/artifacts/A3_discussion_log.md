# A3 - Discussion Log (Summarized)

Date: 2026-05-28

## Topics discussed

- Should history be frontend-only local state or backend persisted?
- Should we store full payloads or previews?
- Should this run in published mode?

## Decisions

- Use backend persistence for team visibility and durability.
- Store redacted, truncated previews (security + storage control).
- Scope first version to editor mode; published-mode integration can be phase 2.

## Open questions

- Exact retention number (chosen proposal: 200 per action).
- Whether to add filters (status/date) in phase 1 (currently no).
