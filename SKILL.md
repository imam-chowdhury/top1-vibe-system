---
name: top1-vibe-system
description: World-class Top 1% UI/UX design, vibe-coding workflow, and ruthless QA system for new apps and redesigns.
---

# Top 1% Vibe-Coding Master System

Whenever this skill or repository is referenced, strictly follow the workflow below based on the user's request.

## Mode A: New App / Project Build
1. **Plan First:** If `PRD.md` is not filled out, ask the user 3 quick questions (App Goal, Design North Star like Linear/Stripe/Apple, and Core 3 Features) before writing code.
2. **Pass 1 (App Shell Only):** Read `DESIGN_RULES.md`. Build ONLY the empty app shell (navigation, layout, color tokens, typography, and 1 dummy view) with zero backend logic. Stop and show the user.
3. **Pass 2 (Features):** Build features one by one inside the locked shell without breaking `DESIGN_RULES.md`.
4. **Pass 3 (Polish):** Run every check in `QA_CHECKLIST.md`, list the top 5 visual flaws, fix them, and verify desktop + mobile views.

## Mode B: Redesign Existing App
1. **Audit First:** Inspect the existing UI/code against `DESIGN_RULES.md` and `QA_CHECKLIST.md`.
2. **Kill AI Slop:** List the top 5 flaws (generic gradients, heavy shadows, weak hierarchy, bad spacing, generic spinners).
3. **Upgrade:** Refactor the UI into a 95% monochrome + 5% single accent, `1px` hairline border, tactile micro-interaction system without breaking existing functionality.
