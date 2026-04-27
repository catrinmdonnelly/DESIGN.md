# DESIGN.md

A design system in a single markdown file. Tells your AI assistant how every screen, page, and component should look. Stops it from defaulting to glassmorphism, gradient hero sections, and three-column feature grids.

This is one of a family of five templates that customise AI for the way you actually work.

| Template | What it covers | When to do it |
|----------|----------------|---------------|
| **[CLAUDE.md](https://github.com/catrinmdonnelly/CLAUDE.md)** | Who you are, how you work, what's on your desk | First. Even if you do nothing else, this gets you 70% of the value |
| **[COPY.md](https://github.com/catrinmdonnelly/COPY.md)** | How things should sound. Voice + banned phrases | Second. Voice is the most-violated AI default |
| **[DESIGN.md](https://github.com/catrinmdonnelly/DESIGN.md)** (this repo) | How things should look. Design tokens + banned aesthetics | Third. Only if you make visual things (websites, slides, social posts) |
| **[CONTEXT.md](https://github.com/catrinmdonnelly/CONTEXT.md)** | What each project is and where it's going | Per project, when you start working in a specific folder |
| **[NORTH-STAR.md](https://github.com/catrinmdonnelly/NORTH-STAR.md)** | Career-level direction. The why behind the projects | Last, and only if you have multiple businesses or want to think strategically |

You don't have to do all five. The minimum useful set is **CLAUDE.md + COPY.md**. Add the others as you need them.

They reference each other. Your CLAUDE.md tells AI to read the others when the relevant work comes up, so you do not have to think about which file is needed when.

## Why this exists

AI assistants have a default aesthetic and it's bad. Glassmorphism. Gradient backgrounds. Neon accents. Floating blobs. Three-column features sections. Same Tailwind buttons everyone has. That's not design, it's the visual equivalent of "delve" in copy.

A DESIGN.md is the brief that stops it.

## Built on the work of others

This template aligns with a forming standard, not invents one. If anything in here is good, the credit goes to:

- **[Google Labs](https://github.com/google-labs-code/design.md)** for publishing the open `design.md` spec on 22 April 2026. This template's structure follows that spec with a few additions.
- **[Brad Frost](https://atomicdesign.bradfrost.com)** for Atomic Design, the philosophy that maps cleanly to tokens, components, patterns.
- **[GOV.UK Design System](https://design-system.service.gov.uk)** for the gold standard in plain-language design documentation. The do/don't pattern and the audience-first writing came from there.
- **[Shopify Polaris](https://polaris.shopify.com)** for the rationale-first writing pattern (always explain why, not just what).
- **[Hardik Pandya](https://hvpandya.com/llm-design-systems)** for naming the failure mode I built around: unwired DESIGN.md files get ignored. The "wiring step" exists because of his article.
- **[VoltAgent](https://github.com/VoltAgent/awesome-design-md)** for curating 69 brand examples that showed what works across many categories.

What's mine is the non-tech-friendly framing, the "banned aesthetics" list with specific AI defaults, the conversational walk-through, and the integration with CLAUDE.md and COPY.md as a coherent family.

## What this template adds to the Google Labs spec

Three things they don't include:

1. **Plain-English explanations** alongside the YAML (the bit at the top in `---` marks, machine-readable), for non-technical owners who can't read design tokens
2. **A "banned aesthetics" list** that explicitly kills the generic-AI defaults
3. **Wiring instructions**: the line you add to your CLAUDE.md so AI actually reads DESIGN.md (most templates skip this step, which is why they get ignored)

## Who it's for

- **Solo founders** who need their AI assistant to design things consistently for their brand
- **Designers** working with AI agents and tired of fighting defaults
- **Small teams** sharing a single design source of truth via git
- **Anyone using Claude, Cursor, v0, Lovable, or similar** to generate UI

## What's in this repo

| File | What |
|------|------|
| `DESIGN.md` | The template. Walk through it with Claude (paste it into a chat) or fill it in by hand. |
| `README.md` | This file. |
| `LICENSE` | MIT. |

## How to use

There are two ways to use this template:

### Conversational (the easy way, for non-technical users)
1. Open `DESIGN.md` in this repo, copy the whole file
2. Paste it into a Claude chat. Claude reads the meta-instruction at the top and walks you through it section by section
3. Claude will propose specific colour values, fonts, and tokens based on your description of the feel
4. At the end, you get a clean version (comments stripped) to save as `DESIGN.md` in your project folder

### Manual (for designers and developers)
1. Copy `DESIGN.md` to your project folder
2. Fill in the YAML frontmatter (your colour hex codes, font choices, spacing scale)
3. Write the body sections (Aesthetic direction, Inspiration, Do's and Don'ts) in your own words
4. Delete the HTML comments. Save.

### The non-negotiable wiring step

Whichever way you use it, you must add this line to your `CLAUDE.md` so AI actually reads `DESIGN.md` before any visual work:

```
Read DESIGN.md before any visual or UI work. Use only the tokens defined in its frontmatter. Do not invent values.
```

Without that line, AI treats DESIGN.md as inspiration, not law. With it, AI treats it as a rule.

## The structure

The standard DESIGN.md has twelve sections:

1. **Frontmatter**: machine-readable tokens (YAML)
2. **Wiring**: the line that goes in your CLAUDE.md
3. **Product context**: who, what, what it isn't
4. **Aesthetic direction**: the feel, references, decoration level
5. **Colour**: palette, semantic roles, dark mode strategy
6. **Typography**: families, scale, weight assignments
7. **Spacing**: base unit and scale
8. **Layout**: grid, max width, breakpoints
9. **Shape and elevation**: radius scale, shadow tiers (or "no shadows" rule)
10. **Motion**: easing, duration, when to animate
11. **Components**: atoms with states, referencing tokens
12. **Do's and don'ts**: guardrails and banned patterns
13. **Decisions log**: date-stamped record of what changed and why

## The five things I learned from research

1. **Wire it explicitly via CLAUDE.md or AI ignores it.** This is the single biggest finding. A DESIGN.md sitting unwired in the repo is treated as optional context.
2. **Banned patterns matter as much as preferred ones.** "No glassmorphism" is more useful than "modern and clean."
3. **Keep total file under ~3,000 tokens.** Larger files get partially ignored mid-context. Use variants for different scales.
4. **Tokens with prose, not tokens or prose.** YAML alone leaves AI guessing when to use what. Prose alone leaves it inventing values.
5. **A decisions log compounds.** Future-you needs to know why the radius is 4px and not 6px.

## The "banned aesthetics" list

This is the highest-leverage section. The current AI defaults that this list is fighting:

- Glassmorphism (frosted glass effects)
- Gradient hero sections
- Neon glow, iridescent surfaces
- Floating blobs and organic shapes
- Three-column feature grids
- Dark mode by default
- Strokes and borders on cards
- Pill-shaped buttons everywhere
- Title case headings
- Em dashes in copy and labels

Edit the list to match your brand. The act of writing it down is what makes it stick.

## References

The best thinking I found while writing this:

- [Google Labs DESIGN.md spec](https://github.com/google-labs-code/design.md): the canonical format (Apache 2.0, the de facto standard as of April 2026)
- [Stitch DESIGN.md format docs](https://stitch.withgoogle.com/docs/design-md/format/): how the spec is structured
- [VoltAgent awesome-design-md](https://github.com/VoltAgent/awesome-design-md): 69 brand examples to learn from
- [Hardik Pandya: Expose your design system to LLMs](https://hvpandya.com/llm-design-systems): failure modes and the three-layer token system
- [buildthisnow.com: DESIGN.md for Claude Code](https://www.buildthisnow.com/blog/guide/mechanics/design-md-claude-code): the reference-vs-constraint distinction
- [Brad Frost: Atomic Design](https://atomicdesign.bradfrost.com): the philosophy that maps cleanly to tokens, components, patterns
- [GOV.UK Design System](https://design-system.service.gov.uk): best-in-class plain-language section structure for non-technical readers
- [Shopify Polaris](https://polaris.shopify.com): rationale-first writing pattern
- [Tailwind theme docs](https://tailwindcss.com/docs/theme): DESIGN.md tokens map cleanly to `tailwind.config`

## Pair this with

- [CLAUDE.md](https://github.com/catrinmdonnelly/CLAUDE.md): context file Claude reads on every session
- [CONTEXT.md](https://github.com/catrinmdonnelly/CONTEXT.md): per-project context file
- [NORTH-STAR.md](https://github.com/catrinmdonnelly/NORTH-STAR.md): career-level direction
- [COPY.md](https://github.com/catrinmdonnelly/COPY.md): brand voice and banned phrases

## License

MIT. Do whatever you want with it. Credit appreciated, not required.

Made by [Catrin Donnelly](https://catrinmd.netlify.app), North Wales.
