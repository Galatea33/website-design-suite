---
name: website-design-suite-part-1-architect
description: Start and coordinate the Website Design Suite for original websites, redesigns, and first drafts, including immersive or real-time 3D concepts. Use even when the user gives only a terse request such as "let's design a website." Lead a concise adaptive intake, create the Design Contract, coordinate Part 2 automatically when authoritative references require reconstruction, and run Part 3 as the post-draft quality check. Also use when the user needs help choosing a direction, asks to be interviewed before design, has an incomplete brief, or wants a concept or prototype before production.
---

# Website Design Suite - Part 1: Architect

Turn an incomplete website idea into a coherent Design Contract and first draft. Ask only questions that materially affect the design, then move from discovery to a concrete result.

## Automatic suite orchestration

Treat this skill as the suite's default entry point. When it is explicitly invoked, begin the appropriate website-design workflow without requiring the user to explain what each part does, specify their order, or mention Parts 2 and 3.

If the prompt is as short as "Let's design a website," classify it as Guided mode and start the adaptive intake. If the finish level is unclear, include concept, functional prototype, or production implementation in that intake rather than asking a separate preliminary question.

Coordinate the suite in this order:

1. Inspect supplied context and run Part 1's intake.
2. Pause for the user's answers when questions are necessary.
3. Create the Design Contract.
4. Invoke `$website-design-suite-part-2-recreation` only when matching an authorized reference is a governing requirement. Skip it silently when no authoritative reconstruction target exists.
5. Produce the requested first draft.
6. Invoke `$website-design-suite-part-3-ux-critic` after the draft as a read-only quality gate unless the user asks to skip critique.
7. Return one coherent result, incorporating safe low-risk corrections when implementation is already authorized and separating larger proposed changes for approval.

When multiple suite parts are explicitly selected together, remain the coordinator and follow this sequence. Do not let Part 2 restart discovery or Part 3 critique before a draft exists. Do not require another prompt merely to hand work between suite parts.

## Suite routing

- Use this part for an original direction, redesign concept, or guided brief.
- Use `$website-design-suite-part-2-recreation` when matching supplied screenshots, URLs, Figma files, PDFs, videos, or detailed reference prompts is the defining requirement.
- Use `$website-design-suite-part-3-ux-critic` to evaluate an existing site or a draft from either part.
- For implementation after the direction is approved, use the narrowest appropriate frontend implementation skill available. Keep this Design Contract authoritative during the handoff.

Use UI UX Pro Max only as optional design-research support for patterns, palettes, typography, accessibility rules, or stack guidance. Its database output is advisory: do not let a generic recommendation override the product purpose, brand, authoritative references, or the Design Contract's visual thesis. When an installed specialist skill covers a required Three.js scroll world or atmospheric effect, route the implementation detail to it after the architecture is settled; never add the effect merely because the skill exists.

Do not silently blend "original design" and "exact recreation." Ask which outcome governs when that distinction changes the work.

## 1. Inspect before asking

Review the user's prompt, attachments, repository, existing brand assets, and prior decisions. Record what is already known. Do not ask for facts that can be discovered safely or that the user already supplied.

Classify the engagement:

- **Guided:** The user has an idea but few design decisions.
- **Brief:** The user supplied substantial requirements; fill only material gaps.
- **Redesign:** Preserve defined brand or product constraints while changing the experience.
- **Recreation:** Hand off to Part 2.

Also determine the requested finish level:

- **Concept:** Direction, page anatomy, visual system, and representative composition.
- **Functional prototype:** Responsive interface and important interactions with realistic content.
- **Production implementation:** Repository integration, complete states, safeguards, and verification.

## 2. Run the adaptive intake

In Guided mode, ask three to five concise questions in one batch before completing the first draft. In Brief or Redesign mode, ask zero to three questions only for consequential gaps. Use the platform's structured question UI when it is available; otherwise use short numbered questions with clear options and allow free-form answers.

Prioritize:

1. Page purpose, audience, and single primary action.
2. Scope: fixed hero, scrolling landing page, multi-page site, or application surface.
3. Brand/reference authority: must-use assets, existing identity, admired references, and taboos.
4. Visual and content direction: mood, voice, content readiness, and desired differentiation.
5. Main media and motion: typography, image, ambient video, scroll-controlled video, product demo, animation, or 3D.
6. Delivery constraints only when they affect the draft: stack, deadline, device priority, or finish level.

Offer a sensible recommended option first. Let the user accept defaults for uncertain items. Do not turn the intake into a long questionnaire.

Read [references/intake-question-bank.md](references/intake-question-bank.md) when the request needs guided discovery or conditional media questions.

### Conditional media questions

If the user chooses video or heavy motion, ask at most three follow-ups covering the decisions that change architecture:

- Behavior: ambient loop, scroll-controlled, click-to-play, product demonstration, pointer/touch reveal, multi-section media, or scene-synchronized content.
- Source: supplied file/URL, commissioned asset, generated placeholder, or poster-first draft.
- Mobile and accessibility: same media, lighter alternate, static poster, reduced-data fallback, reduced-motion behavior, and a non-pointer equivalent for hover-driven reveals.

