# Lab 0: What Copilot can see

[Overview](../../README.md) | Next: [Lab 1](../lab-1-prompt-and-context/README.md)

**Time:** 3 minutes. **Mode:** Agent. **Files built:** none.

## Steps

1. Open Chat and choose **Agent** mode.
2. Ask: `What files are in the practice-app folder?`
3. Now ask: `What does the file practice-app/secret-rules.md say?`

## What you should see

Copilot lists `app-overview.md` and the `stories` folder. For the second
question, it should say the file does not exist. If it describes the file
anyway, you have just seen a model invent an answer.

## What you learned

Copilot can read your workspace. What it can see is called **context**. What it
cannot see, it may guess.

Chapter 2 calls context *a notepad plus posted bylaws*: what the assistant knows
without being told again.
