# QA Checklist

- [ ] Open the app at desktop and mobile widths. Check navigation, primary actions, dialogs, clipping, overflow, and content reflow.
- [ ] Scan each view for a clear heading, reading order, and dominant action. Remove decorative elements that compete with them.
- [ ] Compare spacing, alignment, typography, and component variants across views. Check realistic long labels and dense data.
- [ ] Inspect accent use, border weights, shadows, gradients, and loading indicators against the design rules.
- [ ] Exercise hover, focus, pressed, and disabled states. Verify visible keyboard focus, logical tab order, accessible labels, sufficient contrast, and reduced motion.
- [ ] Exercise loading, empty, error, and success states. Verify that recovery actions work.
- [ ] Run the main user flows end to end. In a redesign, compare their behavior against the pre-change app.
- [ ] Rank the five most consequential visual flaws by user impact. If fewer are reproducible, report the ones observed. Record the affected view, viewport, and fix for each.
- [ ] Recheck the affected flows at both viewport sizes after fixing the flaws. Record any checks that could not be run.