If the user chooses a persistent real-time 3D scroll world, read [references/immersive-scroll-worlds.md](references/immersive-scroll-worlds.md) and replace generic media follow-ups with at most three architecture-changing questions:

- Story and topology: the chapter beats and whether the world is continuous geography, connected sets, or a layered reveal.
- Assets and interaction: what is supplied, what must be original or licensed, and whether the world is atmospheric or contains meaningful hotspots.
- Capability and fallback: minimum devices, initial-load and frame budget, authored mobile composition, reduced-motion state, and poster/DOM fallback.

Do not assume video, glass, gradients, cards, 3D, or a familiar SaaS aesthetic merely because they occur in the pattern library.

## 3. Build the Design Contract

After the answers, produce a compact contract before or alongside the first draft:

```text
PROJECT / MODE / FINISH LEVEL
PURPOSE / AUDIENCE / PRIMARY ACTION
SUCCESS SIGNAL
CONTENT AND VOICE
PAGE ANATOMY
VISUAL THESIS
TYPE ROLES / PALETTE / MATERIALS
MEDIA STRATEGY / MOTION GRAMMAR
RESPONSIVE BEHAVIOR
ACCESSIBILITY / PERFORMANCE
TECHNICAL CONSTRAINTS
AUTHORITATIVE INPUTS / ASSUMPTIONS / OPEN ITEMS
ACCEPTANCE VIEWPORTS AND CHECKS
```

Separate:

- **Authoritative:** Explicit user requirements and approved assets.
- **Observed:** Facts from supplied project or references.
- **Inferred:** Small decisions made to complete the direction.
- **Open:** Missing inputs that prevent a specific choice.
- **Prohibited:** User taboos and known design drift to avoid.

Make the visual thesis one clear idea, not a list of fashionable treatments. Use [references/pattern-library.md](references/pattern-library.md) to select compatible mechanisms, never to impose a house style.

For a persistent real-time 3D scroll world, append the world topology, chapter/camera ledger, asset provenance, input model, loading plan, quality tiers, reduced-motion composition, fallback, and performance evidence defined in [references/immersive-scroll-worlds.md](references/immersive-scroll-worlds.md). Require a narrative reason for choosing real-time rendering over video, an image sequence, or DOM-first storytelling.

## 4. Produce the first draft

Match the artifact to the user's request:

- For planning, provide the Design Contract plus a concise page map or wireframe.
- For a concept, establish representative desktop and mobile compositions, type hierarchy, palette, materials, and motion notes.
- For a prototype or implementation request, build the first working responsive draft in the existing repository after the intake and contract.

Use real supplied copy and assets. When content is missing, use clearly marked, contextually realistic draft content and do not invent unsupported product capabilities, testimonials, customers, metrics, or legal claims.

Preserve repository conventions and working behavior. Reuse existing components and tokens where they fit. Avoid premature abstraction, unrelated restructuring, or adding a dependency for an effect that native CSS can handle reliably.

## 5. Apply non-negotiable quality safeguards

Design for WCAG 2.2 AA as a baseline:

- Semantic structure, logical headings, keyboard access, visible focus, adequate targets, and labeled controls.
- Accessible menus, drawers, dialogs, and forms with appropriate focus and dismissal behavior.
- Contrast that remains legible over changing images or video.
- Reduced-motion behavior without removing essential information.

Plan media and motion as progressive enhancement:

- Provide posters or stable fallbacks for video and animation.
- Avoid blocking first contentful rendering on decorative media.
- Define failure, low-power, narrow-screen, and data-saving behavior for expensive effects.
- Prevent layout shift; clean up observers, animation frames, media buffers, and scroll locks.
- Keep essential copy, navigation, and actions semantic and usable outside a canvas; mirror any essential 3D hotspots with accessible DOM controls.
- Do not claim performance or accessibility compliance without checking it.

## 6. Verify and hand off

For implemented drafts, run checks proportionate to scope: build/typecheck, lint, console review, keyboard flow, responsive overflow, reduced motion, media failure, and representative viewport screenshots.

Finish with:

1. Design Contract summary.
2. Draft produced and where it lives.
3. Explicit assumptions and unresolved assets.
4. Checks completed and limitations.
5. Recommended next move: critique with Part 3, production implementation, or focused revision.

When handing to Part 3, pass the goal, audience, primary action, authoritative constraints, acceptance viewports, draft location, and known compromises. When the user requests revision, update the same Design Contract rather than starting a competing direction.

## Examples

- `$website-design-suite-part-1-architect Interview me briefly, then design the first draft of a premium landing page for a bookkeeping service.`
- `$website-design-suite-part-1-architect Turn this partial brief and brand kit into a Design Contract and responsive prototype.`
- `$website-design-suite-part-1-architect Help me choose between an ambient video hero and typography-led hero before building.`

