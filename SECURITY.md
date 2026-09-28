# Security policy

This repository holds templates, a telemetry example, and a hands-on lab. It contains no runnable service. Security concerns still matter here: a template or lab file could teach an unsafe pattern, or a contribution could leak a secret or real data.

## Reporting a concern

Please do not open a public issue for a security concern. Use GitHub's private vulnerability reporting instead: open the **Security** tab of this repository and choose **Report a vulnerability**.

Include the file path, what the concern is, and, if you can, a suggested fix. You will get an acknowledgement, and the fix will be recorded in [CHANGELOG.md](CHANGELOG.md).

## What counts

- A secret, credential, token, or real personal or customer data in any file
- A template or instruction that would lead a reader to grant broader permissions than needed
- A lab step that relies on an instruction file or prompt as a security boundary
- Guidance that would cause telemetry to collect prompt or business content

## What this repository promises

- All data is synthetic or fictional.
- Instructions in skills, agents, and prompt files guide a model. They do not enforce anything. Hard limits belong in code, tool permissions, or workflow hooks.
