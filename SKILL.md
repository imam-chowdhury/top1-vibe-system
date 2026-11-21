---
name: top1-vibe-system
description: Use for building a new app, redesigning an existing product, or implementing a user-facing feature or fix. Also use when explicitly invoked as top1-vibe-system. Guides product decisions, visual design, implementation, and evidence-based QA.
---

# Top 1% Vibe System

When a user mentions this repo or skill alongside an app request, select the mode below and carry out the work in the target project. If the user requests a redesign, infer the product from the target repository. If there is no identifiable product, idea, or target, ask for that one missing input. Use the user's requirements, project conventions, and available tools. Resolve the linked guides relative to this skill. When working from a GitHub URL, open the linked files in that repository.

## Default for every UI request

Treat a single invocation as a request to apply the complete relevant workflow. Select the build, redesign or feature mode yourself. For UI work, use the bundled [design rules](DESIGN_RULES.md) during implementation and [QA checklist](QA_CHECKLIST.md) on the rendered result. Own visual direction, interaction design, interface copy, responsive behavior, accessibility and task verification within the requested scope. The user only needs to supply the product goal or change. Choose any useful specialists yourself and use the bundled guidance when none are available.

## Ask when the answer changes the work

Use the brief, existing project and earlier answers first. For routine, reversible choices, pick a sensible default and proceed. When a missing preference would materially change the result, ask one short question in the user's language. Offer a recommended option and a brief reason when helpful. Continue independent work while awaiting a necessary decision.

## Choose guidance for this project

When invoked by repository URL, use the current default branch unless the user specified a revision. Read this entry point and its relevant guides from the same commit when possible. If remote access is unavailable, use the available local copy and disclose that its freshness was unverified.

Identify the user journey, platform, installed versions, and highest-impact failure first. Use an available specialist skill only when it covers a concrete gap in this task. Treat third-party suggestions as candidates. Check compatibility with the project's constraints and evaluate the suggestion through an observable acceptance check. A referenced skill grants no permission to install software, share data, or change unrelated projects.

For decisions that depend on changing APIs or standards, consult current primary guidance applicable to the project's version. For example, use [W3C accessibility guidance](https://www.w3.org/WAI/standards-guidelines/wcag/) for keyboard and focus behavior, [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/) for relevant application security requirements, and [Web Vitals](https://web.dev/articles/vitals) for web loading, responsiveness, and visual stability. Use platform documentation for native apps. When sources disagree, choose the option that meets user requirements and demonstrates the better outcome in the target environment. Record consequential choices and their evidence in the project PRD or delivery note.

### Find and apply specialist methods

For a consequential design or engineering choice, name the decision before searching. Inspect the host's available skills and MCP capabilities. If the local catalog leaves a gap or plausible approaches differ, look up maintained upstream sources for that specific problem when browsing is available. The following are starting points. Extend the search to the actual platform and domain.

