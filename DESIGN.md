---
# ═══════════════════════════════════════════════════════════════════════
# DESIGN TOKENS (machine-readable)
# Replace the bracketed values with real ones. Hex codes only for colours.
# AI agents read these directly and use them as constraints.
# Comments inside this YAML block start with # and get stripped on save.
# ═══════════════════════════════════════════════════════════════════════

version: 1
name: [Your design system name. E.g. "Daylight Prestige"]
description: [One paragraph on the feel. What it looks like, what it doesn't]
audience: [Who you're designing for, in plain English. E.g. "Non-technical UK SME owners"]

# COLOURS
# Light backgrounds by default. The accent appears in one or two moments
# per screen, never everywhere. Hex codes only.
colors:
  primary: "[#hex, your main ink colour. Near-black, never pure black]"
  secondary: "[#hex, secondary text]"
  neutral: "[#hex, page background. Light unless you have a real reason]"
  surface: "[#hex, cards and elevated surfaces]"
  surface-muted: "[#hex, soft backgrounds]"
  border-subtle: "[#hex, dividers]"
  accent: "[#hex, the one colour that lands. Should feel luminous]"
  error: "[#hex, destructive actions and validation]"

# TYPOGRAPHY
# Family is your call. Scale and weights are the global recommendation.
# Sentence case for every heading, label, and button. Never title case.
typography:
  family-display: "[The font you use for headings. Be specific]"
  family-body: "[The font you use for body. Be specific]"
  family-mono: "[The font you use for code or labels. Be specific]"
  scale:
    display: { size: "64px", weight: 600, lineHeight: 1.05, tracking: "-0.02em" }
    h1: { size: "48px", weight: 600, lineHeight: 1.1, tracking: "-0.02em" }
    h2: { size: "32px", weight: 500, lineHeight: 1.2, tracking: "-0.01em" }
    h3: { size: "22px", weight: 500, lineHeight: 1.3 }
    body-lg: { size: "18px", weight: 400, lineHeight: 1.6 }
    body-md: { size: "16px", weight: 400, lineHeight: 1.6 }
    body-sm: { size: "14px", weight: 400, lineHeight: 1.55 }
    label: { size: "14px", weight: 500, lineHeight: 1.2, tracking: "0.02em" }
    caption: { size: "12px", weight: 400, lineHeight: 1.4 }

# SPACING
# 8-point scale with a 4-point half-step. Nothing eyeballed.
spacing:
  base: "8px"
  scale:
    xs: "4px"
    sm: "8px"
    md: "16px"
    lg: "32px"
    xl: "64px"
    2xl: "96px"

# RADIUS
# Small. Never pill-shaped except for status dots and avatars.
rounded:
  none: "0px"
  sm: "4px"
  md: "6px"
  lg: "10px"
  full: "9999px"

# COMPONENTS
# Reference tokens by name (e.g. {colors.primary}), not raw values.
# This is what stops drift between the doc and the rendered UI.
components:
  button-primary:
    background: "{colors.primary}"
    text: "{colors.neutral}"
    typography: "{typography.scale.label}"
    rounded: "{rounded.md}"
    padding: "14px 22px"
  card:
    background: "{colors.surface}"
    text: "{colors.primary}"
    rounded: "{rounded.lg}"
    padding: "24px"
    border: none
    shadow: "0 2px 12px rgba(0,0,0,0.04)"
---

<!-- ═══════════════════════════════════════════════════════════════════════
     INSTRUCTIONS FOR CLAUDE (READ FIRST, THEN REMOVE BEFORE SAVING)

     The user has pasted this template into the chat to set up their DESIGN.md
     file. They are likely non-technical. Be patient and conversational.

     What you do:
     1. Greet them briefly without assuming you know them. Treat this as a
        fresh setup, even if you have memory from previous chats.
     2. Tell them this file describes how their work should look, so AI
        assistants stop defaulting to generic aesthetics like glassmorphism,
        gradient hero sections, and neon accents.
     3. Ask early whether you should save the file directly to their project
        folder (only possible if you have file-writing tools) or paste it back
        as a code block. Default to the code-block option if you can't tell.
     4. Walk them through filling in the values. Start with the body sections
        (Aesthetic direction, Inspiration) before the YAML tokens, because
        the body shapes the colour and font choices.
     5. For each section: read the HTML comment, ask the questions needed
        to fill in the [bracketed bits]. One section at a time. For the
        YAML tokens, propose specific hex values they confirm rather than
        making them generate them.
     6. The Aesthetic direction is the most creative section. Push them
        to use a vivid metaphor, not abstract adjectives. "Modern" and
        "clean" mean nothing.
     7. The Inspiration section needs SPECIFIC references with what they
        take from each. "I like Apple" is useless. "I like the white space
        in Apple's product pages" is useful.
     8. When you've worked through every section, output a CLEAN version:
        - Remove THIS instruction block (everything between the ═ lines above)
        - Remove every other <!-- comment --> in the body, including the
          per-section explainer comments
        - Remove every # comment line inside the YAML frontmatter
        - Keep only the filled-in values and the section headings
     9. Then explain the WIRING step: they must add the line below to
        their CLAUDE.md so AI actually reads DESIGN.md before UI work.
        This step is the most-missed and the most important.
    10. Deliver the file as agreed in step 3 (save to disk, or paste in a
        code block).

     Important:
     - Do not assume you know the user's name. Ask them in this chat.
     - Do not invent design tokens for them. Ask, propose, confirm.
     - The "banned aesthetics" Don't list is high-leverage. Don't water it down.
     - File should land under 250 lines after they fill in.
══════════════════════════════════════════════════════════════════════════ -->

# Design system

<!-- This file does two jobs: the YAML frontmatter is the machine-readable
     spec (AI agents read tokens directly), the markdown body is the human-
     readable explanation (the why behind each choice).
     Both halves must agree. If they drift, the rendered UI drifts. -->

## Wiring (this step is non-negotiable)

<!-- Without this line in CLAUDE.md, AI treats DESIGN.md as inspiration,
     not law. The single biggest finding from the research:
     unwired DESIGN.md files get ignored. -->

This file does nothing on its own. To make Claude (or Cursor, or v0) actually obey it, add this line to your `CLAUDE.md`:

```
Read DESIGN.md before any visual or UI work. Use only the tokens defined in its frontmatter. Do not invent values. Match component states exactly.
```

Without that line, the file gets treated as inspiration. With it, it gets treated as a rule.

## Product context

<!-- Three to five lines on who, what, what it isn't. Grounds every later
     decision. If the audience changes, this whole file changes. -->

[Who you're designing for. What it is. What it isn't. Three to five lines. The grounding for every later decision.]

## Aesthetic direction

<!-- The most creative section. A vivid metaphor or image, not abstract
     adjectives. Vague descriptions like "modern" and "clean" mean nothing
     to AI or humans. A good aesthetic direction reads like a sentence
     from a novel. -->

The feel. Use a vivid metaphor or image, not abstract adjectives.

[Write 1-2 paragraphs. Examples:
- "Sunlight hitting a crystal and projecting luminous circles of spectrum colour onto a plain wall. The wall does nothing. The light does everything. Colour is not applied, it lands."
- "An old-school bookshop on a rainy afternoon. Warm wood, soft yellow light, the kind of quiet where you can hear pages turn."
- "A Japanese ryokan: precise, restrained, every object earning its place."]

Then say what kind of decoration is OK and what isn't, in plain language.

## Inspiration

<!-- The references that calibrate everything else. Be SPECIFIC about what
     you take from each one. "I like Apple" is useless. "I like the white
     space and quiet typography of Apple's product pages" is useful. -->

The references that calibrate everything else.

### Looks like
<!-- Brands or sites you draw from. What specifically. -->
- **[Site or brand]:** [What specifically. E.g. "GOV.UK Design System: plain-language section structure, generous whitespace, no decoration"]
- **[Site or brand]:** [What specifically]
- **[Site or brand]:** [What specifically]

### Doesn't look like
<!-- Equally important. What you actively reject. -->
- **[Site or brand]:** [What specifically. E.g. "Generic SaaS landing pages: gradient hero, three-column features, neon CTAs"]
- **[Site or brand]:** [What specifically]

### Real-world references (not just websites)
<!-- The non-digital things that inform the feel. -->
- **[Reference]:** [What it gives you. E.g. "Dieter Rams product photography: light as the hero, neutral background"]
- **[Reference]:** [What it gives you. E.g. "Newsreader-set editorial pages: restraint with character"]
- **[Reference]:** [What it gives you. E.g. "Brutalist concrete architecture: stark, considered, lasting"]

## Colour

<!-- Translate the YAML colour tokens into plain English with rationale.
     The rationale is what helps AI make judgement calls in unfamiliar
     situations. -->

Light backgrounds by default. The accent appears in one or two moments per screen, never everywhere.

| Role | Token | Use |
|------|-------|-----|
| Primary | `{colors.primary}` | Body text, headings. Near-black, never pure black. |
| Neutral | `{colors.neutral}` | Page background. |
| Surface | `{colors.surface}` | Cards and elevated surfaces. |
| Accent | `{colors.accent}` | Links, primary buttons, status indicators. The colour that lands. |
| Error | `{colors.error}` | Destructive actions only. |

**Dark mode:** [Either describe your dark variant or write "Not supported. The system is light by default."]

## Typography

<!-- Family choice is yours. Scale, weight, and tracking are the global
     recommendation in the YAML. Sentence case is the rule, regardless. -->

**Heading family:** [Your display font]. Sentence case for every heading, label, and button. Never title case. Never all caps.

**Body family:** [Your body font].

**Mono family:** [Your monospace font, used for code, labels, technical data].

Scale defined in frontmatter. Use named tokens (`{typography.scale.h1}`) rather than hard-coded sizes.

## Spacing

<!-- 8-point scale, 4-point half-step. Every gap, padding, and margin
     resolves to a scale value. Eyeballed spacing is the start of drift. -->

8-point scale with a 4-point half-step. Every gap, padding, and margin resolves to a scale value. Nothing eyeballed.

## Layout

<!-- Container behaviour, grid, breakpoints. The architectural rules
     for how content sits on the page. -->

Max content width: **1200px** on desktop, fluid on mobile. Content prefers to breathe. Vertical rhythm between sections is deliberate (32px to 64px depending on hierarchy).

## Shape and elevation

<!-- The two things AI gets wrong most often: card borders (always wants
     to add them) and pill-shaped buttons (always wants to use them). -->

- Border radius: 4-10px. Never pill-shaped except for status dots and avatars.
- Elevation: tonal contrast and soft shadow. **Never strokes or borders on cards.**
- Circles appear intentionally as focal points (status dots, framing devices), never as decoration.

## Motion

<!-- Restrained. Most things should be static. Movement is for moments
     that earn it, not for showing off animation skill. -->

[How things move. Easing, duration, when to animate. Example: "Most transitions 120ms ease. Hover states shift colour, never opacity. No scroll-triggered animation."]

## Components

<!-- Atoms with their states. Reference tokens, not raw values. -->

Defined in frontmatter. Each component references tokens, not raw values.

**Cards:** white surface on neutral background, large radius, subtle shadow, no border ever.
**Buttons:** one primary action per view. Never two competing.
**Inputs:** focus state on the bottom border only, in the accent colour. Never a full box outline.

## Do

<!-- The required behaviours. Pair with Don't list below. -->

- Use sentence case for every heading, bullet, label, and button.
- Keep backgrounds light by default.
- Use the spacing scale. Nothing eyeballed.
- Use soft shadow and tonal contrast for depth.
- Maintain WCAG AA contrast (4.5:1 normal text, 3:1 large text).
- Reference tokens by name, not value.

## Don't

<!-- The "banned aesthetics" list. THIS is the highest-leverage section.
     Without it, AI defaults to glassmorphism, gradients, and neon.
     Edit and add to this list as you spot patterns to reject. -->

- **No em dashes anywhere**, in copy or labels. Use commas, full stops, or restructure.
- No title case. No all caps.
- No borders or strokes on cards or containers.
- No dark backgrounds by default.
- No glassmorphism, neon glow, gradient hero sections, floating blobs, iridescent surfaces.
- No flat corporate blues, muddy earth tones, or neon as accents.
- No two primary buttons competing on one screen.
- No mixing sharp 0px corners with rounded ones in the same view.
- No decorative elements without a purpose.

## Decisions log

<!-- Date-stamped record of changes. Future-you needs to know why the
     radius is 4px and not 6px. Yearly review at minimum. -->

| Date | Change | Why |
|------|--------|-----|
| [YYYY-MM-DD] | [What changed] | [Why it changed] |
