# Building Your First AI QE Assistant

**A hands-on lab for the book *AI-Native Quality Engineering* by Anitesh Shaw.**
It is the companion to Chapter 2, *Anatomy of an AI Teammate*.

Chapter 2 explains where knowledge can live in an AI teammate: a prompt, context,
an instruction file, a skill, a tool, a custom agent, and a workflow hook. This
lab lets you build those files yourself, one at a time, and watch what each one
changes.

The goal is **to understand the files**, not to produce test cases. The AI
helpers you build do one small job, a *story check note*, so your attention stays
on the files and how they behave.

| | |
|---|---|
| Time | About 90 minutes |
| Level | Beginner. No coding needed. |
| You need | VS Code, GitHub Copilot with Agent mode, this folder |
| Practice app | Riverside Library Room Booking. Fictional, with fictional data. |
| Last verified | TBD (date, VS Code version, and GitHub Copilot version to be recorded after a dry run) |

> Product features change. If a step no longer matches your screen, check the
> official VS Code and GitHub Copilot documentation. The ideas in the book stay
> the same even when the menus move.

---

## The journey

Each lab ends by exposing a gap. The next lab closes it with one file. Do them
in order.

| Lab | The gap | The file that closes it | Chapter 2 calls it | Time |
|---|---|---|---|---|
| [0](labs/lab-0-what-copilot-can-see/README.md) | What can Copilot see? | None (context) | Notepad plus posted bylaws | 3 min |
| [1](labs/lab-1-prompt-and-context/README.md) | "Check this story" gets a guess | A clear prompt with context | A single work order | 10 min |
| [2](labs/lab-2-skill-file/README.md) | The good prompt is retyped every day | `SKILL.md` | A shelved playbook | 15 min |
| [3](labs/lab-3-custom-agent-file/README.md) | The note lives only in chat, and nothing limits what Copilot can touch | `.agent.md` with `tools:` | A hired role with a job description | 15 min |
| [4](labs/lab-4-instruction-file/README.md) | Every run formats IDs and risk words differently | `copilot-instructions.md` | Standing ordinances | 10 min |
| [5](labs/lab-5-prompt-files-and-handoffs/README.md) | Nobody checks the note before it is used | `.prompt.md` and `handoffs:` | A saved work order, passed between roles | 15 min |
| [6](labs/lab-6-prove-what-each-file-did/README.md) | Which of these files actually *stops* anything? | None. You decide. | The inspection gate you have not built yet | 10 min |

Finished files for Labs 2 to 5 are in each lab's `solution` folder.

## Folder map

```text
first-ai-qe-assistant/        Open THIS folder in VS Code
  README.md                   This page
  practice-app/               The fictional app and its three stories (read only)
  story-checks/               Where your AI helpers save their notes
  labs/                       Step-by-step instructions, one folder per lab
    lab-2-skill-file/solution/.github   Finished files, to check or catch up
  facilitator-guide.md        For anyone running the lab with a group
  .github/                    YOU build this during the labs
```

Copilot only reads the `.github` folder at the top of the folder you open. The
`solution` folders inside `labs/` are for checking your work or catching up.
Copilot does not read them where they are.

---

## How every lab works

Every lab from Lab 2 onward follows the same seven steps. Once you know the
pattern, you can use it to learn any new customization file.

| Step | The question it answers |
|---|---|
| **The file** | What is it, in one sentence? |
| **Where it lives** | Which folder and file name does Copilot look for? |
| **When it loads** | Always, or only when a request matches? |
| **Build it** | What goes inside, and why is each part there? |
| **Prove it loaded** | What evidence shows Copilot used it? |
| **Break it on purpose** | What small change makes it stop working? |
| **What it cannot do** | Where does its control end? |

The last two steps matter most. You only understand a file once you have seen it
fail.

---

## The files you will meet

The analogies are the same ones Chapter 2 uses, so the lab and the book tell one
story.

