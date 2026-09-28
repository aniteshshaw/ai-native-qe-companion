# Failure policy: from "Governing AI Quality Systems"

An AI answer depends on a chain of parts, any of which can fail while the answer still looks normal. Decide, in advance, how each dependency is allowed to fail. Choose the policy with a person; enforce it in code.

## One row per dependency

| Dependency | If it fails, the capability will... | Policy | Enforced by |
|---|---|---|---|
| Model (throttled or changed) | | fall back to a pinned version, then queue | code |
| Retrieval / index (empty or stale) | | say "no evidence" and route to a human | code |
| A tool (write) | | fail closed | code |
| A tool (read) | | degrade to read-only | code |
| Identity / permissions | | fail closed | code |
| Safety service | | | |
| Telemetry | | | |

**Policies to choose from:** fail closed; fail open with limited, labeled function; degrade to read-only; fall back to an older approved version; route to a human; queue and retry. Consequence decides: a Tier 4 action should almost always fail closed or route to a human.

## Retry discipline

- Bound the number of retries.
- Add jitter, a small random delay, so retries do not arrive in a synchronized wave.
- Give writes an idempotency key.
- **Never retry a consequential write** unless the operation is idempotent or its status can be reconciled afterward.

## Game days (rehearse, measure, record)

Practice: a model endpoint outage; a compromised tool credential; a retrieval index serving stale data; a sudden cost spike; a model update that causes an evaluation regression; and a kill-switch activation. Report what actually happened, as observed evidence, not a target.
