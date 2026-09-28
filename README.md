# AI-Native Quality Engineering: Companion

**AI-Native Quality Engineering**
*A Practical Field Guide to Building, Governing, and Measuring AI-Powered Quality Systems*
by **Anitesh Shaw** (First Edition, 2026)

> Help practitioners design, evaluate, govern, observe, and improve AI-enabled quality systems that teams can trust.

This repository is the companion to the book. The book teaches principles that last. This repository holds the parts that change faster than print: a hands-on lab, fill-in-the-blank templates, and a worked example.

Author website: https://aniteshshaw.github.io/

## About the book

Most teams now have AI helpers that write tests, review code, or triage failures. Few teams can say whether those helpers are right, who owns them, or how to switch them off. The book is a field guide for quality engineers, SDETs, automation architects, and QE leaders who need to introduce AI into quality work safely. It covers how to design a skill or agent with clear boundaries, test variable AI behavior, keep human decisions with humans, observe what the AI did without collecting private content, measure adoption honestly, and govern it all at team and enterprise scale.

## What is here

| Folder | What it is | Start here if you want to |
|---|---|---|
| [labs/first-ai-qe-assistant](labs/first-ai-qe-assistant/) | A 90-minute hands-on lab | See how skills, agents, instruction files, prompt files, and handoffs actually work |
| [templates](templates/) | Twelve fill-in-the-blank artifacts | Write a quality contract, evaluation case, capability record, or 90-day plan |
| [examples/agentops-telemetry](examples/agentops-telemetry/) | A privacy-safe telemetry example | Observe AI helpers without collecting prompt content |

## The hands-on lab

**[Building Your First AI QE Assistant](labs/first-ai-qe-assistant/)** is the companion to Chapter 2, *Anatomy of an AI Teammate*. It teaches how each GitHub Copilot customization file works, one file per lab. In every lab you build the file, prove it loaded, and then break it on purpose to see what it does not control.

| Lab | You learn | Book chapter |
|---|---|---|
| 0 | [What Copilot can see](labs/first-ai-qe-assistant/labs/lab-0-what-copilot-can-see/) | 2 |
| 1 | [Prompts and context](labs/first-ai-qe-assistant/labs/lab-1-prompt-and-context/) | 2 |
| 2 | [Skill files](labs/first-ai-qe-assistant/labs/lab-2-skill-file/) | 2, 3 |
| 3 | [Custom agent files and tool limits](labs/first-ai-qe-assistant/labs/lab-3-custom-agent-file/) | 2, 3 |
| 4 | [Always-on instruction files](labs/first-ai-qe-assistant/labs/lab-4-instruction-file/) | 2 |
| 5 | [Prompt files and handoffs](labs/first-ai-qe-assistant/labs/lab-5-prompt-files-and-handoffs/) | 6 |
| 6 | [Proving what each file did](labs/first-ai-qe-assistant/labs/lab-6-prove-what-each-file-did/) | 4, 7 |

No coding is needed. The practice app, Riverside Library Room Booking, and all its data are fictional. Facilitators running it with a group can use the [facilitator guide](labs/first-ai-qe-assistant/facilitator-guide.md).

## Templates

Ready-to-use versions of the artifacts the book builds, one file each. Copy a template, fill in the blanks, delete the guidance comments, and you have a working first draft. Each template names the chapter it comes from.

### How to use the templates

- Start with the smallest artifact the job needs. If you are not sure which, read [templates/capability-decision-ladder.md](templates/capability-decision-ladder.md) first.
- **Every example value is illustrative.** Replace it. Do not ship the samples, and do not read any number here as a benchmark or a guarantee. Measure numbers in your own context.
- The order the book recommends: prove one bounded capability, make it supportable, then decide to scale. The templates below map to that order.

### The template files

