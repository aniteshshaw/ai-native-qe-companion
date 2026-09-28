# Lab 5: Prompt files and handoffs

Previous: [Lab 4](../lab-4-instruction-file/README.md) | [Overview](../../README.md) | Next: [Lab 6](../lab-6-prove-what-each-file-did/README.md)

**Time:** 15 minutes. **Finished files:** [solution/.github](solution/.github/)

| Step | Answer |
|---|---|
| The files | A prompt file is a saved work order. A handoff is a button that passes work from one agent to another. |
| Where they live | `.github/prompts/story-check.prompt.md`, and `handoffs:` inside agent files |
| When they load | The prompt file runs when you type `/story-check`. Handoff buttons appear after an agent answers. |

The idea is a maker and a checker. The Checker writes. The Reviewer reads, and
has no tool to write with.

```mermaid
flowchart LR
    P["/story-check"] --> C[Story Checker<br/>read, search, edit]
    C -->|Send to Reviewer| R[Story Reviewer<br/>read, search]
    R -->|Send fixes to Checker| C
    R --> H[You decide when it is done]
```

## Build it

**Part A: the Reviewer.** Copy
[solution/.github/agents/story-reviewer.agent.md](solution/.github/agents/story-reviewer.agent.md)
into `.github/agents/`. Read it before you move on. Notice three things:

- `tools: [read, search]`. The Reviewer physically cannot change the note.
- A fixed output format: Verdict, Gaps, Questions. Reviews become comparable.
- "On a second review, check only the gaps you listed before." Without this, the
  loop can produce new small complaints forever.

**Part B: give the Checker a handoff.** Add this to the front matter of
`story-checker.agent.md`, after `argument-hint`:

```yaml
handoffs:
  - label: Send to Reviewer
    agent: story-reviewer
    prompt: Review the story check note I just saved against the story, including its Notes section.
    send: false
```

And add this section above `## Rules`:

```markdown
## When the Reviewer sends work back

- Fix only the items the Reviewer listed.
- Keep the existing question IDs. New questions get the next number.
```

**Part C: the prompt file.** Create `.github/prompts/story-check.prompt.md`:

```markdown
---
description: "Start the story check workflow: check one Riverside Library story, save the note, then hand off to the reviewer."
agent: story-checker
argument-hint: "Story ID, for example US-203"
---

Check story **${input:storyId:US-203}**.

1. Find the story in `practice-app/stories/`.
2. Use the `room-story-check` skill.
3. Save the note to `story-checks/`.
4. When you are done, remind me to click **Send to Reviewer**.
```

| Part | What it does |
|---|---|
| `agent: story-checker` | Runs the prompt with that agent |
| `${input:storyId:US-203}` | Asks you for a value, with `US-203` as the default |
| `send: false` on a handoff | Fills in the next prompt but waits for you to press Enter |

## Prove it loaded

1. Start a new chat and type `/story-check`. Enter `US-203`.
2. The Checker saves `story-checks/US-203-check.md`. Click **Keep**.
3. Click **Send to Reviewer**. Read the verdict. Did it catch the rules in the
   Notes section?
4. Click **Send fixes to Checker**. The Checker updates the note.
5. Click **Send to Reviewer** again. The verdict should now be **Ready**.

## Break it on purpose

1. In the Checker's handoff, change `send: false` to `send: true`.
2. Run the workflow again. The handoff now sends by itself when you click the
   button, and you lose the moment where you read the prompt before it goes.
3. Change it back.

Then try a typo: change `agent: story-reviewer` to `agent: story-review`. The
handoff button breaks or disappears. Fix it.

## What it cannot do

A handoff is a human checkpoint, not a gate. Nothing stops you from clicking
through without reading. And the Reviewer is AI too, so it can share the
Checker's blind spots.

## Next

[Lab 6](../lab-6-prove-what-each-file-did/README.md) asks you to prove which
file caused each behavior you saw.