| Decision | Where to look | How to judge the result |
| --- | --- | --- |
| Visual direction and hierarchy | [Anthropic frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design) and the product's existing design language | Render the most important screen with realistic content at phone and desktop sizes. Check whether the primary task is discoverable. |
| React rendering or data-loading performance | [Vercel's skill directory](https://vercel.com/docs/agent-resources/skills) and the framework's versioned docs | Reproduce the slow journey and compare the same trace before and after the change. |
| Confidence in a refactor | [ECC](https://github.com/affaan-m/ECC), especially its verification-loop skill, and the project's test commands | Run the applicable build, type, lint and regression checks, inspect the diff, and replay the original journey. |
| Change spans unfamiliar modules | Query an available [Graphify](https://github.com/Graphify-Labs/graphify) graph for callers and dependencies. For small changes, follow imports with repository search. | Check graph freshness and confirm consequential or inferred edges in current source. |
| Implementation is growing faster than the requirement | Apply the simplicity approach from [Ponytail](https://github.com/dietrichgebert/ponytail). Try an existing project primitive or platform API before adding an abstraction. | Verify the simpler implementation against the same accessibility, failure, and data-integrity cases. |
| Build or test logs crowd out useful context | Use the host's configured [RTK](https://github.com/rtk-ai/rtk) command-output filtering. | Keep exit status and the actionable failure. Recover original output if the summary is ambiguous. |
| Large tool payloads or repeated context drive LLM costs | Evaluate [Headroom](https://github.com/headroomlabs-ai/headroom) on representative, non-sensitive inputs within the authorized provider setup. | Compare billed input, latency and answer correctness against the same uncompressed workload, including a rare but essential detail. |
| User flow looks right but behavior is uncertain | Exercise it with existing [Playwright](https://github.com/microsoft/playwright) tests or an available browser tool. | Verify a user-visible result and recovery path at relevant viewport sizes. |

Combine specialists around one acceptance check. For example, when rescheduling loses a booking, trace callers with Graphify if the path is unclear, apply Ponytail's simplicity principle to the fix, and replay rescheduling plus a failed save in the browser. RTK can shorten the test output. Trial Headroom only if measured context cost remains significant. Change one compression layer at a time so lost evidence and incremental savings can be attributed. Keep a working route through source search, ordinary commands and the project's tests when optional integrations are absent.

Read the candidate method itself before adopting it. Compare the strongest applicable approach with the project's current approach on user benefit, compatibility, implementation cost and measurable outcome. If both remain plausible, try the cheapest representative prototype or measurement that distinguishes them. Stop searching when the decision has enough evidence to act.

Choose a connected MCP tool for the evidence or action it can actually provide. For example, use an available browser inspector to exercise a dialog with the keyboard and observe focus restoration. If unavailable, use an existing browser test or mark that interaction unverified. In the PRD or handoff, give a short decision note for material choices: source consulted, technique used, alternative considered, and observed result or planned check. Claim tool use only after executing it.

### Reuse open-source implementations

Before implementing a substantial, widely solved capability, inspect the project's existing dependencies, then search GitHub for maintained implementations when network access is available. Search by function and platform using public terms. Keep private source, customer data and credentials out of queries. Conserve context by reading licenses, manifests, relevant source paths and focused tests before loading larger files.

Compare the most promising candidate with the existing stack or a small local implementation. Consider API fit, accessibility, upstream maintenance, dependency footprint, published security advisories and the cost of future updates. Inspect install scripts and requested permissions before integration. Choose the smallest maintained package or reusable component that passes a representative test in the target app. Record the upstream URL and exact version or commit. If a candidate fails, fall back to the working alternative.

Verify license coverage at the chosen revision, including separate terms for fonts, images, datasets and bundled components. Prefer compatible permissive licensing such as MIT when it fits the project. Preserve the upstream copyright and license text with redistributed copies or substantial portions of MIT software. If rights for an asset are unclear, select a cleared alternative. [MIT license terms](https://opensource.org/license/mit)

Use the engineering time saved to improve one product-specific interaction. Identify a moment where the user waits, repeats work or makes a costly mistake. Prototype an improvement with realistic content and compare completion steps, elapsed time or errors with the baseline. Preserve the design that improves the user's outcome.

For apps that call paid AI services, keep provider secrets server-side, restrict access per user, bound input and output sizes, and cap retries and usage. Test the quota-exhausted path and measure token usage and latency on a representative request before making cost claims.

## Challenge a feature when it works against the goal

Apply this in every mode before committing to a consequential choice and again if implementation reveals new evidence. Infer the intended user outcome from the brief and the current journey. If the request fits, proceed. Surface a concern when you can name a meaningful consequence, such as adding a mandatory step to a time-sensitive task, excluding keyboard users, or increasing cost beyond the stated budget.

Tell the user which goal is affected, the evidence or assumption behind the concern, and one practical alternative that achieves their intent. When evidence is thin, suggest the smallest comparison that could settle the question. Avoid presenting predicted user behavior as an observed result.

For advice-only requests, return the recommendation before editing. For delegated implementation choices, take a reversible option within scope and disclose it. If the alternative would remove an explicit requirement or change product policy, ask which direction to take before changing that part. Continue independent work. Respect an informed choice within applicable constraints.

## Own the PRD for builds and redesigns

Write the PRD yourself before implementation. Read the brief, existing specs, project instructions, manifests, and relevant screens or routes. Use [the PRD template](PRD.md) to create or update the target project's PRD.md, preserving prior requirements and user decisions. Keep the bundled template reusable. When the user delegates a choice, decide it, record why, and proceed. Ask only when a missing decision materially changes the intended outcome and available evidence cannot resolve it.

Choose a product-specific visual direction, platform, stack, and up to three priorities. Favor a complete primary journey over disconnected showcase features. Consider one alternative that removes a step, prevents a common error, or improves a difficult decision. Adopt it when the benefit justifies its cost. Label assumptions and distinguish observed behavior from proposed improvements.

## A. Build a new app

1. Complete the PRD above. Choose a working name if none was supplied. Ground each feature in a user task and define a testable result.
2. Read [the design rules](DESIGN_RULES.md). Build the shell with navigation, tokens, and one representative view using realistic sample content. Show the rendered shell before connecting business logic. Continue after the preview unless the user requested an approval checkpoint.
3. Implement the primary journey end to end first. Connect the actual data source where required and exercise validation, persistence, and recovery. Add the remaining agreed features one at a time. Verify library behavior against the installed version and its official docs when uncertain.
4. Run the applicable [QA checks](QA_CHECKLIST.md). Fix the highest-impact findings and repeat the affected checks.

## B. Redesign an existing app

Run the current app where possible. Record the main journey, its result, and desktop and mobile views before editing. Audit them against [the design rules](DESIGN_RULES.md). Rank up to five observed problems by their effect on the user's task. Use that baseline to write the redesign PRD before changing the app. Keep the product name and existing stack by default. Choose up to three improvements supported by the audit and define a before/after check for each. Introduce a dependency or interaction such as command search only for an identified need. Refactor the presentation in focused changes, preserving routes, permissions, data contracts, and working interactions. Replay the same journey and compare the same views using [the QA checklist](QA_CHECKLIST.md).

## C. Add a feature or fix a bug

Identify the affected journey and define the expected result. For a bug, capture the failing behavior when feasible. Trace its callers and data dependencies, make the smallest complete change, then verify through the normal entry point. Use [the design rules](DESIGN_RULES.md) for UI changes and select [QA checks](QA_CHECKLIST.md) for the actual impact. Add a regression test when existing coverage would miss the failure.

## Delivery

State what the user can now do, which checks ran and their results, and any remaining limitation. Support visual conclusions with rendered observations and performance claims with measurements. When a service, device, or credential is unavailable, identify the unverified path and report what you could exercise locally.
