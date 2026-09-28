# Incident runbook: from "Governing AI Quality Systems"

A kill switch no one has tested is only a theory. Answer these on paper, then rehearse them in a drill before you need them.

## The questions, answered in advance

1. **How is the capability disabled, and who can do it right now?**
2. **How are its credentials or tokens revoked?**
3. **How do we list the outputs it produced in a given window?**
4. **Who assesses the impact on users, data, and production?**
5. **How are users told?**
6. **What becomes a new regression test, so this exact failure cannot return unseen?**
7. **What must be true before it goes back on?**

## Two habits that turn the list into a control

- **Run a disable drill on a schedule.** Find the missing credential owner in a drill, not in an incident. Record how long the drill actually took, from decision to fully off. That measured time is your most useful governance number; do not report a target as if it were a result.
- **Record the capability's actions as metadata.** Capture what it did and when, never the private content it handled, so question 3 has an answer.

## Stop conditions (pause first, discuss after)

Pause immediately when: the system changes a consequential intent without approval; a tool exceeds its permission boundary; sensitive content is collected that should not have been; or severe regressions recur without being caught. Review on a schedule when: users can no longer tell advice from authority, or support cost clearly exceeds demonstrated value.
