# Website Critique Rubric

Use this rubric to gather evidence and prioritize findings. Do not assign a numerical score unless the user requests one and the scoring method is explained.

## Evidence strength

- **High:** Directly observed in the interface, code, test, analytics, or supplied research.
- **Medium:** Supported by repeatable design or usability principles but not validated with product-specific data.
- **Low:** Plausible hypothesis requiring user research, analytics, or stakeholder confirmation.

Keep severity and evidence confidence separate.

## Review domains

### Purpose and comprehension

- Can the intended user understand what this is, for whom, and why it matters?
- Is the primary action obvious and consistent with the promise?
- Does supporting copy reduce uncertainty or merely add slogans?
- Are claims credible and supported?
- Are statistics, activity counts, ratings, security statements, and community numbers real, current, and appropriately qualified?

### Information architecture and flow

- Can users predict where links and actions lead?
- Is the primary journey complete across navigation, forms, success, and recovery states?
- Is content ordered by user need rather than internal organization?
- Are essential destinations reachable at every supported width?

### Visual hierarchy and brand

- Does the first visual emphasis match the primary goal?
- Are type, spacing, color, imagery, and material rules coherent?
- Is there a distinct product-specific idea, or a collection of unrelated trends?
- Does decorative media support or compete with content?
- Do glass, texture, blend modes, masked reveals, giant type, and video form one thesis, or merely accumulate spectacle?
- Which strong choices must be preserved during revision?

### Responsive behavior

- Does content priority survive narrow and short viewports?
- Are wrapping, ordering, touch targets, overflow, fixed elements, and safe areas intentional?
- Are essential interactions available without hover?
- Does mobile media have an appropriate cost and fallback?

### Interaction and states

- Do controls look and behave like their semantics?
- Are hover, focus, active, selected, disabled, loading, success, empty, and error states present where relevant?
- Do menus and dialogs manage focus, Escape, backdrop dismissal, and scroll restoration?
- Does every action provide timely feedback?

### Accessibility

- Semantic HTML and logical headings.
- Keyboard-complete primary paths and visible focus.
- Accessible names and instructions.
- Text and non-text contrast.
- Touch target size and spacing.
- Status not conveyed by color alone.
- Reduced-motion behavior and media alternatives.
- Sensible reading and focus order.

Treat WCAG 2.2 AA as the baseline target. Report tested evidence, not assumed compliance.

### Motion

- Does each animation communicate hierarchy, continuity, feedback, or state?
- Can content be read while motion occurs?
- Are duration, easing, and stagger coherent?
- Is there a useful reduced-motion state?
- Does scroll-linked motion preserve navigation and control?
- Can pointer-driven reveals be discovered and understood on touch, keyboard, coarse-pointer, and reduced-motion configurations?

### Performance and resilience

- Is important content available before decorative media?
- Are font, image, video, and script loading strategies appropriate?
- Are layout shift and input delay visible or measurable?
- Do video/canvas/mask systems have memory limits, error fallbacks, input fallbacks, and cleanup?
- When several videos autoplay, are offscreen assets lazy-activated or paused, and is the total decoder/network cost justified?
- Does custom loop-fade logic improve a demonstrated seam, or add flashing, blank frames, timer races, and unnecessary complexity?
- Does the page remain useful after asset or network failure?

### Fidelity lens

When reviewing a recreation:

- Compare defined target viewports and states.
- Separate measurable implementation differences from inherited reference issues.
- Mark UX improvements that intentionally depart from the reference.
- Do not optimize one viewport at the expense of another.

## Finding template

```text
[P1] Primary CTA loses contrast over the middle video frames

Location: Hero, desktop and mobile
Evidence: Contrast drops when the background changes; keyboard focus is also indistinct.
Impact: Users can miss the main action and keyboard users cannot reliably locate focus.
Cause: One translucent treatment is used over media with a wide luminance range.
Recommendation: Add a stable local contrast surface and a distinct focus ring while preserving the material language.
Acceptance: CTA label and focus indicator meet the project's contrast target across sampled frames.
Confidence: High
```

## Prioritization checks

Before recommending a change, ask:

1. Does it improve the primary user outcome?
2. Is there direct evidence or a clearly labeled hypothesis?
3. Does it preserve the strongest design idea?
4. Can one systemic change solve several findings?
5. What is the smallest safe slice?
6. How will the team know the issue is fixed?

