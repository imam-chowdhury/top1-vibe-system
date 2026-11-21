---
name: top1-vibe-system
description: Use for building a new app, redesigning an existing product, or implementing a user-facing feature or fix. Also use when explicitly invoked as top1-vibe-system. Guides product decisions, visual design, implementation, and evidence-based QA.
---

# Top 1% Vibe System

When a user mentions this repo or skill alongside an app request, select the mode below and carry out the work in the target project. If the user requests a redesign, infer the product from the target repository. If there is no identifiable product, idea, or target, ask for that one missing input. Use the user's requirements, project conventions, and available tools. Resolve the linked guides relative to this skill. When working from a GitHub URL, open the linked files in that repository.

## Default for every UI request

Treat a single invocation as a request to apply the complete relevant workflow. Select the build, redesign or feature mode yourself. For UI work, use the bundled [design rules](DESIGN_RULES.md) during implementation and [QA checklist](QA_CHECKLIST.md) on the rendered result. Own visual direction, interaction design, interface copy, responsive behavior, accessibility and task verification within the requested scope. The user only needs to supply the product goal or change. Choose any useful specialists yourself and use the bundled guidance when none are available.

## Quality bar for every delivery

A top result is one where the user's task succeeds reliably. More features do not make it better. Before handoff, each applicable aspect meets its bar or is reported as an open gap with the missing evidence.

| Aspect | Bar |
| --- | --- |
| Product | The requested journey completes with real or representative data. Trace the result to the project PRD or, for a focused fix, the requested behavior. |
| Design | One dominant action per view, realistic content, and a passed rendered critique from [the design rules](DESIGN_RULES.md) at 390px, 768px and 1440px. |
| Accessibility | Test relevant [WCAG 2.2](https://www.w3.org/TR/WCAG22/) A and AA criteria for the journey, including keyboard access, focus and accessible names. Check normal text at 4.5:1 and large text at 3:1 where applicable. Respect reduced motion. Report the criteria tested and reserve a conformance claim for a full assessment. |
| Performance | Evaluate web LCP ≤ 2.5 s, INP ≤ 200 ms and CLS ≤ 0.1 at the 75th percentile of real visits, separately for mobile and desktop. Before field data exists, report reproducible lab measurements with device and conditions, and leave field status unverified. For native apps, measure relevant startup and frame metrics. |
| Security and privacy | Authorization and validation happen on the server. Secrets stay out of client bundles, logs and errors. Shipped dependencies have no known high or critical advisories, or there is a recorded exception. |
| Data integrity | Writes survive reload, failure and retry without loss or duplicates. Schema changes are reversible or backed up first. |
| Code | Build, type, lint and test commands pass. Each fixed bug gets a regression test where coverage would miss it. No dead code or unused dependency is added. |
| Operations | Setup runs from a clean clone with documented steps. Required environment variables are listed without values. Production errors are observable and the release has a rollback path. |

### Work loop

- **Checkpoint.** Inspect existing changes and preserve the user's work. Use isolated commits where the project's workflow calls for them.
- **Review.** Before handing off a build or redesign, review the diff against the PRD and applicable checks. Use independent review when available and authorized. Otherwise review the diff directly. Fix confirmed findings and replay the affected checks.
- **Stop rule.** Work on the highest-impact remaining gap each round. Stop when the bar is met within the PRD scope, or when the remaining gaps need a user decision, device, credential or service. Report those gaps. Polishing beyond the agreed scope is not quality.

## Ask when the answer changes the work

Use the brief, existing project and earlier answers first. For routine, reversible choices, pick a sensible default and proceed. When a missing preference would materially change the result, ask one short question in the user's language. Offer a recommended option and a brief reason when helpful. Continue independent work while awaiting a necessary decision.

## Choose guidance for this project

When invoked by repository URL, use the current default branch unless the user specified a revision. Read this entry point and its relevant guides from the same commit when possible. If remote access is unavailable, use the available local copy and disclose that its freshness was unverified.

Identify the user journey, platform, installed versions, and highest-impact failure first. Use an available specialist skill only when it covers a concrete gap in this task. Treat third-party suggestions as candidates. Check compatibility with the project's constraints and evaluate the suggestion through an observable acceptance check. A referenced skill grants no permission to install software, share data, or change unrelated projects.

For decisions that depend on changing APIs or standards, consult current primary guidance applicable to the project's version. For example, use [W3C accessibility guidance](https://www.w3.org/WAI/standards-guidelines/wcag/) for keyboard and focus behavior, [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/) for relevant application security requirements, and [Web Vitals](https://web.dev/articles/vitals) for web loading, responsiveness, and visual stability. Use platform documentation for native apps. When sources disagree, choose the option that meets user requirements and demonstrates the better outcome in the target environment. Record consequential choices and their evidence in the project PRD or delivery note.

### Specialist methods

Read [the specialist methods](METHODS.md) before any of these: a consequential design or engineering choice where approaches differ, building a widely solved capability that a maintained package may cover, or adding or upgrading a paid AI integration. Claim a tool or method only after running it. Record the source, the alternative considered and the observed result in the PRD or handoff.

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

State what the user can now do, which checks ran and their results, the status of each applicable quality-bar aspect, and any remaining limitation. Support visual conclusions with rendered observations and performance claims with measurements. When a service, device, or credential is unavailable, identify the unverified path and report what you could exercise locally.
