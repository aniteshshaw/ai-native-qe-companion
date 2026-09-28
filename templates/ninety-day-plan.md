# Your first 90 days: from "Your First 90 Days"

Do not start with a platform. Run one lap around the whole method, at the smallest useful scale. Three thirty-day acts, and a gate you must pass before the next.

## Days 1 to 30: prove the problem

- [ ] **Week 1: pick the workflow.** Frequent, bounded, reviewable, not high-consequence. Write the current workflow and a baseline (how long it takes, how good it is today).
- [ ] **Week 2: write the quality contract** (see quality-contract.yaml) and assign a risk tier (see risk-tiers.md).
- [ ] **Week 3: build the smallest useful thing.** Instruction, prompt, skill, or read-only agent. Version it from day one.
- [ ] **Week 4: baseline it.** Run the evaluation set with the capability and without it. Record failures, not just averages.

**Day 30 gate:** users can explain what it does and does not do; no unresolved severe safety or permission failure; real evidence it helped on at least one workflow.

## Days 31 to 60: make it supportable

- [ ] **Week 5: controls in code.** Validate schemas, tool parameters, allowed resources, forbidden actions, outside the model.
- [ ] **Week 6: make delivery boring.** Release notes, one-step install, tested rollback, a named version.
- [ ] **Week 7: privacy-safe observability.** Capability, version, outcome class, latency, error class, feedback. No prompt or business content.
- [ ] **Week 8: pilot with a small group.** Clear support channel and office hours. Their confusion is your backlog.

**Day 60 gate:** named owner and support path; rollback tested; high-risk failures tracked; human acceptance measured separately from invocations.

## Days 61 to 90: decide to scale

- [ ] **Week 9: harden it.** Every serious pilot failure becomes a regression case. Run the adversarial cases.
- [ ] **Week 10: governance review.** Data, tools, security, privacy, accessibility, decision rights (see capability-record.yaml).
- [ ] **Week 11: measure impact honestly.** Invocations, unique users, repeat users, accepted outputs, completed workflows, defects, estimated time saved, observed change in elapsed time. Keep estimated and observed apart.
- [ ] **Week 12: decide to scale, revise, or stop.**

**Day 90 decision:** scale only with real demand, acceptable risk, an operational owner, and an affordable support model. "Not yet" is a successful outcome.

## The line to hold

Let facts open the gates (severe failure? rollback run? tool exceeded permission?). Let a named person make the scale call (which workflow, is demand real, can we afford support, do we scale).
