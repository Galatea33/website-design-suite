---
name: website-design-suite-part-2-recreation
description: Reconstruct websites with measurable visual and behavioral fidelity from authorized screenshots, live URLs, Figma files, PDFs, videos, existing code, detailed prompts, or real-time 3D experiences. Use when the defining goal is pixel-faithful recreation, reference-to-code translation, responsive or motion matching, or correction of measurable differences. When coordinated by Website Design Suite Part 1, accept its Design Contract without restarting discovery, run only when an authoritative reconstruction target exists, and hand the completed draft to Part 3 for review.
---

# Website Design Suite - Part 2: Recreation

Translate authorized references into a faithful, maintainable implementation. Treat fidelity as an evidence problem, not a license to invent missing details or generic styling.

## Automatic suite behavior

When Part 1 invokes this skill or multiple suite parts are selected together:

- Accept the existing Design Contract, answers, finish level, and repository context as the handoff. Do not repeat Part 1's intake.
- Run only if an authorized reference is a reconstruction target. If references are merely inspiration, return control to Part 1 without forcing a recreation workflow.
- Ask only for a missing fact that blocks measurable fidelity and was not already resolved.
- Complete the Fidelity Contract and requested draft, then return the reference authority, assumptions, verification evidence, and draft location to the suite coordinator.
- If Part 3 is active, let it review the completed draft; do not begin an overlapping critique beforehand.

When invoked alone, operate as a standalone recreation workflow as described below.

## Suite routing

- Use this part when the reference is authoritative and matching it is the main goal.
- Use `$website-design-suite-part-1-architect` when references are inspiration for a new direction rather than a target to reproduce.
- Use `$website-design-suite-part-3-ux-critic` after a draft when the user wants a separate quality review. Tell Part 3 whether it should judge fidelity, usability, or both.

Reproduce only material the user owns, is authorized to reproduce, or has supplied for that purpose. Open source is not synonymous with reusable: inspect the repository license and the license or provenance of art, fonts, models, textures, audio, and other assets before copying. When a third-party site is merely inspiration or its repository grants no reuse rights, preserve high-level mechanisms and create a meaningfully original result without copying source, artwork, scene design, or distinctive prompt language.

## 1. Establish the reference contract

Inspect all supplied sources before coding:

- Live page and reachable states.
- Screenshots and their viewport sizes.
- Figma frames, component variants, and tokens.
- PDFs, videos, or motion captures.
- Written recreation prompts and exact asset lists.
- Existing repository, framework, routes, styles, assets, and checks.

Classify every requirement:

- **Authoritative:** Explicit copy, assets, measurements, behavior, and prohibitions.
- **Observed:** Directly visible structure, type, color, spacing, motion, or states.
- **Inferred:** Necessary implementation choices not proven by evidence.
- **Unresolved:** Missing or contradictory evidence.
- **Prohibited:** Substitutions or design drift the user explicitly rejects.

When sources conflict, apply this order unless the user specifies another: explicit current instruction, approved design source, current target screenshots, live reference, historical prompt, inference. Record the conflict rather than silently combining versions.

Ask no more than three concise questions, and only when the answers materially change fidelity: authorization/acceptable deviation, target viewports and states, or missing required assets/behavior. Do not re-ask details already shown by the references.

## 2. Inventory the design before implementation

Create a compact Fidelity Contract containing:

- Page anatomy and component map.
- Layout grid, bounds, alignment, spacing rhythm, and z-layer order.
- Typography families, roles, weights, line heights, tracking, and exact line breaks.
- Palette, opacity, borders, radii, shadows, blur, masks, and material rules.
- Copy, links, logos, images, video, icons, and asset provenance.
- Fixed, sticky, overflow, scroll, and viewport behavior.
- Motion grammar, durations, easings, sequencing, and interaction states.
- Responsive transformations rather than desktop shrinking alone.
- Accessibility and performance constraints.
- Acceptance viewports, interactions, and known unknowns.

For a persistent real-time 3D reference, also inventory world topology, chapter and camera endpoints, object continuity, geometry/material/light/fog/post-processing rules, hotspots and input paths, asset provenance, loading sequence, quality tiers, reduced-motion composition, fallback, and measurable frame/load budgets. Read the shared [immersive scroll-world reference](../website-design-suite-part-1-architect/references/immersive-scroll-worlds.md) before specifying or implementing that system.

Read [references/fidelity-workflow.md](references/fidelity-workflow.md) for source-specific inspection and comparison guidance. The shared suite pattern library lives in Part 1 at `../website-design-suite-part-1-architect/references/pattern-library.md`; consult it only to name or implement an observed mechanism, not to add one.

