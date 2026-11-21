---
name: top1-vibe-system
description: Use when the user references top1-vibe-system to build an app, redesign an existing product, or ship a feature or fix. Guides product decisions, visual design, implementation, and evidence-based QA.
---

# Top 1% Vibe System

When a user mentions this repo or skill alongside an app request, select the mode below and carry out the work in the target project. If the mention comes alone, ask what they want to build or improve. Use the user's requirements, project conventions, and available tools. Resolve the linked guides relative to this skill. When working from a GitHub URL, open the linked files in that repository.

## A. Build a new app

1. Read the brief and any existing project PRD. If the goal, design direction, or first three features are unclear, ask only for the missing details. Use [the PRD template](PRD.md) to capture decisions in the target project. Give each feature an observable completion condition.
2. Read [the design rules](DESIGN_RULES.md). Build the shell with navigation, tokens, and one representative view using realistic sample content. Show the rendered shell before connecting business logic. Pause for feedback unless the user asked for autonomous delivery.
3. Implement the primary journey end to end first. Connect the actual data source where required and exercise validation, persistence, and recovery. Add the remaining agreed features one at a time. Verify library behavior against the installed version and its official docs when uncertain.
4. Run the applicable [QA checks](QA_CHECKLIST.md). Fix the highest-impact findings and repeat the affected checks.

## B. Redesign an existing app

Run the current app where possible. Record the main journey, its result, and desktop and mobile views before editing. Audit them against [the design rules](DESIGN_RULES.md). Rank up to five observed problems by their effect on the user's task. Refactor the presentation in focused changes, preserving routes, permissions, data contracts, and working interactions. Replay the same journey and compare the same views using [the QA checklist](QA_CHECKLIST.md).

## C. Add a feature or fix a bug

Identify the affected journey and define the expected result. For a bug, capture the failing behavior when feasible. Trace its callers and data dependencies, make the smallest complete change, then verify through the normal entry point. Use [the design rules](DESIGN_RULES.md) for UI changes and select [QA checks](QA_CHECKLIST.md) for the actual impact. Add a regression test when existing coverage would miss the failure.

## Delivery

State what the user can now do, which checks ran and their results, and any remaining limitation. Support visual conclusions with rendered observations and performance claims with measurements. When a service, device, or credential is unavailable, identify the unverified path and report what you could exercise locally.