| File | Chapter 2 calls it | Where it lives | Always on or on demand | Advises or acts |
|---|---|---|---|---|
| Prompt | A single work order | The chat box | Once | Advises |
| Context | Notepad plus posted bylaws | What is open, attached, or in the chat | Current chat | Advises |
| Skill | A shelved playbook | `.github/skills/<name>/SKILL.md` | On demand | Advises |
| Tool | A machine to operate | Listed in an agent's `tools:` | When allowed | Acts |
| Custom agent | A hired role with a job description | `.github/agents/<name>.agent.md` | When chosen | Acts |
| Instruction file | Standing ordinances | `.github/copilot-instructions.md` | Always on | Advises |
| Prompt file | A saved work order | `.github/prompts/<name>.prompt.md` | When run with `/` | Starts work |
| Workflow hook | An automatic inspection gate | Not built in this lab | Always on | Enforces |

Keep one idea in mind throughout: **advice guides the model, and only a hook or
a missing tool actually stops it.** Every lab will show you where that line sits.

---

## Before you start

1. Open **this folder** (`first-ai-qe-assistant`) in VS Code with
   **File > Open Folder**. Do not open the whole repository. Copilot only reads
   the `.github` folder at the top of the folder you open.
2. Choose one model and keep it for every lab. Different models give different
   answers, and you want to see the effect of the files, not the model.
3. Confirm there is **no** `.github` folder here yet. You will build it.

---

## Catching up

Each lab from 2 to 5 has a `solution` folder with the finished `.github` folder
at the **end** of that lab. Each one builds on the one before.

| Folder | Contains | Use it to start |
|---|---|---|
| `labs/lab-2-skill-file/solution` | Skill and template | Lab 3 |
| `labs/lab-3-custom-agent-file/solution` | Plus the Story Checker agent | Lab 4 |
| `labs/lab-4-instruction-file/solution` | Plus the house rules | Lab 5 |
| `labs/lab-5-prompt-files-and-handoffs/solution` | Plus the Reviewer, handoffs, and `/story-check` | Lab 6 |

From this folder, in PowerShell:

```powershell
Copy-Item labs\lab-4-instruction-file\solution\.github -Destination . -Recurse -Force
```

On macOS or Linux:

```bash
cp -R labs/lab-4-instruction-file/solution/.github .
```

Change the folder name to the lab you just missed. Start a new chat afterwards.

---

## Troubleshooting

| Symptom | Check |
|---|---|
| The skill never loads | Does the folder name equal `name:`? Is `.github` at the top of the folder you opened? Did you start a new chat? |
| A different skill answers | Other skills installed on your machine may match. Call `/room-story-check` directly, or use a clean VS Code profile. |
| The agent is missing from the picker | The file must end in `.agent.md` and sit in `.github/agents/`. |
| Handoff buttons are missing | Check the YAML indentation. `agent:` must match the target file name without `.agent.md`. |
| `/story-check` is missing | The file must sit in `.github/prompts/` and end in `.prompt.md`. |
| House rules are ignored | The file must be exactly `.github/copilot-instructions.md`. |
| Files appeared during Lab 1 | You were in Agent mode, not Ask mode. Undo them and switch modes. |

Three checks solve most problems:

1. Is `.github` at the top of the folder you opened?
2. Does the folder or file name match exactly?
3. Did you start a **new chat** after changing a file?

---

## Where to go next in the book

| If you want to | Read |
|---|---|
| Understand why these files exist and how to choose between them | Chapter 2, *Anatomy of an AI Teammate* |
| Design a skill properly, including its description and boundaries | Chapter 3, *Designing a Skill*, and the appendix *Build Your First Skill* |
| Test a skill with normal, boundary, and hostile cases | Chapter 4, *Testing a Skill*, and the appendix *The Break the Skill Workshop* |
| Connect skills into a library with handoffs | Chapter 6, *From One Skill to a Library* |
| Enforce a rule the model cannot skip | Chapter 7, *Workflow Hooks, the Nervous System* |

---

Copyright (c) 2026 Anitesh Shaw. All rights reserved. The practice app, its
people, and its data are fictional.
