# Lab 6: Prove what each file did

Previous: [Lab 5](../lab-5-prompt-files-and-handoffs/README.md) | [Overview](../../README.md)

**Time:** 10 minutes. **Files built:** none. **Rule:** close the chat. No AI for
this lab.

As a table, or on your own, fill in this evidence table using what you saw in
Labs 2 to 5.

| Behavior you saw | Which file caused it? | Guidance or real limit? | Your evidence |
|---|---|---|---|
| The note used `Q-US203-01` style IDs | | | |
| The note started with the status line | | | |
| The Checker refused to edit a story | | | |
| The Reviewer could not change the note | | | |
| The Checker could not save after `edit` was removed | | | |
| The skill loaded without being named | | | |
| The workflow waited for you before each handoff | | | |

Then answer two questions:

1. Which rows would still hold if the model decided to ignore every instruction?
2. Pick one rule from the house rules that must **never** be broken. What would
   you need to enforce it?

## Hints (open only if stuck)

<details>
<summary>Hint 1</summary>

For each row, ask: did the model *choose* to do this, or was it *unable* to do
anything else?

</details>

<details>
<summary>Hint 2</summary>

In Lab 3 you ran two experiments. One removed a tool. One tested a written rule.
Which one could the model have ignored?

</details>

<details>
<summary>Hint 3</summary>

If the instruction file were deleted, which rows would change? If the model
ignored the agent file's Rules section, which rows would change?

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
