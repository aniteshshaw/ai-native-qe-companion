# Capability decision ladder: from Appendix E, "Choosing the Smallest Useful AI Capability"

Start at the bottom. Climb only when the job outgrows the rung. Every step up adds evaluation, security, permission, support, and failure-recovery work, and you pay that rent for as long as the capability lives.

## The ladder

1. **Use no AI** when the rules are deterministic and stable, exact reproducibility is required, a normal script or query or validator already solves it, or the consequence exceeds the control and review you can give it.
2. **Use a reusable prompt** when one person performs a bounded language task, no tools or sensitive retrieval are needed, and variation is acceptable and reviewed.
3. **Use an instruction file** when a repository or team needs consistent conventions across many authoring tasks, and the need is rules, not autonomous action.
4. **Use a skill** when a focused capability needs instructions, examples, templates, and progressive disclosure, many users repeat the workflow, and versioning and evaluation are needed.
5. **Use an agent** when the workflow genuinely requires planning, retrieval, or tools, the goal is bounded with clear stop conditions, and permissions can be minimized and monitored.
6. **Buy a product** when the workflow is common and not a differentiator, the vendor's security, accessibility, support, integration, and lifecycle meet your requirements, and configuring costs less than building and operating.
7. **Build a platform** when many capabilities share identity, policy, tools, evaluation, telemetry, and deployment, the organization can fund ownership and operations and security and support, and reuse is proven, not hypothetical.

## Eight questions before you climb

- [ ] What decision or work product is actually being improved?
- [ ] Is the task deterministic?
- [ ] What is the consequence of a wrong answer?
- [ ] What data and tools are required?
- [ ] Is human review practical?
- [ ] How will quality be evaluated?
- [ ] Who owns its operation and its retirement?
- [ ] What is the simpler non-AI alternative?

## The anti-pattern

Do not build an agent because an agent sounds advanced. Advanced is not a goal. Solved, at the lowest cost you can defend, is the goal. If you cannot say which rung a capability is on and why it is not one lower, you have found your first design question.