| File | From the chapter | What it is |
|---|---|---|
| [quality-contract.yaml](templates/quality-contract.yaml) | Proving It Still Works | The bounded spec that makes a capability testable |
| [evaluation-case.yaml](templates/evaluation-case.yaml) | Proving It Still Works | One test case: fixture, expected and forbidden behavior |
| [evaluation-scorecard.md](templates/evaluation-scorecard.md) | Proving It Still Works | Eight dimensions scored 0 to 3, plus a release rule |
| [capability-record.yaml](templates/capability-record.yaml) | Governing AI Quality Systems | Owners, tier, tools, kill switch, rollback |
| [risk-tiers.md](templates/risk-tiers.md) | Governing AI Quality Systems | The four tiers and the controls each requires |
| [incident-runbook.md](templates/incident-runbook.md) | Governing AI Quality Systems | The questions a kill switch must answer, tested in a drill |
| [data-contract.yaml](templates/data-contract.yaml) | Test Data, Privacy, and Synthetic Data | Class, transformation, prohibited fields, retention |
| [failure-policy.md](templates/failure-policy.md) | Governing AI Quality Systems | A chosen failure policy per dependency |
| [ninety-day-plan.md](templates/ninety-day-plan.md) | Your First 90 Days | Three thirty-day acts, with a gate at the end of each |
| [api-coverage-checklist.md](templates/api-coverage-checklist.md) | API and Contract Quality with AI | The five regions of API coverage |
| [accessibility-checklist.md](templates/accessibility-checklist.md) | Accessibility and Inclusive AI Quality | The testing layers and the AI-specific cases |
| [capability-decision-ladder.md](templates/capability-decision-ladder.md) | Appendix E, Choosing the Smallest Useful AI Capability | Build or buy, and how much machine is enough |

## Examples

Larger, runnable-shaped assets live under `examples/`:

- [examples/agentops-telemetry/](examples/agentops-telemetry/): the privacy-safe event schema, a governed list of error categories, a metric dictionary, synthetic fixtures, and the telemetry test scenarios from the chapters *Workflow Hooks, the Nervous System*, *Measuring Adoption Without Fooling Yourself*, *Governing AI Quality Systems*, and *The AI-Native QE Platform*. The durable architecture stays in the book; the implementation-specific scripts and dashboards stay in your own repository.

## Confidentiality

These templates are generic and contain no employer, client, product, repository, or personal data. Keep them that way when you fill them in for anything public: use sanitized names and sample data, and classify real data before it goes anywhere (see [templates/data-contract.yaml](templates/data-contract.yaml)).

## Use these safely

- Every example value is illustrative. Replace it and measure your own numbers.
- Instructions guide an AI helper. They do not enforce anything. Use code for hard limits.
- Never put secrets, credentials, or real customer data in a prompt, template, or lab file.
- Inspect, test, and adapt every file before you use it in real work.

## Disclaimer

This is an independent educational project written in the author's personal capacity. The views expressed do not represent any employer, client, customer, or business partner.

Examples are synthetic, generalized, composite, sanitized, independently created, or based on public sources. No confidential information, proprietary code, private architecture, credentials, customer data, or internal business material is intentionally included.

The content and companion materials are provided for educational purposes and on an "as is" basis. AI, software, security, privacy, accessibility, and platform guidance should be independently reviewed and tested before real-world use. Product names and trademarks belong to their respective owners and do not imply endorsement.

## Versions

| Item | Value |
|---|---|
| Book edition | First Edition, 2026 |
| Companion version | See [CHANGELOG.md](CHANGELOG.md) |
| Lab last verified | See the top of the [lab README](labs/first-ai-qe-assistant/README.md) |
| Maintainer | Anitesh Shaw |

Product features change faster than a printed book. If a lab step no longer matches your tools, check the official documentation and [open an issue](https://github.com/aniteshshaw/ai-native-qe-companion/issues) with the book edition, the lab or template name, and what you saw. See [CONTRIBUTING.md](CONTRIBUTING.md) before proposing a change, and [SECURITY.md](SECURITY.md) to report a security concern privately.

## License

Copyright (c) 2026 Anitesh Shaw.

- Templates, schemas, fixtures, and lab solution files are licensed under the [MIT License](LICENSE).
- Written guides (README files, lab instructions, the facilitator guide, and the practice app stories) are licensed under [Creative Commons Attribution 4.0 International](LICENSE-docs).

The book itself is not covered by these licenses. All rights in the book are reserved.
