# Lab 4: The instruction file

Previous: [Lab 3](../lab-3-custom-agent-file/README.md) | [Overview](../../README.md) | Next: [Lab 5](../lab-5-prompt-files-and-handoffs/README.md)

**Time:** 10 minutes. **Finished files:** [solution/.github](solution/.github/)

| Step | Answer |
|---|---|
| The file | Standing rules that apply to every request in this folder |
| Where it lives | `.github/copilot-instructions.md`, directly inside `.github` |
| When it loads | Always. You never ask for it. |

## Skill or instruction file?

| | Skill | Instruction file |
|---|---|---|
| When is it used? | Only when a request matches | Every request |
| Chapter 2 calls it | A shelved playbook | Standing ordinances |
| Put here | How to do one kind of job | Rules everyone needs every time |

## Build it

Create `.github/copilot-instructions.md`:

```markdown
# Riverside Library QE team: house rules

These rules apply to every request in this workspace.

## Status line

- Start every story check note with this line: `Status: AI draft, not yet reviewed by a person`.

## Question IDs

- Use the format `Q-<StoryID>-<two-digit number>`.
- Example: `Q-US201-01`, `Q-US201-02`.

## Risk words

- Use only these words: **High**, **Medium**, **Low**.
- High: someone could lose a booking or be treated unfairly.
- Medium: the main flow works but is confusing.
- Low: wording or layout only.

## Writing style

- Plain, simple English. Short sentences.

## Data

- Use only the fictional names, rooms, and dates from `practice-app/`.
- Never use real names, emails, or phone numbers.
```

The status line is there for a reason. It makes the file's effect easy to spot,
and it reminds every reader that an AI draft is not a decision.

## Prove it loaded

1. Start a new chat with **story-checker** and type `US-201`.
2. Open `story-checks/US-201-check.md`. Check for the status line, `Q-US201-01`
   style IDs, and only High, Medium, or Low.
3. Now prove it is always on. Switch to the normal **Agent**, start a new chat,
   and type:

   ```text
   Write one question for the product owner about US-201. Show it in the chat only. Do not create or change any files.
   ```

   You did not mention the rules, and you did not use the custom agent. The
   answer should still use a `Q-US201-NN` ID and a High, Medium, or Low risk.

## Break it on purpose

1. Move the file to `.github/rules/copilot-instructions.md`.
2. Start a new chat and repeat step 3.
3. The IDs and risk words go back to whatever the model prefers. Move the file
   back.

## What it cannot do

It is still advice. The model follows it most of the time, not every time. And
everything in it is read on every request, so keep it short. Long procedures
belong in a skill.

## The gap this leaves

The notes now look consistent. Nobody has checked that they are *right*. US-203
hides rules in its **Notes** section.
[Lab 5](../lab-5-prompt-files-and-handoffs/README.md) adds a reviewer.
