# Creative Direction Guidelines

## Overview
The design guidelines make a site correct, accessible and consistent. This
document makes it **specific to the client**. Every page must express the
**Creative Direction** section of `website-brief.md` — the concept, signature
motif, shape language, style dials, imagery style and anti-references captured
in the interview.

If two websites built with this framework could swap logos and nobody would
notice, the creative direction was not applied.

**Precedence:** the design guidelines (accessibility, contrast, one H1, touch
targets, responsive rules) always win. Creative direction decides *how* a page
looks within those limits, never *whether* it meets them.

**If the brief has no Creative Direction section** (older briefs), do not
guess. Ask the client one question: "What is one shape, object or detail that
is unmistakably part of your business?" Then continue.

---

## 1. Concept → design decisions

The brief contains a one-sentence **Creative concept** and 3 **design
principles**. Before writing any code, write a short comment at the top of the
CSS file stating how the concept shows up in each of these decisions:

1. Shape language (corners, dividers, image masks)
2. Signature motif (where it appears — see section 2)
3. Typography treatment (weight, case, scale contrast)
4. Spacing and density
5. Color distribution (which color dominates, where the accent is spent)
6. Imagery treatment
7. Layout rhythm (see section 4)

If a decision cannot be traced to the brief's concept, dials or motif, it is a
default — and defaults are what make sites generic. Replace it.

---

## 2. Signature motif

The motif is the shape, symbol, pattern or object the client identified as
distinctly theirs (e.g. a leaf curve, a hexagon, a wave, a tool outline, an
arch, a stitch pattern).

### Where it must appear
Use the motif in **at least three different roles** on every page. Pick from:

| Role | Examples |
|---|---|
| Section dividers | Wave, arch, zigzag or notch edge via `clip-path` or an SVG divider instead of a straight line |
| Image masks / frames | Photos cropped to the motif shape using `clip-path` or `border-radius` |
| Hero background | Oversized, low-contrast motif shapes behind or cropping into the headline |
| Bullets and icons | Motif used as list markers, service icons or step numbers |
| Cards and buttons | Corner treatment, notch, or border style derived from the motif |
| Backgrounds | Repeating pattern at 4–8% opacity on one or two sections |
| Details | Hover states, underline style on links, favicon, footer ornament |

### Rules
- Build the motif with **inline SVG or CSS geometry** (`clip-path`,
  `border-radius`, gradients, pseudo-elements). No JavaScript, no external
  libraries, no placeholder image services.
- If the client supplied an SVG logo or icon, derive the motif from it. Do not
  redraw or alter the logo itself.
- If the motif is too complex to reproduce faithfully with simple geometry
  (e.g. a detailed illustration), use a simplified abstract version of its
  *outline or rhythm* and add a note to the page: `<!-- Motif simplified: ask
  client for an SVG version -->`. Never invent a different symbol.
- Decorative motif elements must use `aria-hidden="true"` and `alt=""`; they
  must never carry meaning or block content.
- Motif repetition must stay intentional: restraint beats saturation. One hero
  use, one repeating use, one detail use is enough.
- Keep text contrast at 4.5:1 over any motif background (design guidelines).

### If the client has no motif
Derive one from the interview answers about the **personal story, place,
material or object** tied to the business. State the derived motif in the CSS
comment so it is traceable.

---

## 3. Style dials → implementation

The brief records the client's position on five dials. Apply them consistently
across the whole page.

| Dial | Leans left | Leans right |
|---|---|---|
| Era | **Classic**: serif or high-contrast headings, generous margins, ornamental rules, symmetrical layout | **Modern**: sans-serif headings, tight tracking, asymmetric layout, large type scale |
| Mood | **Playful**: rounded shapes, tilted elements, bold accent color, friendly microcopy, bouncy hover transitions | **Serious**: restrained palette, straight edges, small corner radii, calm transitions |
| Richness | **Minimal**: few elements, lots of whitespace, one accent, type-led sections | **Rich**: layered backgrounds, textures, overlapping elements, more imagery |
| Temperature | **Warm**: off-white or cream backgrounds, warm neutrals, soft shadows | **Cool**: pure or blue-grey neutrals, crisp borders, sharper shadows |
| Form | **Organic**: curves, blobs, irregular masks, flowing dividers | **Geometric**: grids, straight lines, hard angles, repeating shapes |

Express each dial in at least one visible, global decision (corner radius
tokens, divider style, heading font weight, background neutral, shadow style).
Define them as CSS custom properties in `:root` — for example
`--radius-card`, `--divider-shape`, `--surface-neutral` — so the direction is
consistent and editable.

A dial marked "balanced" means: do not push it either way; do not use it to
justify a default.

---

## 4. Layout rhythm — avoid the template look

The most common generic pattern is: centered hero → three identical cards →
alternating text/image rows → centered CTA. Avoid repeating the same layout
across consecutive sections.

- No more than two consecutive sections may share the same layout structure.
- Vary at least three of these between sections: alignment (left, centered,
  offset), column split (50/50, 60/40, 70/30), background (neutral, tinted,
  primary, pattern), density (airy vs. compact), and presence of imagery.
- Use one **signature section** per page — a deliberate moment that breaks the
  rhythm (an oversized statement, a full-bleed motif band, a stacked numbered
  list, an offset image collage) — built from the brief's concept and
  "first impression" answer.
- Heading scale contrast should be visible: the hero H1 should be clearly
  larger than a default `2rem`, with deliberate line breaks and weight.
- Service cards must differ from the generic icon + title + text pattern when
  the brief's imagery style or motif offers an alternative (motif-shaped image
  masks, numbered blocks, large type labels).

---

## 5. Imagery and iconography

Follow the brief's **Imagery style** (photography, illustration, graphic or
type-led) and **Image mood**.

- Photography: apply one consistent treatment (aspect ratio, crop, mask, or
  duotone via CSS) so images from different sources feel unified.
- Illustration or graphic: build from the palette and motif; no emoji or
  generic icon packs as icons.
- Type-led: give typography the main visual role — large scale, mixed weights,
  strong alignment.
- Never use stock-style imagery descriptions in alt text; describe what is
  actually in the image.

---

## 6. Anti-reference (what must NOT happen)

The brief lists the client's **anti-references** — looks they do not want and
competitors to avoid resembling. Treat each as a hard constraint equal to
"words to avoid" in the content guidelines. Before delivering, state in the CSS
comment how the page avoids each one.

### Default patterns that need a deliberate reason to appear
- Generic blue-to-purple gradients as hero backgrounds
- Centered H1 over a darkened full-width stock-style photo, with no other
  design idea
- Three equal cards with circular icons directly below the hero
- Identical rounded-corner cards with drop shadows everywhere
- Emoji or default icon-pack icons used as decoration
- Pure white page with gray text and a single blue button
- Lorem-ipsum-feeling copy that could belong to any business

If one of these appears, there must be a reason in the brief that justifies it.

---

## 7. Creative direction quality gate

Before delivering a page, verify:

- [ ] A CSS comment maps the concept to the seven decisions in section 1
- [ ] The motif appears in at least three different roles
- [ ] The five style dials are visible in `:root` custom properties and
  actually used
- [ ] No more than two consecutive sections share the same layout
- [ ] One signature section exists
- [ ] Imagery treatment matches the brief
- [ ] Every anti-reference is explicitly avoided
- [ ] The "swap the logo" test passes: this page could not belong to another
  client without edits
- [ ] Contrast, touch targets and one-H1 rules from the design guidelines
  still pass
