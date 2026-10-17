# Lab 6: Prove what each file did

Previous: [Lab 5](../lab-5-prompt-files-and-handoffs/README.md) | [Overview](../../README.md)

**Time:** 10 minutes. **Files built:** none. **Rule:** close the chat. No AI for
this lab.

As a table, or on your own, fill in this evidence table using what you saw in
Labs 2 to 5.

**For the third column, choose one of two answers:**

- **Guidance:** a file *asked* the model to do it. The model could have done
  something else.
- **Real limit:** the model *could not* do anything else, because something it
  needed was missing.

**Here is one row filled in, as an example.** It is not one of the seven.

| Behavior you saw | Which file caused it? | Guidance or real limit? | Your evidence |
|---|---|---|---|
| The Checker saved its note in `story-checks/` | `story-checker.agent.md`, step 3 | Guidance | The step told it where to save. It holds `edit`, so it could have saved anywhere. |

Now fill in the seven rows:

| Behavior you saw | Which file caused it? | Guidance or real limit? | Your evidence |
|---|---|---|---|
| The note used `Q-US203-01` style IDs | | | |
| The note started with the status line | | | |
| The Checker refused to edit a story | | | |
| The Reviewer could not change the note | | | |
| The Checker could not save after `edit` was removed | | | |
| The skill loaded without being named | | | |
| The workflow waited for you before each handoff | | | |

If the handoff buttons never appeared for you in Lab 5, answer the last row from
the Lab 5 README: what does `send: false` do?

Then answer two questions:

1. Which rows would still hold if the model decided to ignore every instruction?
2. Pick one rule from the house rules that must **never** be broken. What would
   you need to enforce it?

## Hints (open only if stuck)

<details>
<summary>Hint 1: one test for every row</summary>

Ask one question: **could the model have done something else?** If yes, it is
guidance. If no, it is a real limit.

</details>

<details>
<summary>Hint 2: where each behavior came from</summary>

| Row | Look back at |
|---|---|
| 1 and 2 | Lab 4, the instruction file |
| 3 | Lab 3, Experiment 2 (the written rule) |
| 4 and 5 | The `tools:` line in an agent file: Lab 3, Experiment 1, and the Reviewer in Lab 5 |
| 6 | Lab 2, the skill's `description` |
| 7 | Lab 5, the `send:` setting on each handoff |

</details>

<details>
<summary>Hint 3: for question 1</summary>

Imagine a model that ignores every sentence in every file you wrote. What is
still true? A tool the agent was never given is still missing. Which rows does
that leave?

</details>

<details>
<summary>Hint 4: for question 2</summary>

A rule that must never break cannot live in a sentence the model reads, because
the model can ignore a sentence. It needs something that runs outside the model,
before or after the model acts.

</details>

## What you learned

<details>
<summary>Open after you have your answers</summary>

The answer to question 1 is the short list of real limits: a missing tool, and
nothing else you built today. The answer to question 2 is a workflow hook, which
runs outside the model. Chapter 7, *Workflow Hooks, the Nervous System*, is where
the book builds one.

</details>

## Where to go next

Go back to the [overview](../../README.md#where-to-go-next-in-the-book) for the
book chapters that take each file further.
