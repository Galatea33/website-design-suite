# Immersive Scroll Worlds

Use this reference when a website's concept, authoritative reference, or implementation includes a persistent real-time 3D world that changes composition across scroll chapters. Do not use it for ordinary parallax, a looping video, a scroll-scrubbed image sequence, or decorative particles by themselves.

## Source and reuse boundary

This guidance distills general mechanisms from the public Kage experience and Meng To's MIT-licensed web-design skills. The Kage repository does not grant reuse or redistribution rights for its original code or artwork. Inspect it to understand behavior, but do not copy its source, art, distinctive scene, or prompt language into user work. Create original worlds and verify the license of every source before reuse.

Sources:

- Kage live experience and repository: <https://mengto.github.io/kage/> and <https://github.com/MengTo/kage>
- Scroll-world skill: <https://github.com/MengTo/skills/blob/main/agent-skills/web-design/build-threejs-scroll-worlds/SKILL.md>
- Falling-leaves skill: <https://github.com/MengTo/skills/blob/main/agent-skills/web-design/falling-leaves/SKILL.md>
- Pointer-trail skill: <https://github.com/MengTo/skills/blob/main/agent-skills/web-design/pointer-trail-emitter/SKILL.md>
- Skill-library license: <https://github.com/MengTo/skills/blob/main/LICENSE>

## Choose the correct renderer

| Experience | Preferred mechanism |
|---|---|
| Persistent spatial objects remain meaningful across several chapters | One real-time 3D world with a continuous camera path |
| A linear cinematic sequence does not need real-time interaction | Video or image sequence |
| DOM content and ordinary transitions carry the experience | DOM-first scroll storytelling |
| One decorative 3D object supports an otherwise normal page | Isolated 3D component, not a site-wide world |

Require a written reason why real-time 3D earns its loading, rendering, accessibility, and maintenance cost.

## Addendum to the Design Contract

Record these fields before implementation:

- **Narrative role:** What the world explains or makes memorable.
- **World topology:** Continuous geography, connected sets, or layered reveal.
- **Chapter ledger:** Four to eight chapters with story beat, semantic DOM content, camera endpoint, focus object, environment change, interaction, and mobile override.
- **Visual system:** Geometry language, materials, light, fog, post-processing, and asset provenance.
- **Input model:** Native scroll, anchors, keyboard, touch, pointer, and any hotspots.
- **Loading plan:** Complete first authored frame, next-chapter prefetch, progress/loading state, and poster fallback.
- **Capability policy:** Minimum device target, DPR and quality tiers, reduced-motion composition, failure state, and static/mobile alternative.
- **Acceptance evidence:** Chapter endpoints and transitions at named viewports plus measured performance on representative hardware.

## Architecture rules

- Prefer one renderer, one scene, and one persistent world unless multiple contexts are justified and budgeted.
- Keep semantic headings, copy, navigation, and primary actions in the DOM above the canvas. Mirror essential 3D hotspots with keyboard-accessible DOM controls.
- Map native scroll to an exact target state for anchors, reload, history, and accessibility. Use a separate damped render state for visual smoothness. Never replace native scroll merely to make interpolation easier.
- Store chapter, camera, lighting, fog, and interaction states as data. Design endpoints independently for desktop and mobile; mobile is a new composition, not a uniformly shrunken desktop path.
- Make transitions deterministic and reversible. Test slow, fast, reverse, scrollbar-drag, anchor-jump, reload-at-depth, resize, and orientation change.
- Treat particles and pointer effects as supporting atmosphere. They must never carry instructions, navigation, or essential meaning.

## Performance starting gates

Treat these as provisional budgets to test, not guarantees:

| Measure | Mobile starting gate | Desktop starting gate |
|---|---:|---:|
| Device-pixel ratio cap | 1.25-1.5 | 1.5-2 |
| Visible triangles | 150k-300k | 500k-1.2m |
| Draw calls | 50-90 | 90-160 |
| Shadow-casting lights | 1-2 | 2-4 |
| Full-screen blended layers | 2 | 3 |
| Critical initial transfer | 3-6 MB | 5-10 MB |

- Measure frame time, memory, transfer, decode, and input responsiveness on real representative devices. Target 16.7 ms frames when practical; introduce a simpler tier before sustained mobile frames exceed roughly 25 ms.
- Use a quality governor that can reduce DPR, post-processing, shadows, particles, and distant detail without changing the story.
- Pause rendering and ambient simulation while hidden. Clamp large frame deltas after wake. Dispose geometry, materials, textures, render targets, observers, and listeners on teardown.
- Handle loading failure and WebGL context loss with a usable poster-backed DOM experience.

## Specialist effects

### Falling leaves or similar instanced particles

- Use one instanced mesh where practical; avoid one draw call per particle.
- Make leaves tumble edge-on, vary front/back appearance and physical parameters, and couple lateral slip to tumble phase.
- Recycle particles ahead of the camera path rather than around a fixed origin.
- Scale count with viewport area, cap DPR, use alpha testing where it reduces fill cost, pause offscreen/hidden work, and render a designed still for reduced motion.

### Pointer trail emitter

- Emit by distance traveled, not by elapsed time, so density stays consistent at different pointer speeds.
- Interpolate emission points along long pointer segments and use a bounded ring buffer.
- In 3D, anchor the trail to a camera-facing or screen-aligned plane so composition survives camera motion.
- Provide touch, keyboard, coarse-pointer, idle, and reduced-motion behavior. Keep the trail inside the existing rendering/post-processing chain unless measurement proves a DOM overlay is better.

Use the external specialist skills when they are installed and the effect is explicitly required. Their presence is not permission to add the effects.

## Verification matrix

At minimum inspect 1440x900, 768x1024, and 390x844 when those sizes are relevant. Capture representative chapter endpoints and test the transitions between them. Verify semantic reading order, anchors, keyboard access, touch behavior, focus visibility, reduced motion, data-saving/static fallback, first-frame loading, asset failure, context loss, tab hiding, resize, cleanup, and console output.

