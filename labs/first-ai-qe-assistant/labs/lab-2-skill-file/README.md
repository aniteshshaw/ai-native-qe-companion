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
| `name` | The skill's handle. It becomes the slash command `/room-story-check`. Use only lowercase letters, numbers, and hyphens. Keep it the same as the folder name (see the note in *Break it on purpose*). |
| `description` | The label on the shelf. Copilot compares requests against it, so it must use the words people really type. The description, not the folder name, decides whether the skill loads by itself. |
| Steps | The prompt from Lab 1, written down once. |
| Template link | Loaded only when the skill runs, which keeps the skill small until it is needed. |
| "Do not invent rules" | The most important quality rule for any AI helper that reads requirements. |
| "Chat only" | Keeps the skill as advice. Saving files is a job for an agent. |

## Prove it loaded

1. Start a new chat in Agent mode, with **Session Target** set to **Local**.
2. Type only: `Check the Riverside Library story US-202`
3. Near the top of the answer, look for a step that shows Copilot read `SKILL.md`.
   It may be inside the collapsed list of steps. That is the playbook coming off
   the shelf.
4. Now call it by name: `/room-story-check US-202`.

## Break it on purpose

**Experiment 1: change the label on the shelf.**

1. In `SKILL.md`, replace the description with this one:
   `description: "Formats release notes for the Riverside Library app. Use when the user asks for release notes."`
2. Start a new chat and type `Check the Riverside Library story US-202`.
3. Copilot answers without reading `SKILL.md`. Your request no longer matches the
   label, so the playbook stays on the shelf.
4. Now type `/room-story-check US-202`. The skill runs, because the slash command
   comes from the `name`, not from the description.
5. Put the original description back.

This shows the two jobs. The **description** decides when Copilot picks the
skill by itself. The **name** is the handle you call it by.

**Experiment 2: break the name.**

1. Change `name: room-story-check` to `name: Room Story Check`. Capitals and
   spaces are not allowed in a skill name.
2. Start a new chat and type `/`. The `/room-story-check` command is gone. The
   skill also stops loading for `Check the Riverside Library story US-202`.
   VS Code skips a skill with an invalid name and shows no error, so a typo here
   fails silently.
3. Put the name back.

Then try a request that does **not** match the description, such as
`Summarise the app overview`. The skill should stay on the shelf.

> **What about the folder name?** You may read that the folder must have the
> same name as `name:`. The Agent Skills standard says so. But when testers
> renamed the folder, VS Code still loaded the skill (October 2026). Keep the
> two the same anyway, because other tools that read skills do enforce it.

## What it cannot do

A skill advises. It cannot save a file, and it cannot stop Copilot from ignoring
a step. It also only helps when its description matches the request.

## The gap this leaves

The note lives only in chat. The playbook can advise, but it cannot act.
[Lab 3](../lab-3-custom-agent-file/README.md) gives the job to a specialist
with tools.
