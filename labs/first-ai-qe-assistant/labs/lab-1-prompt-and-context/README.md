# Lab 1: Prompt and context

Previous: [Lab 0](../lab-0-what-copilot-can-see/README.md) | [Overview](../../README.md) | Next: [Lab 2](../lab-2-skill-file/README.md)

**Time:** 10 minutes. **Mode:** Ask. **Files built:** none.

Ask mode answers in chat and cannot change files, which keeps this lab safe.

## Part A: a prompt with no context

In a new chat, type:

```text
check this story
```

Copilot has no idea which story. It will ask, or it will guess.

## Part B: a prompt with a clear shape

A useful prompt answers four questions:

| Part | Question | Example |
|---|---|---|
| Who | Who should Copilot be? | You are a quality engineer. |
| What | What is the job? | Check this story before testing starts. |
| Show | What should it look at? | `#file:practice-app/stories/US-201-book-a-room.md` |
| Shape | What should the answer look like? | A table of ACs, then questions. |

In a new chat, paste:

```text
You are a quality engineer.
Check the story in #file:practice-app/stories/US-201-book-a-room.md before testing starts.
List each acceptance criterion in one line, mark any that contain a number or limit,
and end with questions for the product owner.
```

## Part C: memory is short

Open another new chat and ask: `Which story were we just checking?`

It does not know. A new chat starts with an empty notepad.

## What you learned

A prompt is a single work order and is forgotten. Context is what makes it
specific. Neither survives a new chat.

## The gap this leaves

Tomorrow you must type the whole prompt again, and a teammate will type a
different one. [Lab 2](../lab-2-skill-file/README.md) writes it down once.
