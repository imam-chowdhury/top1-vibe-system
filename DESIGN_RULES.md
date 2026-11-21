# Design Rules

- Start with the user's primary task. Use placement, type scale, and weight to establish a clear reading order and one dominant action per view.
- Use a design reference to identify qualities such as density, typography, and pacing. Translate those qualities into an original interface.
- Define reusable tokens for typography, spacing, color, radii, and borders. Align elements to a shared grid and use consistent gaps to group related controls.
- Choose a palette suited to the brand, content, and lighting conditions. For a restrained workspace, try neutral surfaces with one accent. Reserve the accent for primary actions and selected states. Communicate status through labels or icons as well as color.
- Use 1px hairlines for separation. Avoid generic gradients, heavy shadows, nested cards, and decorative badges that compete with the content.
- Give controls visible hover, focus, pressed, and disabled states. Use brief feedback for clicks and respect reduced-motion preferences.
- Use content-shaped skeletons when the layout is known. For longer operations, show contextual progress and explain how the user can recover from errors.
- Design narrow layouts around the same primary task. Reflow content, keep touch targets usable, and preserve keyboard access and text contrast.

## Product-specific decisions

- Pick a representative object from the product and design around its real content. A booking screen should make availability easy to compare. An editor should give the document most of the working area.
- Match density and visual tone to the audience. Treat the monochrome palette as a starting point when the product has no established brand. Preserve meaningful colors in charts, maps, and status indicators.
- Use tabular numerals for changing counters and comparable amounts. Try the longest realistic label, a missing image, and a populated view before locking dimensions.
- Label actions with their outcome. Preserve entered values on recoverable errors and place the recovery action near the failure. Show optimistic success only where a failed change can be clearly reversed.

## Choose a direction before styling

Identify the audience, the first decision the screen must support, and the content that deserves attention. For a new visual identity or major redesign, sketch two plausible compositions with the same real content. Compare reading order, legibility, brand fit, and task completion at phone width. Carry the stronger direction into the shell. For a small fix, use the established system.

Map the journey from entry through decision to completion and recovery. Name destinations and controls in the user's vocabulary. Test a first-time visit and a returning user's shortcut. In a Bengali interface, render actual Bengali labels, numerals and multiline text to catch font fallback, clipped marks and broken wrapping.

## Art direction and motion

Choose specialist techniques by what they communicate. A campaign page may earn attention through expressive imagery. A booking form earns trust through clear availability, prices and confirmation.

| Need | Candidate | Acceptance check |
| --- | --- | --- |
| Distinct composition, typography and spacing | [Taste Skill](https://github.com/Leonxlnx/taste-skill) | Render the same brief in two directions. Check the headline, focal point and primary action with realistic copy. |
| Original abstract artwork for a brand or concept | [Anthropic Algorithmic Art](https://github.com/anthropics/skills/tree/main/skills/algorithmic-art) | Save a reproducible seed and a static frame. Check contrast over the busiest region. Give informative imagery a text equivalent. |
| Spatial relationships or a scroll-driven story | [Meng To's Three.js and GSAP skills](https://github.com/mengto/skills) | Build the static sequence first. Keep reading and navigation usable with reduced motion, keyboard input, or unavailable WebGL. Measure on the target device before retaining the effect. |
| Reuse a validated brand direction across screens | [Anthropic Skill Creator](https://github.com/anthropics/skills/tree/main/skills/skill-creator) when a separate reusable skill is requested | Capture tokens, asset choices, voice and component states in the target project's existing design documentation. Apply them to a second screen with different content. |

Keep semantic names for surface, text, action, focus, success and error roles. Define how each component behaves across pointer, touch, keyboard, narrow widths and supported themes. For charts, label units and comparison periods and provide a readable alternative to color encoding. For forms, keep labels visible and explain recovery beside the affected input.

## Compare the rendered result

Use the same content and viewport for before/after captures. Ask a representative user to find the primary action and finish a realistic task without hints when available. Record observed hesitation or errors. Label a designer walkthrough as a walkthrough. Recheck changes in the running app, including static fallback, focus order, text zoom and one dense or long-content screen.
