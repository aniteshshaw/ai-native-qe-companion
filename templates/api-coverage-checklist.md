# API coverage checklist: from "API and Contract Quality with AI"

Coverage is not a count of tests. It is whether all five regions are exercised. A hundred tests of one region is a tall pile, not a wide map. Tag each generated test to a region; the empty region is where your next bug is hiding.

## The five regions

### Structure
- [ ] Required and optional fields, types, formats, ranges, enums match the contract
- [ ] Additional properties handled as intended
- [ ] Backward and forward compatibility

### Behavior
- [ ] Happy path
- [ ] Boundary values and negative conditions
- [ ] State transitions and idempotency
- [ ] Pagination, sorting, concurrency
- [ ] Timeout and retry behavior

### Security
- [ ] Authentication (proves identity)
- [ ] Authorization by object and action (proves permission): test the whole matrix
- [ ] Tenant isolation
- [ ] Sensitive response fields, rate limits, replay, token expiry

### Resilience
- [ ] Dependency failure and partial response
- [ ] Duplicate and out-of-order messages
- [ ] Retry storms and circuit-breaker behavior

### Consumer impact
- [ ] Consumer-driven contracts
- [ ] Deprecated fields still read by someone
- [ ] Changed defaults and semantic changes that remain schema-valid

## Guardrails

- [ ] A deterministic validator checks schema, protocol, and breaking changes
- [ ] Inferred business rules cite a source, or are marked UNKNOWN; never invented
- [ ] No live secret in any fixture or log; test data isolated and repeatable
- [ ] The specification is compared against runtime, consumers, and domain rules, not worshipped
- [ ] Coverage is reported by region, as five numbers, not one
