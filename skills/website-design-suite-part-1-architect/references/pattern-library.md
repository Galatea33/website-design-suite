# Website Design Suite Pattern Library

This library abstracts reusable mechanisms from a corpus of detailed website briefs. It intentionally excludes source brands, copy, URLs, and distinctive asset identities. Patterns are descriptive tools, not defaults.

## Contents

1. [Selection doctrine](#selection-doctrine)
2. [Composition patterns](#composition-patterns)
3. [Navigation patterns](#navigation-patterns)
4. [Hero patterns](#hero-patterns)
5. [Media patterns](#media-patterns)
6. [Typography patterns](#typography-patterns)
7. [Material patterns](#material-patterns)
8. [Motion grammars](#motion-grammars)
9. [Responsive transformations](#responsive-transformations)
10. [Quality safeguards](#quality-safeguards)
11. [Pattern recording template](#pattern-recording-template)

## Selection doctrine

- Start with purpose, audience, content, and primary action.
- Choose the smallest set of mechanisms that expresses one visual thesis.
- Treat user-supplied assets, brand rules, and references as higher authority than this library.
- Never infer a house style from frequency in the corpus.
- Combine patterns only when their spatial, typographic, material, and motion logic agrees.
- Prefer stable readability and task completion over spectacle.
- Record why each high-cost pattern earns its cost.

## Composition patterns

| Pattern | Choose when | Avoid when | Required checks |
|---|---|---|---|
| Locked viewport composition | One cinematic or editorial scene must read as a poster-like whole | Content cannot fit at supported heights or zoom levels | Short viewport, browser chrome, text zoom, safe-area, no hidden essential content |
| Scrolling landing page | A value proposition needs progressive explanation and proof | The content truly supports only one focused action | Section rhythm, anchor behavior, CTA continuity, scroll restoration |
| Storytelling sequence | Media or narrative changes meaning across scroll | Content order is arbitrary or motion is decorative | Reduced motion, seekability, reading order, low-power fallback |
| Split composition | Two content groups need equal or complementary weight | Mobile ordering is unclear or both sides compete | Collapse order, width balance, wrapping, touch priority |
| Sparse editorial frame | Type, negative space, and a few precise elements carry identity | The product requires dense comparison or operational tasks | Content clarity, large-type wrapping, contrast, empty-space behavior |
| Layered cinematic frame | Foreground cutouts, type, and background media need depth | Assets lack clean edges or z-order does not convey meaning | Explicit layer map, crop, pointer behavior, contrast |
| Framed media canvas | A full-height scene benefits from an intentional outer margin, rounded media frame, or page-colored cutout | The frame wastes scarce mobile space or exists only as decoration | Short-height fit, inverse-corner geometry, background continuity, safe-area behavior |
| Typography-as-scene | A few oversized words create the spatial composition rather than merely labeling it | Supporting copy, navigation, or translation cannot coexist without collisions | Exact word positions, overlap rules, reading order, zoom, narrow and short viewports |
| Multi-video anthology | Distinct sections genuinely need different moving scenes | Several ambient loops repeat the same message or overload decoding/network budgets | Per-section purpose, lifecycle, posters, lazy activation, total media budget |
| Persistent 3D scroll world | Spatial continuity itself carries a four-to-eight-chapter story | A video, image sequence, or DOM transition can communicate the same idea more reliably | World and chapter ledger, native-scroll mapping, authored mobile endpoints, semantic DOM, loading/fallback, measured frame budget |

Create a z-layer table for any composition with three or more overlapping planes.

## Navigation patterns

| Pattern | Best fit | Safeguards |
|---|---|---|
| Centered desktop links | Symmetrical marketing headers | Prevent logo/action collision; define narrow collapse |
| Split metadata navigation | Editorial and portfolio compositions | Preserve semantic navigation and readable mobile grouping |
| Full-screen mobile overlay | Small link sets that benefit from a deliberate transition | Focus trap, Escape, close control, scroll lock restoration |
| Right-side sheet | Mobile navigation with secondary actions or account controls | Backdrop dismissal, focus return, 100dvh, safe-area padding |
| Compact dropdown | Short mobile menus that should retain page context | Correct anchoring, outside click, keyboard navigation |
| Hidden secondary links | Deliberately minimal small-screen chrome | Ensure essential destinations remain reachable elsewhere |

## Hero patterns

| Pattern | Structure | Main risk |
|---|---|---|
| Centered conversion hero | Logo/nav, centered promise, supporting copy, primary action | Generic SaaS appearance without a brand-specific thesis |
| Bottom-anchored cinematic hero | Media background, lower metadata/title/actions | Low contrast and short-height collisions |
| Editorial marquee hero | Oversized moving type, layered portrait, sparse chrome | Motion distraction, cropping, inaccessible overflow |
| Product prompt hero | Clear promise plus a functional prompt/input surface | Fake functionality or ambiguous submit behavior |
| Split brand/story hero | Primary statement paired with services, proof, or navigation | Competing hierarchy and weak mobile order |
| Scroll-transition hero | Initial promise followed by media-driven second state | Expensive rendering and content dependence on motion |
| Staggered word-stage hero | Separate oversized words intentionally occupy different regions over media | Visual order and semantic reading order diverge or copy cannot localize safely |
| Interactive reveal hero | A spotlight, mask, or cursor reveals a meaningful second media layer | The effect is pointer-only, undiscoverable, or reveals no additional meaning |

Every hero needs a recognizable primary message even when decorative media fails.

## Media patterns

### Still image or poster

Use for reliable atmosphere, editorial framing, and mobile fallback. Define focal point, crop behavior, intrinsic dimensions, alt behavior, and loading priority.

### Ambient looping video

Use for mood without narrative dependence. Require muted inline playback, poster, failure fallback, legible overlays, reduced-motion behavior, and mobile/data-saving policy. Avoid audio and avoid making content timing depend on the loop.

Record a focal-position contract when the important subject is not centered: subject coordinates or region, `object-position` by breakpoint, any scale/translation, and the crop that must remain visible. Treat transforms such as vertical shifts as evidence-driven exceptions, not general tuning.

### Fixed background video

Use when media should remain behind viewport content. Test mobile browser behavior and compositor cost. Avoid fixed positioning when it causes viewport or keyboard defects.

### Scroll-controlled video

Use only when the timeline communicates progress or transformation. Define scroll mapping, smoothing, poster/video/canvas layer states, seeking fallback, memory budget, CORS behavior, visibility pause, cleanup, DPR cap, and constrained-device mode.

### Click-to-play media

Use for showreels, explainers, and sound-bearing content. Provide a real button, state transition, captions when needed, focus handling, pause/close behavior, and poster.

### Animated graphics or 3D

Use when interaction or dimensionality explains the product. Define performance budget, input model, reduced-motion/static fallback, and content independence.

For a persistent real-time world that recomposes across scroll chapters, read [immersive-scroll-worlds.md](immersive-scroll-worlds.md). Do not promote an ordinary 3D accent into a site-wide renderer without narrative and performance justification.

### Pointer or spotlight reveal

Use when revealing a second layer communicates discovery, comparison, or product behavior. Prefer a live CSS radial mask updated with CSS variables when it is sufficient; use canvas only when the mask itself must be generated. Define pointer exit, first-load state, touch/keyboard/coarse-pointer behavior, reduced motion, clipping bounds, resize/DPR handling, and animation-frame cleanup. Avoid repeatedly exporting canvas data URLs during pointer movement unless measurement proves the cost acceptable.

### Loop-seam treatment

Start with the native loop and the source asset's edit. Add a custom fade only when the seam is visibly disruptive and the fade itself is acceptable. If custom control is required, model explicit loading, playing, fading, reset, and failure states; cancel competing animation frames and test background-tab, stalled-media, autoplay-rejection, and reduced-motion behavior. A fade-to-black is not a seamless loop.

### Multi-video lifecycle

For pages with several videos, avoid decoding every loop continuously. Prioritize the first meaningful scene, use posters, activate near the viewport, pause when out of view or hidden, and define a total network/decoder budget. Keep copy and navigation useful while every video is unavailable.

## Typography patterns

- **Single-family system:** Use hierarchy, weight, scale, and spacing within one family for a calm unified voice.
- **Role-split system:** Assign display, body, label, and data roles deliberately. Do not switch fonts decoratively.
- **Display plus utility:** Pair a distinctive wordmark/headline face with a highly readable UI face.
- **Bitmap or mono accent:** Reserve for labels or selected words; verify raster-like fonts remain legible on small screens.
- **Oversized editorial type:** Define exact wrapping and safe viewport behavior; avoid hiding meaning behind media.

Always provide fallbacks, stable font loading, and a layout that survives delayed or failed webfonts.

## Material patterns

| Material | Composition rule | Failure mode |
|---|---|---|
| Flat editorial | Contrast, type, rules, and whitespace create hierarchy | Adding cards, pills, or shadows that dilute the concept |
| Frosted glass | Transparency reveals context while separating controls | Low contrast, excessive blur, every element becoming glass |
| Liquid-glass edge | Very light fill plus carefully masked highlight border | Browser inconsistency and decorative complexity |
| Opaque utility surface | Stable readable controls over busy media | Covering the visual story or becoming visually heavy |
| Masked blur region | Blur increases legibility without color darkening | Unsupported masks or unreadable fallback |
| Texture veil | Grain or atmospheric texture unifies otherwise clean layers | Fixed high-z texture lowers contrast, obscures focus, or blends controls unpredictably |
| Page-colored inverse cutout | A surface appears carved from a framed scene using matching fills and corner masks | Geometry breaks when page and frame backgrounds diverge or at breakpoint transitions |

Define materials as reusable tokens or primitives only when repeated.

## Motion grammars

- **Fade-up:** General content entrance; use a shared duration/easing and modest stagger.
- **Blur-fade-up:** Cinematic reveal; use sparingly because blur is expensive and harms readability during motion.
- **Rise-and-scale:** Foreground media entrance; keep scale subtle and preserve crop.
- **Line grow:** Editorial separators and progress accents; set transform origin explicitly.
- **Marquee:** Continuous identity or editorial motion; duplicate content correctly and pause or simplify for reduced motion.
- **Drawer/sheet transition:** Couple container motion with focus and scroll state, not only visual animation.
- **Pointer parallax:** Use restrained movement as depth feedback; disable or stabilize for coarse pointers, reduced motion, and keyboard use.
- **Micro-interaction:** Hover, active, and focus feedback should confirm affordance without moving layout.

Centralize durations, easings, and stagger logic. Reduced motion should preserve final state and information rather than merely setting animation duration to zero if that breaks initialization.

## Responsive transformations

Describe behavior, not just breakpoints:

- Desktop navigation becomes a drawer, sheet, dropdown, or intentionally simplified set.
- Multi-column metadata changes order based on reading priority.
- Bottom-anchored content becomes scrollable when short mobile heights cannot contain it.
- Oversized typography gains controlled wrapping, not arbitrary shrinking.
- Heavy video becomes lighter video or a poster based on capability and preference.
- Pointer-driven reveals become a stable disclosed state, tap-controlled state, or poster on touch and keyboard devices.
- Framed scenes may lose ornamental margins or inverse cutouts when space is scarce, while preserving the visual hierarchy.
- Hover-only disclosure gains touch and keyboard equivalents.
- Fixed pixel bounds become capped fluid bounds while preserving intentional proportions.

Validate at representative narrow, tablet, desktop, wide, and short-height viewports defined by the project.

## Quality safeguards

Apply across all patterns:

- WCAG 2.2 AA target; keyboard and visible focus.
- Semantic controls and meaningful accessible names.
- No essential information encoded by color, motion, sound, or hover alone.
- Stable layout during font and media loading.
- Poster/error/reduced-motion fallbacks for decorative media.
- A total media budget and visibility lifecycle when more than one autoplaying asset exists.
- Stable text contrast sampled across video frames, texture overlays, masks, and blend modes.
- Cleanup for observers, animation frames, media buffers, event listeners, and scroll locks.
- No unsupported claims, fake proof, or decorative controls that appear functional.
- Repository build, type, lint, console, and responsive checks proportionate to scope.

## Pattern recording template

Use this template when adding future corpus-derived patterns:

```text
NAME
PURPOSE
OBSERVED MECHANISM
CHOOSE WHEN
AVOID WHEN
REQUIRED INPUTS
RESPONSIVE TRANSFORMATION
ACCESSIBILITY SAFEGUARDS
PERFORMANCE SAFEGUARDS
VERIFICATION
```

Abstract away brands, exact copy, private URLs, and distinctive asset identities. Preserve implementation lessons and acceptance logic.

