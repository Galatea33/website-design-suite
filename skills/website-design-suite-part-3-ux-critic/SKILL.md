---
name: website-design-suite-part-3-ux-critic
description: Audit website concepts, implementations, screenshots, flows, Design Contracts, or immersive real-time 3D experiences and produce evidence-backed, prioritized improvement guidance. Use for website critique, conversion, accessibility, responsive behavior, visual hierarchy, motion, performance, generic-AI-pattern checks, or the automatic post-draft quality gate coordinated by Website Design Suite Part 1. In suite mode, wait for the draft, reuse the existing Design/Fidelity Contract without restarting discovery, and return prioritized findings to the coordinator. Remain read-only unless implementation is explicitly authorized.
---

# Website Design Suite - Part 3: UX Critic

Review a website like a senior UX and design director: diagnose the experience, show evidence, rank impact, and recommend the smallest coherent improvements. Do not redesign by personal taste.

## Automatic suite behavior

When Part 1 invokes this skill or multiple suite parts are selected together:

- Wait until the Design Contract and first draft exist. Do not interrupt Part 1's intake or critique an unfinished direction.
- Reuse the established goal, audience, primary action, constraints, finish level, viewports, and known compromises. Do not repeat discovery questions.
- Review the finished Part 1 draft or Part 2 recreation as the suite's final quality gate.
- Return Preserve, Fix now, Next pass, and Later findings to Part 1 so the user receives one coherent outcome.
- Apply only safe, scoped corrections when the user already authorized implementation. Keep larger redesign choices as recommendations requiring user direction.

When invoked alone, perform a standalone, read-only critique unless the user explicitly requests implementation.

## Suite routing

- Use this part standalone for an existing site, concept, screenshot set, or codebase.
- After `$website-design-suite-part-1-architect`, use its Design Contract to test whether the draft fulfills the intended goal.
- After `$website-design-suite-part-2-recreation`, evaluate fidelity and UX as separate lenses. Do not penalize a faithful implementation for an inherited reference choice unless the user wants modernization.
- Hand revised direction back to Part 1; hand fidelity corrections back to Part 2.

This skill is read-only by default. Inspect and recommend. Implement fixes only when the user explicitly includes implementation in scope.

## 1. Establish the review lens

Inspect the available website, screenshots, code, analytics, reference material, and Design Contract. Determine:

- User and business goal.
- Primary audience and task.
- Primary conversion or success action.
- Review scope and target devices/states.
- Whether the governing standard is original intent, reference fidelity, current best practice, or a combination.

Ask at most two concise questions when the purpose or review lens cannot be inferred safely. Otherwise proceed.

Do not infer missing analytics, user research, backend capabilities, or business results. Label hypotheses as hypotheses.

## 2. Inspect the real experience

Review representative desktop and narrow viewports plus important interactive states. Follow the primary path rather than judging only the hero screenshot. Inspect:

- Value proposition, content clarity, trust, and CTA hierarchy.
- Information architecture, navigation, orientation, and task flow.
- Visual hierarchy, composition, typography, spacing, color, and brand coherence.
- Responsive transformations, touch targets, wrapping, overflow, and content priority.
- Interaction states, forms, menus, drawers, feedback, empty/loading/error states, and recovery.
- Accessibility: semantics, headings, labels, keyboard, focus, contrast, reduced motion, and screen-reader behavior.
- Motion: purpose, timing, interruption, readability, vestibular risk, input modality, and whether an interactive reveal is discoverable without a mouse.
- Performance: loading path, layout stability, input responsiveness, fonts, images, video, canvas, masks, multi-video lifecycle, and cleanup.
- Originality: whether the result expresses the product or falls into unrelated template and generic-AI patterns.

When the experience uses a persistent real-time 3D scroll world, read the shared [immersive scroll-world reference](../website-design-suite-part-1-architect/references/immersive-scroll-worlds.md) and inspect the running experience, not screenshots alone. Review:

