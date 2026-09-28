# Lab 2: The skill file

Previous: [Lab 1](../lab-1-prompt-and-context/README.md) | [Overview](../../README.md) | Next: [Lab 3](../lab-3-custom-agent-file/README.md)

**Time:** 15 minutes. **Mode:** Agent. **Finished files:** [solution/.github](solution/.github/)

| Step | Answer |
|---|---|
| The file | A playbook Copilot takes off the shelf only when a request matches it |
| Where it lives | `.github/skills/room-story-check/SKILL.md` |
| When it loads | On demand. Copilot reads only the `description` until a request matches. |

## Build it

At the top of the lab folder, create `.github/skills/room-story-check/` and add
two files.

`SKILL.md`:

```markdown
---
name: room-story-check
description: "Riverside Library lab: check a user story (US-201, US-202, or US-203) before testing starts. Lists the acceptance criteria, the limits worth testing at the edge, rules hidden outside the criteria, and questions for the product owner. Use when the user asks to check, review, or read a Riverside Library story."
---

# Story check

A playbook for reading one user story carefully before anyone designs tests.

## When to use

- Someone asks to check or review a story from `practice-app/stories/`.
- Someone shares a Riverside Library story file.

## Steps

1. Read the story file and the app overview in `practice-app/app-overview.md`.
2. List every acceptance criterion (AC) by number, each in one plain line.
3. Mark every AC that contains a number or a limit, such as a time or a character count.
4. Read the **Notes** section if there is one. List each note as a rule found outside the ACs.
5. List anything the story does not answer as a question for the product owner.
6. Fill in the [note template](./note-template.md).

## Rules

- Do not invent rules the story does not give. Ask a question instead.
- Keep every line short enough for a new team member to follow.
- This skill drafts the note in the chat only. Do not create or edit any files.
```

`note-template.md`: copy it from
[solution/.github/skills/room-story-check/note-template.md](solution/.github/skills/room-story-check/note-template.md).

## Why each part is there

| Part | Why it is there |
|---|---|
| `name` | The skill's unique handle. It **must** match the folder name. It also becomes the slash command `/room-story-check`. |
| `description` | The label on the shelf. Copilot compares requests against it, so it must use the words people really type. |
| Steps | The prompt from Lab 1, written down once. |
| Template link | Loaded only when the skill runs, which keeps the skill small until it is needed. |
| "Do not invent rules" | The most important quality rule for any AI helper that reads requirements. |
| "Chat only" | Keeps the skill as advice. Saving files is a job for an agent. |

## Prove it loaded

1. Start a new chat in Agent mode.
2. Type only: `Check the Riverside Library story US-202`
3. Near the top of the answer, look for Copilot reading `SKILL.md`. That is the
   playbook coming off the shelf.
4. Now call it by name: `/room-story-check US-202`.

## Break it on purpose

1. Rename the folder to `room-story-checker`, but leave `name: room-story-check`
   inside the file.
2. Start a new chat and repeat step 2 above.
3. The skill no longer loads. Rename the folder back.

Then try a request that does **not** match the description, such as
`Summarise the app overview`. The skill should stay on the shelf.

## What it cannot do

A skill advises. It cannot save a file, and it cannot stop Copilot from ignoring
a step. It also only helps when its description matches the request.

## The gap this leaves

The note lives only in chat. The playbook can advise, but it cannot act.
[Lab 3](../lab-3-custom-agent-file/README.md) gives the job to a specialist
with tools.
