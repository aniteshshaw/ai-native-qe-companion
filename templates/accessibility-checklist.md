# Accessibility checklist: from "Accessibility and Inclusive AI Quality"

An automated pass is a floor, not a verdict. Most of accessibility lives above it. AI can explain, cluster, and draft; a human, using real assistive technology, must judge whether the experience works.

## The testing layers (do all, not one)

- [ ] Static checks (automated): AI can explain and cluster the findings
- [ ] Browser automation
- [ ] Keyboard-only paths
- [ ] Assistive-technology review (a person with a real screen reader or other tool)
- [ ] Visual inspection
- [ ] Human usability review

## AI-specific cases

- [ ] Generated content is actually available to assistive technology
- [ ] Streaming updates are announced usefully, not as a flood of fragments
- [ ] Focus stays predictable after an AI response or a tool action
- [ ] Users can review, edit, reject, and undo generated content
- [ ] Confidence or uncertainty is not signaled by color alone
- [ ] Timeouts account for people who need more time
- [ ] No inaccessible verification (such as a visual-only CAPTCHA) as a safety control
- [ ] The system never infers disability or exposes a person's accessibility preferences

## Where AI must not be the final authority

Whether alt text conveys the right purpose; whether focus order is understandable; whether keyboard interaction is practical; whether an announcement is useful; whether it works with real assistive technology. Let AI draft; let a person judge purpose. Alt text that says "image of a chart" passes the scan and fails the user.

## Defect report fields

Standard or requirement it violates - user impact in functional terms - reproduction steps - actual and expected behavior - environment and assistive technology used - evidence.

## Measure two numbers, separately

- [ ] Automated pass rate (activity: the floor is sound)
- [ ] Usability with assistive technology (outcome: it actually works). Never let the first masquerade as the second.