- Whether real-time 3D serves the narrative better than video, an image sequence, or DOM-first storytelling.
- Chapter clarity, spatial continuity, authored desktop/mobile camera endpoints, deterministic reverse scroll, anchors, reload-at-depth, resize, and orientation changes.
- Semantic DOM reading order, focus, keyboard and touch paths, and accessible equivalents for essential canvas hotspots.
- First authored frame, loading/progress state, next-chapter prefetch, poster fallback, reduced-motion composition, data-saving behavior, and asset/WebGL failure recovery.
- Measured frame time, draw calls, triangles, transfer, memory, quality-governor behavior, hidden-tab pause, context loss, and complete teardown.
- Whether particles or pointer trails support atmosphere without carrying instructions or excluding coarse-pointer, keyboard, or reduced-motion users.

Read [references/critique-rubric.md](references/critique-rubric.md) for evidence standards, severity, and domain prompts. Use the shared pattern library in Part 1 only to understand intended mechanisms; do not score a design by how many patterns it uses.

UI UX Pro Max may supply additional general heuristics, but treat its results as advisory evidence. Product goals, observed behavior, the Design/Fidelity Contract, measured performance, and accessibility testing take precedence over a database-selected style or pattern.

## 3. Diagnose before prescribing

For each actionable finding, include:

```text
SEVERITY / CONFIDENCE
LOCATION OR STATE
EVIDENCE
USER OR BUSINESS IMPACT
LIKELY CAUSE
RECOMMENDATION
ACCEPTANCE CHECK
```

Use severity consistently:

- **P0 Blocker:** Prevents completion, access, or safe use for a meaningful group.
- **P1 High:** Seriously harms comprehension, trust, conversion, accessibility, or a primary task.
- **P2 Medium:** Noticeable friction or inconsistency with a credible impact.
- **P3 Low:** Polish opportunity with limited task impact.

Use confidence as High, Medium, or Low. Prefer a short list of consequential findings over a long inventory of taste-based remarks. State positive patterns worth preserving so fixes do not erase what works.

## 4. Apply the right constraints

For original designs, compare the result with the Design Contract and product goal. For recreations, split the report:

1. **Fidelity findings:** Measurable differences from the authorized reference.
2. **UX/accessibility findings:** Issues in the reference or implementation that may justify an intentional deviation.

For each visible recommendation, say whether it preserves, adapts, or departs from the governing direction.

Do not:

- Recommend trends without a user or business rationale.
- Replace a distinctive art direction with a generic SaaS layout.
- Treat every section as a card or every improvement as "add more content."
- Invent evidence, analytics, capabilities, or user needs.
- Claim WCAG conformance or performance success without testing.
- Expand a focused review into an unauthorized rebuild.

## 5. Prioritize a coherent improvement plan

Group recommendations into:

- **Preserve:** Strong choices that define the experience.
- **Fix now:** P0/P1 issues and low-effort, high-impact corrections.
- **Next pass:** P2 improvements that should be designed together.
- **Later/optional:** P3 polish or experiments.

Identify the smallest safe improvement slice, affected screens/components, dependencies, risks, and validation steps. When several findings share a root cause, recommend one systemic fix rather than repeated local patches.

## 6. Return the critique

Use this concise structure:

1. **Executive diagnosis:** The most important outcome in two to four sentences.
2. **What works:** Decisions to preserve.
3. **Prioritized findings:** Evidence-backed P0-P3 items.
4. **Recommended sequence:** Fix now, next pass, later.
5. **Validation plan:** Viewports, tasks, accessibility, performance, or fidelity checks.
6. **Suite handoff:** Updated constraints for Part 1 or correction list for Part 2.

For immersive 3D reviews, include representative chapter endpoints and transitions in the evidence set and separate narrative/art-direction findings from renderer/performance defects. Do not recommend removing a distinctive world solely because it is unconventional; recommend simplification when measured cost, access, or comprehension does not justify it.

For code reviews, attach findings to exact files and tight line ranges when the interface supports inline comments. Report no issue when evidence is insufficient; do not manufacture critique to fill a template.

## Examples

- `$website-design-suite-part-3-ux-critic Review this landing page for clarity, conversion, responsive behavior, accessibility, and generic template patterns.`
- `$website-design-suite-part-3-ux-critic Critique the Part 1 draft against its Design Contract and rank only the changes worth making before production.`
- `$website-design-suite-part-3-ux-critic Compare this Part 2 recreation with the reference, separating fidelity defects from improvements to the original UX.`

