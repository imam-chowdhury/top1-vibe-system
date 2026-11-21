# Specialist methods

Read the section that matches the decision in front of you. [SKILL.md](SKILL.md) holds the core workflow.

## Find and apply specialist methods

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

## Reuse open-source implementations

Before implementing a substantial, widely solved capability, inspect the project's existing dependencies, then search GitHub for maintained implementations when network access is available. Search by function and platform using public terms. Keep private source, customer data and credentials out of queries. Conserve context by reading licenses, manifests, relevant source paths and focused tests before loading larger files.

Compare the most promising candidate with the existing stack or a small local implementation. Consider API fit, accessibility, upstream maintenance, dependency footprint, published security advisories and the cost of future updates. Inspect install scripts and requested permissions before integration. Choose the smallest maintained package or reusable component that passes a representative test in the target app. Record the upstream URL and exact version or commit. If a candidate fails, fall back to the working alternative.

Verify license coverage at the chosen revision, including separate terms for fonts, images, datasets and bundled components. Prefer compatible permissive licensing such as MIT when it fits the project. Preserve the upstream copyright and license text with redistributed copies or substantial portions of MIT software. If rights for an asset are unclear, select a cleared alternative. [MIT license terms](https://opensource.org/license/mit)

Use the engineering time saved to improve one product-specific interaction. Identify a moment where the user waits, repeats work or makes a costly mistake. Prototype an improvement with realistic content and compare completion steps, elapsed time or errors with the baseline. Preserve the design that improves the user's outcome.

For apps that call paid AI services, keep provider secrets server-side, restrict access per user, bound input and output sizes, and cap retries and usage. Test the quota-exhausted path and measure token usage and latency on a representative request before making cost claims.

## Select a current AI API for the workload

When adding or upgrading an AI integration, define a representative task and its required output, language, modalities, latency, budget and data-handling constraints. Compare the existing integration with suitable direct APIs or a gateway using current official sources: [Gemini models](https://ai.google.dev/gemini-api/docs/models), [OpenAI models](https://platform.openai.com/docs/models), and [OpenRouter provider routing](https://openrouter.ai/docs/guides/routing/provider-selection). For a gateway, check both the model and the eligible upstream providers, including fallback privacy and feature support.

Verify the exact model ID, supported endpoint, SDK compatibility, pricing, account or regional availability, and deprecation status before implementation. Prefer a supported stable release for production. Record the decision date, source links and any unverified constraint. Keep the selected model configurable. Recheck on upgrade or retirement and compare against the working baseline before switching.

Where authorized credentials are available, test shortlisted options on the same small set of representative inputs, including a difficult example. Compare usable output, latency and cost per successful task. Choose the simplest eligible option meeting the quality target within budget. Without live access, document a provisional choice and the acceptance test still needed.
