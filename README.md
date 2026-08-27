# Website Design Suite

A coordinated three-skill system for designing, recreating, and reviewing websites with Codex.

The suite separates design discovery, reference-led reconstruction, and UX critique so that an agent does not jump straight into implementation or flatten every project into the same visual style.

## The three parts

### Part 1 — Architect

`website-design-suite-part-1-architect`

The normal entry point for original sites and redesigns. It runs a concise adaptive intake, creates a Design Contract, produces the requested first draft, and coordinates the other parts when they are useful.

Use it for prompts such as:

```text
$website-design-suite-part-1-architect Help me design a website for an academic writer. Ask me the important questions first.
```

### Part 2 — Recreation

`website-design-suite-part-2-recreation`

For authorized reference-led work where measurable visual or behavioral fidelity is the governing requirement. It can work from screenshots, live URLs, Figma files, PDFs, videos, code, or detailed specifications.

Use it directly for prompts such as:

```text
$website-design-suite-part-2-recreation Recreate this authorized landing page from the supplied desktop and mobile screenshots.
```

When a reference is only inspiration, start with Part 1. Part 2 deliberately avoids turning inspiration into an unauthorized copy.

### Part 3 — UX Critic

`website-design-suite-part-3-ux-critic`

A read-only senior UX and design review. It evaluates clarity, hierarchy, conversion, responsive behavior, accessibility, motion, performance, fidelity, and generic-template drift, then prioritizes the smallest coherent improvements.

Use it directly for prompts such as:

```text
$website-design-suite-part-3-ux-critic Review this site and rank only the changes worth making before launch.
```

## Recommended workflow

For most projects, invoke only Part 1. It automatically decides whether Part 2 is appropriate and uses Part 3 as the post-draft quality gate.

```text
Part 1: discovery and Design Contract
        ↓
Part 2: reference reconstruction, only when required
        ↓
Part 3: UX and quality review
```

Standalone usage is also supported:

- Use Part 1 for a new direction, redesign, or guided brief.
- Use Part 2 for a faithful authorized recreation or fidelity correction.
- Use Part 3 for an independent audit of an existing site or draft.

## Installation

Each folder under [`skills/`](skills/) is a complete installable skill.

### Shared ChatGPT/Codex installation

Copy all three skill folders into your user-level skills directory:

```text
~/.agents/skills/
```

This produces:

```text
~/.agents/skills/website-design-suite-part-1-architect/
~/.agents/skills/website-design-suite-part-2-recreation/
~/.agents/skills/website-design-suite-part-3-ux-critic/
```

### Codex-only installation

Alternatively, copy the three folders into:

```text
~/.codex/skills/
```

Start a new task after installation if the skills do not appear immediately.

## Suite principles

- Ask only questions that materially change the design.
- Establish purpose, audience, content, and primary action before choosing effects.
- Treat supplied references as evidence, not permission to copy third-party work.
- Keep authoritative requirements separate from observations, inferences, and open questions.
- Do not impose video, glass, gradients, cards, 3D, or a generic SaaS house style.
- Treat responsive behavior as authored transformation rather than desktop shrinking.
- Target WCAG 2.2 AA and plan reduced-motion and media fallbacks.
- Validate implemented work at representative viewports and interaction states.
- Preserve strong design decisions while prioritizing high-impact corrections.

## Repository structure

```text
skills/
├── website-design-suite-part-1-architect/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
├── website-design-suite-part-2-recreation/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
└── website-design-suite-part-3-ux-critic/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/
```

Part 1 owns the shared pattern library and immersive-scroll guidance. Parts 2 and 3 reference those resources through sibling-relative paths, so install all three folders together to retain the complete coordinated workflow.

## License

Released under the [MIT License](LICENSE).

