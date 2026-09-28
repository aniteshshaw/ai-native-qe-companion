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
