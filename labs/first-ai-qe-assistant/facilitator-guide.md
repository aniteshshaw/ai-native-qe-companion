# Facilitator guide: Building Your First AI QE Assistant

For anyone running the lab with a group. Keep this file away from participants
until Lab 6 is finished, because it contains the answer key.

## Before the day

- Do a full dry run from an empty `.github` folder, Lab 0 to Lab 6.
- Record the date, VS Code version, and Copilot version in the lab README.
- Announce one model for everyone and ask people to keep it for every lab.
- Prepare a clean VS Code profile, or a way to switch off unrelated skills.
- Check that every machine shows **Local** in the **Session Target** control of a new
  chat. Handoff buttons (Lab 5) and the agent tool names (Labs 3 and 5) only work
  in the Local harness.
- Plan one helper for every ten people.

## Run of show (90 minutes)

| Time | Section |
|---|---|
| 0 to 5 | Welcome. The goal is to understand the files, not to produce test cases. |
| 5 to 8 | Lab 0 |
| 8 to 18 | Lab 1 |
| 18 to 33 | Lab 2 |
| 33 to 48 | Lab 3 |
| 48 to 58 | Lab 4 |
| 58 to 73 | Lab 5 |
| 73 to 83 | Lab 6 |
| 83 to 90 | Recap and questions |

Protect Lab 6. If you run late, shorten the Lab 5 debrief instead.

## Table roles

| Role | Job |
|---|---|
| Driver | Types in VS Code |
| Navigator | Reads the lab and checks exact paths and names |
| Observer | Watches which skill, agent, and tools Copilot uses |
| Breaker | Leads the "Break it on purpose" step |
| Reporter | Gives the one-minute debrief |

Rotate the driver and navigator every lab.

## Key moments

| Lab | Ask the room |
|---|---|
| 0 | "Who got a description of a file that does not exist?" |
| 1 | "Who had a new chat remember the story?" (Nobody should.) |
| 2 | "Who saw `SKILL.md` load without naming it? Who stopped it loading by changing only the description? So which field decides when a skill loads?" |
| 3 | "Removing `edit` stopped the agent. The written rule only asked it to stop. Which one would you trust?" |
| 4 | Two tables read their question IDs aloud before and after the file. They now match. |
| 5 | Before the lab, check every table has **Session Target** set to **Local**. Then: "What changed when `send` was `true`? What did you stop doing?" |
| 6 | Collect answers to "Which rows would survive a model that ignores every instruction?" |

## Lab 6 answer key

| Behavior | File | Guidance or real limit |
|---|---|---|
| `Q-US203-01` style IDs | Instruction file | Guidance |
| Status line at the top | Instruction file | Guidance |
| Checker refused to edit a story | Custom agent rules | Guidance. It still held `edit`. |
| Reviewer could not change the note | Custom agent `tools` list | Real limit |
| Checker could not save after `edit` was removed | Custom agent `tools` list | Real limit |
| Skill loaded without being named | Skill `description` | Guidance. It depends on the match. |
| Workflow waited before each handoff | `send: false` in handoffs | Human checkpoint, not a gate |

**Question 1:** only the `tools` rows hold if the model ignores instructions.

**Question 2:** a rule that must never break needs a workflow hook, which runs
outside the model. See Chapter 7.

## What the Reviewer should catch in US-203

Use these to judge whether the Lab 5 relay worked. The first three are in the
Notes section, which is the point of the story.

1. Members under 16 need a guardian listed before they can check in.
2. Accessible rooms are held until 1 hour before the start time.
3. A member must see the new room if staff move the booking.
4. AC 1 has a limit: the button appears from 10 minutes before the start.
5. AC 3 has a limit: the email arrives within 5 minutes.
6. AC 4 has a limit: release after 15 minutes without check-in.
7. A question the story does not answer: what happens if the email never arrives?
8. A question the story does not answer: can a member check in to a released booking?

If the Reviewer misses some of these, that is a useful result. The Reviewer is
AI too.

## If someone falls behind

Give them the solution for the lab they missed and keep the group moving. Do not
debug for more than two minutes. See *Catching up* in the lab README.
