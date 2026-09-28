# Telemetry test scenarios

The telemetry pipeline is a software product. Test it before you trust the dashboard. These are the scenarios to cover; the implementation is yours.

## Correlation

- [ ] Completion event without a start event
- [ ] Start event without a completion event
- [ ] Duplicate completion event
- [ ] Two identical tool calls running concurrently
- [ ] Corrupted temporary pairing state
- [ ] Agent process terminated before cleanup
- [ ] Session resumed after a long delay
- [ ] Parent stopped before a subagent

## Privacy

- [ ] No prompt, response, secret, or business content is ever written
- [ ] `user_id` is a keyed pseudonymous identifier, never a raw or unsalted-hashed username
- [ ] Rare team, repository, or workspace combinations cannot identify a person indirectly
- [ ] Every collected field has a documented reason
- [ ] Users are told what is collected, why, and what is not

## Parser and schema

- [ ] Missing, new, or reordered columns
- [ ] Unknown event type; invalid timestamp; duplicate event; events out of order
- [ ] Missing session stop; stop without start; completion without start
- [ ] Embedded comma or newline; byte-order mark; mixed line endings; mixed time zones
- [ ] Truncated final row; concurrent append; schema-version mismatch
- [ ] `error_category` value not in `schema/error-categories.yaml`; raw provider message written instead of a category
- [ ] Spreadsheet formula injection: neutralize fields beginning with `=`, `+`, `-`, or `@`

## Performance and failure

- [ ] Hook p50, p95, and p99 duration within the agreed budget
- [ ] Telemetry destination unavailable: buffer and continue (analytics hook fails open)
- [ ] A hook that enforces security, authorization, or policy: fails closed
- [ ] Malformed event, locked state, partial write, double delivery, hook timeout
- [ ] The dashboard shows telemetry health separately from agent health
