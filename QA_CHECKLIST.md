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

## Engineering checks

Select checks by the flows and data the change touches. For a new app, review the full list for applicability.

- [ ] Run the project's relevant build, type, lint, and test commands. Open the affected route and inspect runtime errors and failed requests.
- [ ] For UI changes, sample 390px, 768px, and 1440px widths. Complete the primary journey using only the keyboard. Check accessible names, focus after a dialog closes, and readability at 200% zoom.
- [ ] For writes, verify the saved result after reload. Exercise a failed request and retry. Check duplicate submission where the action can create a second record or charge.
- [ ] For protected data, verify server-side permissions with appropriate test accounts, including denial for another user's private record. Check server-side input validation and keep sensitive values out of client bundles, logs, and error responses.
- [ ] For performance-sensitive changes, measure the affected journey with representative data. Record the device or throttling setting and the observed bottleneck. Recheck under the same conditions after a fix.
- [ ] For public pages intended for discovery, check page titles, meaningful headings, links, and indexability. For deployment changes, verify configuration and the production build in an authorized preview environment.
- [ ] Record the actual command, viewport, or scenario and result. Distinguish observed passes, failures, and checks that could not run.

## Release and operations

Apply these when the work will be deployed or handed to someone else to run.

- [ ] From a clean clone, follow the documented setup and run the production build. List the required environment variables in an example file that contains no values.
- [ ] One command or CI job runs the build, type, lint and test checks. Record whether it passed.
- [ ] Run the ecosystem's dependency audit, such as `npm audit --omit=dev`. Resolve high and critical advisories in shipped code or record why each one is not exploitable.
- [ ] Unhandled production errors reach a log or error tracker that leaves out sensitive values. Trigger one test error in preview to confirm it.
- [ ] Know how to roll back the release. For a schema or data migration, test the rollback or take a backup in preview before production.

## Decide whether the main journey is ready

- [ ] Run the primary acceptance case through the normal user entry point against a representative environment. For persisted changes, check the result independently in a fresh session. Identify any mocked boundary.
- [ ] For a multi-step write, interrupt the operation between steps using a test fixture. Inspect durable state after reopening. For example, a failed reschedule must preserve the original booking, and a successful retry must leave exactly one booking at the requested time.
- [ ] If an essential acceptance case fails, fix it and replay it. If it cannot be exercised, report the affected journey as unverified and identify the missing evidence. Reserve a readiness claim for the scope and environment actually verified.

- [ ] For a new visual direction, compare the rendered alternatives with the same brief and record the user task that determined the choice. Check a second screen for consistent tokens and component behavior.
- [ ] For generative art, canvas or scroll animation, test the static fallback, reduced motion, keyboard navigation and text readability. Record a performance observation on the target device or identify the untested device.
