# Design Rules

- Start with the user's primary task. Use placement, type scale, and weight to establish a clear reading order and one dominant action per view.
- Use a design reference to identify qualities such as density, typography, and pacing. Translate those qualities into an original interface.
- Define reusable tokens for typography, spacing, color, radii, and borders. Align elements to a shared grid and use consistent gaps to group related controls.
- In redesigns, aim for 95% monochrome with 5% of one accent. Reserve the accent for primary actions and selected states. Communicate status through labels or icons as well as color.
- Use 1px hairlines for separation. Avoid generic gradients, heavy shadows, nested cards, and decorative badges that compete with the content.
- Give controls visible hover, focus, pressed, and disabled states. Use brief feedback for clicks and respect reduced-motion preferences.
- Use content-shaped skeletons when the layout is known. For longer operations, show contextual progress and explain how the user can recover from errors.
- Design narrow layouts around the same primary task. Reflow content, keep touch targets usable, and preserve keyboard access and text contrast.

## Product-specific decisions

- Pick a representative object from the product and design around its real content. A booking screen should make availability easy to compare. An editor should give the document most of the working area.
- Match density and visual tone to the audience. Treat the monochrome palette as a starting point when the product has no established brand. Preserve meaningful colors in charts, maps, and status indicators.
- Use tabular numerals for changing counters and comparable amounts. Try the longest realistic label, a missing image, and a populated view before locking dimensions.
- Label actions with their outcome. Preserve entered values on recoverable errors and place the recovery action near the failure. Show optimistic success only where a failed change can be clearly reversed.