## 3. Implement without fidelity drift

Preserve the repository's package manager, routing, build configuration, and established components unless the reference requires a scoped change. Reuse real assets and exact copy. Do not substitute fonts, URLs, colors, effects, counts, line breaks, or content when they are authoritative.

Centralize repeated tokens and behavior when that improves consistency. Create reusable primitives for genuinely repeated mechanisms such as reveals, glass panels, badges, media layers, or shared controls; avoid abstracting single-use composition into a generic component system.

Do not add fashionable defaults such as purple gradients, cream backgrounds, excessive cards, generic dashboards, glass, video, or animation unless supported by the reference.

## 4. Handle media and motion safely

Identify the actual media mode:

- Static image or poster.
- Ambient looping video.
- Fixed background video.
- Scroll-controlled video.
- Click-to-play or product demonstration.
- Pointer/touch reveal or layered mask effect.
- Multi-section or multi-card video system.
- Animated graphics or 3D.

Distinguish an isolated 3D accent from a persistent scroll world. Use one real-time world only when spatial continuity and interaction are part of the authoritative behavior; otherwise prefer the observed video, image-sequence, or DOM-first mechanism. Keep native scrolling authoritative, use a separate damped visual state if needed, and preserve deterministic anchor, reload, reverse-scroll, and resize behavior.

For video, define autoplay/mute/loop behavior, poster, focal crop by breakpoint, load strategy, mobile policy, media failure, visibility lifecycle, total media budget, and reduced-motion fallback. For canvas, mask, pointer-reveal, or scroll-scrub systems, additionally handle CORS, extraction failure, memory limits, input modality, device constraints, visibility changes, duplicate initialization, cleanup, DPR, and a simpler static or seek fallback.

Do not claim a scroll-scrub or canvas strategy works until it is tested with the actual media origin. Do not let decorative motion prevent content access.

## 5. Add invisible quality safeguards

Maintain fidelity while supplying safeguards that should have been present in the reference:

- Semantic HTML, accessible names, keyboard behavior, visible focus, and logical order.
- Escape/backdrop dismissal, focus management, and scroll restoration for overlays.
- Reduced motion and alternate media behavior.
- Sufficient contrast over dynamic media, without visibly changing the reference unless necessary.
- Asset error handling, stable layout, and cleanup of media and animation resources.

If accessibility or resilience requires a visible deviation, explain it and keep the change as small as possible.

Use UI UX Pro Max only to research general design or accessibility guidance when the reference leaves a genuine gap. Do not let its generic style recommendations overwrite observed evidence or become a substitute for inspecting the real page and its states.

## 6. Compare and refine

Validation is part of the recreation, not an optional polish pass:

1. Run repository checks such as typecheck, lint, and production build.
2. Capture the target viewport sizes and important open/closed or hover/focus states.
3. Compare hierarchy, element bounds, wrapping, spacing, crop, z-order, opacity, blur, borders, and motion timing.
4. Use overlay or image-difference evidence when available; do not optimize only one viewport.
5. Inspect console errors, overflow, keyboard behavior, reduced motion, and media fallback.
6. Correct measurable differences and repeat the relevant checks.

For real-time scroll worlds, compare representative chapter endpoints and the transitions between them on desktop, tablet, and mobile. Exercise slow, fast, reverse, scrollbar-drag, anchor-jump, reload-at-depth, resize, orientation, touch, keyboard, reduced-motion, asset-failure, and WebGL-context-loss paths. Measure frame time, draw calls, triangles, transfer, memory, and loading behavior on representative hardware; screenshots alone cannot establish behavioral fidelity.

Say "pixel-faithful" only when the target and implementation were compared at defined viewport sizes. Otherwise say the implementation is faithful to the written or available evidence.

## 7. Report the handoff

Return:

1. Reference sources and authority order.
2. Fidelity Contract summary.
3. Files changed and user-visible result.
4. Comparison viewports/states and verification evidence.
5. Intentional deviations, inferences, and unresolved assets.
6. Accessibility/performance safeguards.
7. Optional Part 3 review target.

## Examples

- `$website-design-suite-part-2-recreation Recreate this authorized landing page from the desktop and mobile screenshots and verify both viewports.`
- `$website-design-suite-part-2-recreation Translate this Figma hero and motion capture into the existing React repository without changing its copy or assets.`
- `$website-design-suite-part-2-recreation Audit my current implementation against this detailed recreation brief and correct measurable differences.`

