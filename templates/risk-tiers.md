# Risk tiers: from "Governing AI Quality Systems"

Classify a capability by what it can actually do, not by whether it is called AI. The tier decides the controls. These tiers are the book's model; name them however your organization already does.

| Tier | What it does | Examples | Controls it must have |
|---|---|---|---|
| **1 Advisory** | Suggests; a human does everything | Summaries, test ideas | Disclosure, owner, version, evaluation sample, feedback path |
| **2 Read-only analysis** | Reads real data and reports | Querying results, clustering failures, reviewing logs | Tier 1 plus data permissions, privacy review, groundedness checks, monitoring |
| **3 Reversible drafts** | Proposes a change a human reviews before it lands | Drafted test, pull request, locator repair | Tier 2 plus human review of a visible diff, sandbox, protected branches, audit record |
| **4 Consequential action** | Changes production, closes a defect, approves a release, alters expected behavior | Config change, incident close | Do not automate silently. Explicit authorization, stronger evidence, builder/approver separation, tested rollback, incident plan |

## The decision path

1. Does it act, or only advise? Advise only -> **Tier 1**.
2. Does it only read data and report? Yes -> **Tier 2**.
3. Does a human review its change before anything lands? Yes -> **Tier 3**.
4. Can it change production, or a decision about people? Yes -> **Tier 4**.

The tier is a property of what the capability may do, and it moves the moment that changes. Match the controls to the new tier before the change ships, not after the first bad result.
