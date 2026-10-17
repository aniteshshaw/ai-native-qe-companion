# Changelog

All notable changes to the companion are recorded here. Versions follow the pattern MAJOR.MINOR.PATCH.

## 1.0.1 (2026-10-17)

Fixes to the lab *Building Your First AI QE Assistant*, from tester feedback.

- Lab 2: the folder-rename "break it" step did not break anything, because VS Code still loads a workspace skill whose folder name differs from its `name`. It is replaced by two experiments that do break the skill: change the description (the skill stops loading by itself, but `/room-story-check` still works), and use an invalid name (the skill fails silently). The `name` row and the troubleshooting table no longer say the folder name must match.
- Lab 5: handoff buttons only appear in VS Code's Local harness. The lab now says to set **Session Target** to **Local**, explains that the buttons appear after an answer finishes, and gives a five-step check for when they don't appear.
- Lab 6: the hints were not clear. The lab now defines "guidance" and "real limit", shows one example row, says where each behavior came from, and has a separate hint for each question.
- Overview: every lab now runs in the Local harness. The verified date records a documentation check; a full dry run is still to come.

## 1.0.0 (2026-09-24)

First public release, matching the First Edition of the book.

- Twelve templates
- AgentOps telemetry example: event schema, error categories, metric dictionary, synthetic fixtures, test scenarios
- Hands-on lab *Building Your First AI QE Assistant*: seven labs, practice app, finished files, facilitator guide

Known limitation: the lab's verified date and tool versions are TBD. See the top of the lab README.
