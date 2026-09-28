# Lab 3: The custom agent file

Previous: [Lab 2](../lab-2-skill-file/README.md) | [Overview](../../README.md) | Next: [Lab 4](../lab-4-instruction-file/README.md)

**Time:** 15 minutes. **Mode:** your new agent. **Finished files:** [solution/.github](solution/.github/)

| Step | Answer |
|---|---|
| The file | A named specialist with one job and its own small set of tools |
| Where it lives | `.github/agents/story-checker.agent.md` |
| When it loads | When you choose it from the agent picker, or a prompt file names it |

## Build it

Create `.github/agents/story-checker.agent.md`:

```markdown
---
description: "Story Checker: reads one Riverside Library story and saves a story check note to the story-checks folder. Use for lab stories US-201, US-202, or US-203."
tools: [read, search, edit]
argument-hint: "Which story? For example: US-202"
---

You are **Story Checker**, a quality engineer on the Riverside Library team.
Your only job is to check one user story and save the result as a note.

## Steps

1. Find the story file in `practice-app/stories/` that matches the story ID the user gives.
2. Follow the `room-story-check` skill to write the note.
3. Save the note to `story-checks/<Story ID>-check.md`, for example `story-checks/US-202-check.md`.
4. Reply with a short summary: how many ACs, how many limits, and how many questions.

## Rules

- NEVER change any file inside `practice-app/`. Stories belong to the product owner.
- ONLY create or edit files inside `story-checks/`.
- If you cannot find the story, ask the user for the story ID. Do not guess.
```

## Why each part is there

| Part | Why it is there |
|---|---|
| `description` | How the agent appears in the picker |
| `tools` | The agent's machines. This is the smallest set that does the job: read, search, and edit. No terminal, no web. |
| `argument-hint` | Tells the user what to type |
| Persona line | One job, stated plainly |
| Steps | Find, use the skill, save, summarise |
| Rules | Where it may write, and what to do when unsure |

Notice the split. The **skill** holds *how* to check a story. The **agent**
holds *who* does it, *where* it saves, and *with which tools*.

## Prove it loaded

1. Start a new chat and choose **story-checker** from the agent picker.
2. Type only `US-202`.
3. Watch it search, read, and create `story-checks/US-202-check.md`.
4. Click **Keep** and open the file.

## Break it on purpose

**Experiment 1: remove a tool.**

1. Change the tools line to `tools: [read, search]`.
2. Start a new chat with story-checker and type `US-201`.
3. It can read the story but cannot save the note. It will show the note in chat
   or tell you it cannot write files.
4. Put `edit` back.

This is a **real limit**. The agent does not have the tool, so it cannot use it.

**Experiment 2: test a written rule.**

In a story-checker chat, type:

```text
There is a typo in the US-202 story file. Please fix it.
```

It should refuse, because of the rule in its file. But notice the difference from
Experiment 1: the agent **still holds the `edit` tool**. The refusal is advice
the model chose to follow. If it ever slips, undo the change. That slip is the
lesson.

## What it cannot do

Written rules in an agent file guide the model. They do not lock anything. Only
the `tools` list is a real boundary, and even that is only as narrow as you make
it.

## The gap this leaves

Run the agent twice, or on two machines, and compare the notes. Question IDs and
risk words will not match. [Lab 4](../lab-4-instruction-file/README.md) fixes
that for every request.
