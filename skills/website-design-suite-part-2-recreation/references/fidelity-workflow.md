# Fidelity Workflow

Use this reference to turn mixed source material into measurable implementation evidence.

## Source inspection

### Screenshots

- Record pixel dimensions and likely browser viewport.
- Identify crop boundaries, fixed elements, fold position, and visible states.
- Measure major bounds and spacing before fine decoration.
- Avoid inferring motion or unseen responsive behavior from one image.

### Live URL

- Inspect only authorized public or logged-in states within scope.
- Capture target viewports and relevant interactions.
- Record computed fonts, colors, bounds, assets, breakpoints, fixed/sticky behavior, and motion timing when available.
- Distinguish current live behavior from transient loading, experiments, or personalization.

### Figma

- Treat approved frames, component variants, variables, and exported assets as authoritative.
- Record frame size, constraints, auto-layout, tokens, and prototype transitions.
- Do not assume one frame defines every breakpoint.

### PDF

- Render pages before judging layout.
- Record page dimensions, image crop, type hierarchy, and repeated styles.
- Separate print behavior from intended responsive web behavior.

### Video or motion capture

- Sample start, transition, settled, interaction, and end states.
- Record duration, easing shape, delays, direction, scroll/playback coupling, and loop behavior.
- Record the subject focal region, object position, scale/translation crop, layer clipping, masks, and blend modes at each supplied viewport.
- For pointer-driven reveals, record idle, entry, movement, exit, and non-pointer states; distinguish the revealed media from its mask geometry.
- For multiple videos, record which assets are active simultaneously and whether offscreen media pauses or remains decoding.
- Do not derive exact timing from a low-frame-rate capture without labeling uncertainty.

### Written prompt

- Preserve explicit strings, URLs, measurements, classes, breakpoints, delays, and prohibitions.
- Normalize mixed instructions into Authoritative, Preferred, Fallback, Optional, and Prohibited groups.
- Treat claims such as "pixel-perfect" as acceptance goals, not evidence that comparison is possible.

## Measurement order

Correct differences in this order:

1. Page structure and viewport/scroll behavior.
2. Major bounds, grid, alignment, and z-order.
3. Typography family, scale, weight, line-height, and wrapping.
4. Media crop and focal position.
5. Spacing rhythm.
6. Color, opacity, borders, radii, blur, masks, and shadows.
7. Motion timing and interaction states.
8. Micro-alignment and decorative polish.

For custom loop fades, compare the final pre-loop frames, fade duration, reset frame, and first visible post-reset frame. Treat a fade as a behavioral requirement only when the source demonstrates it.

Do not tune shadows while the headline wraps incorrectly.

## Comparison matrix

For each target viewport/state, record:

| Area | Reference evidence | Implementation | Difference | Action |
|---|---|---|---|---|
| Structure |  |  |  |  |
| Bounds/alignment |  |  |  |  |
| Typography/wrap |  |  |  |  |
| Media crop |  |  |  |  |
| Spacing |  |  |  |  |
| Material/color |  |  |  |  |
| Motion/state |  |  |  |  |

Use overlays or image differences as diagnostic evidence. A low aggregate pixel difference can still hide an important content, focus, or interaction defect.

## Responsive inference

When a breakpoint is not shown, infer conservatively from content priority and the repository's established system. Label the result Inferred. Test:

- Narrow width and short height separately.
- Text zoom and long strings.
- Touch behavior and safe areas.
- Menu open/closed states.
- Media loading failure and reduced motion.

## Completion standard

A recreation is complete when:

- Authoritative requirements are implemented or explicitly blocked.
- Target viewports and states were compared.
- Important differences were corrected or documented.
- Build and interaction checks pass.
- Accessibility/performance safeguards are present.
- Remaining inferences and deviations are visible in the handoff.

