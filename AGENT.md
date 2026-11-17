# AGENT.md

This file is written for any AI agent working on this project, regardless of
the tool you are running in. Read it completely before doing anything else.

---

## What this project is

A framework for building client websites. It defines rules for design, content,
and SEO that every page must follow, and templates that define the structure of
each page type. Your job is either to interview a client and produce a brief,
or to read a completed brief and build a page or section.

---

## Two modes

You will always be in one of two modes. Read which one applies and follow
only that section.

---

## MODE A — Interview (no website-brief.md exists yet)

Use this mode when there is no `website-brief.md` at the root, or when the
user asks you to start a new client project.

### Before you start

Read these files silently before saying anything to the user:

```
framework/guidelines/design-guidelines.md
framework/guidelines/creative-direction.md
framework/guidelines/content-guidelines.md
framework/guidelines/seo-guidelines.md
framework/pages/home.md
framework/pages/about.md
framework/pages/service.md
framework/pages/contact.md
```

### Language

Your first message must ask which language to use. Detect it from the user's
first message if already written in a specific language and suggest that as
the default.

Conduct the entire interview in the session language. Field labels in
`website-brief.md` stay in English. Field values from the client go in the
session language.

### Interview rules

- One question at a time. Wait for the answer before continuing.
- Suggest a default with every question.
- If you can infer an answer from context, extract it and move on.
- Never ask the user to write their own H1, meta title, or meta description.
- Track what you still need before closing each topic.

### Topics — cover in this order

**1. Business identity**
- Business name or brand name
- What the business does (one or two sentences)
- Ideal customer (specific — age, situation, need)
- What makes the business different
- Tone (up to three words)
- Words or phrases to avoid

**2. Business goal**
- The single most important action a visitor should take

**3. Website format — one-page or multi-page**

Present this as a guided choice, not a bare question. Explain both options:

> "Should this be a **one-page website** or a **multi-page website**?
>
> **One-page** — everything on a single scrollable page with anchor links.
> Best for: freelancers, consultants, focused offers (1–3 services), lead
> generation sites, faster builds.
>
> **Multi-page** — each section has its own dedicated page. Best for:
> businesses with multiple services, strong per-service SEO needs, brands
> that will grow the site over time.
>
> My suggestion: [recommend based on what you know about the business]"

Store the answer as `one-page` or `multi-page` in the brief. This affects
the entire site map and how templates are applied.

**4. SEO**
- 3 to 5 main keywords (how customers search)
- Cities, regions, or countries served
- Existing domain name (if any)
- Reference website URL (if any)
- Confirm keywords are in the language customers search in

**5. Branding and design**
- Brand colors? If yes: hex codes. If no: mood for colors.
- Logo? If yes: format, shape (horizontal/square/stacked), icon version?
  If no: text-based logo from brand name?
- Fonts? If yes: heading and body names. If no: feeling for typography.

**6. Creative direction**

Colors, a logo, and a font are not enough to make a site feel like this
specific business — without more, the build agent falls back on generic
patterns. Collect concrete, personal, visual raw material instead.

Never ask "what style do you want?" — clients can't answer that. Ask
concrete questions about the business, give 2–3 examples with each, and
suggest a default from what you already know. If the client says "I don't
know", offer three options derived from earlier answers. Skip anything
already answered. One question at a time (the style dials are a single
structured exercise).

1. **Signature shape or symbol** (distinct from the logo file format in
   Topic 5): "Is there a shape, symbol, or pattern that is unmistakably part
   of your brand — in your logo, packaging, shop, or just something people
   associate with you? E.g. a leaf curve, hexagon, arch, wave, tool outline,
   stitch pattern." If none: "Is there an object, tool, material, or place
   so tied to your business that people recognize it instantly?" If they have
   a file, save to `assets/images/brand/`.
2. **Personal story hook**: "Is there something personal or specific about
   how this business began — a place, a person, a ritual, a moment — that
   visitors should feel when they land on the site?"
3. **Space and material metaphor**: "If your business were a physical space,
   what would it feel like to walk into (sunlit workshop, quiet library,
   lively market, clean modern clinic)? What materials or textures come to
   mind — wood, stone, linen, glass, paper, metal?"
4. **Style dials**: pick a side (or "balanced") for each pair, suggesting a
   default from the tone given in Topic 1:
   Classic ↔ Modern · Playful ↔ Serious · Minimal ↔ Rich ·
   Warm ↔ Cool · Organic ↔ Geometric
5. **References and anti-references**: up to three websites, brands, shops, or
   packaging they find beautiful (any industry) and what specifically they
   like. Then: "What would make you say 'this looks like every other website
   in my industry'? Any competitor or style to avoid resembling?"
6. **Imagery style**: real photography, illustration, graphic shapes and
   patterns, or mostly typography? Mood of images: candid, polished studio,
   bright and airy, dark and moody?
7. **First impression**: "In the first five seconds, what should a visitor
   feel or remember?"

**Synthesis and playback (required).** Do not just store the answers. Combine
them into a creative concept and read it back in the session language:

> "Here is the creative direction I will give the design agent:
> - **Concept**: [one sentence tying brand story, motif, and metaphor]
> - **Signature motif**: [shape/symbol] — to be used in [section dividers,
>   image shapes, icons, backgrounds…]
> - **Shape language**: [e.g. soft arches and rounded corners]
> - **Design principles**: [three short rules]
> - **Avoid**: [anti-references]
>
> Does this feel like your business? What would you change?"

Revise until the client confirms. If the client has no motif, derive one from
the story, material, or object answers and say so clearly so they can accept
or reject it. The build agent treats the confirmed result as a hard
requirement.

**7. Home page sections**

Tell the client what the home page always includes, then ask about optional
sections:

> "Every home page includes:
> - Hero (headline, subtitle, CTA)
> - About teaser (brief intro linking to About page)
> - Services (preview of all services)
> - Closing CTA
>
> Would you like to add any optional sections?
> - Testimonials — quotes from past clients
> - Gallery — photo grid (work, products, location, team)
> - Team — photos and names of key people
> - Stats — key numbers (years in business, clients served, etc.)
> - FAQ preview — 3 to 5 common questions
> - Latest blog posts — only if there is a blog
>
> My suggestion: [recommend 1–2 based on business type]"

For each selected section, ask what content goes in it and whether that
content already exists.

**8. Services or products**
- Services, products, or both?
- For each: name, description (1–3 sentences), key benefits (up to 5), CTA
- Which is the flagship?

**9. Images and assets**

Now that you know the sections and services, ask specifically about assets.
Go through each type one at a time:

- **Logo** — filename? Remind client to save to `assets/images/logo/`
- **Hero image** — exists? If yes: filename → `assets/images/hero/`.
  If no: ask — solid color, CSS gradient, or placeholder for later?
- **Service images** — for each service: image exists? If yes: filename →
  `assets/images/services/`. If no: placeholder, CSS illustration, or skip?
- **Gallery images** — only if gallery section selected. How many? Filenames?
  → `assets/images/gallery/`
- **Team photos** — only if team section selected. Name, role, filename per
  person. → `assets/images/team/`
- **Brand assets** — only if a motif file, pattern, texture, or reference
  images came up in Topic 6 → `assets/images/brand/`
- **Any other images** the client wants to include

**Rule:** Never assume or invent image paths. If an image is needed and the
client hasn't confirmed it exists, always ask. Never use placeholder image
services unless explicitly requested.

When confirming a filename with the client, always mention that the folder
already exists in the project — they just need to drop the file in. Example:
"Save it to `assets/images/hero/` — that folder is already created in the
project, just drop your file in there."

**10. Contact information**
- Primary email
- Primary phone
- Physical address (and whether to show it)
- Serves in person, online, or both
- Preferred contact method
- Business hours (if relevant)

**11. Tracking and marketing scripts**

Ask for each of these, one at a time. "None" is a valid answer; record it
as "none" so later sessions don't ask again or add scripts on their own.
- Google Analytics — Measurement ID (e.g. `G-XXXXXXXXXX`), or "none"
- Hotjar — Site ID (number), or "none"
- Any additional marketing script (Meta Pixel, Google Tag Manager, Google
  Ads, LinkedIn Insight, etc.) — ask for the name and the exact snippet or
  ID, and whether it goes in `<head>` or at the end of `<body>`. Repeat
  until the client has nothing more to add.

Save snippets exactly as the client provides them. Never invent IDs.

**12. Site map**

If multi-page: confirm pages — suggest Home, About, one per service, Contact.
Ask about extras (FAQ, portfolio, blog, testimonials page).

If one-page: confirm section order. Suggest: Hero → About → Services →
[optional sections] → Contact. Ask if they want to reorder or remove anything.

### When you are done

Before closing, output a clear asset checklist of every image file the client
needs to place before building starts. Format it like this:

> "Before we start building, make sure these files are in your project:
>
> **Logo**
> - `assets/images/logo/logo.svg`
>
> **Hero**
> - `assets/images/hero/hero.jpg`
>
> **Brand assets** *(if applicable)*
> - `assets/images/brand/motif.svg`
>
> **Services**
> - `assets/images/services/landscaping.jpg`
> - `assets/images/services/garden-design.jpg`
>
> **Gallery** *(if applicable)*
> - `assets/images/gallery/photo-1.jpg` ... *(8 files)*
>
> All these folders already exist in your project — just drop the files in.
> Filenames must match exactly, including the extension."

Only list the assets the client confirmed exist. If something is a placeholder
or none, leave it off the checklist.

Then tell the user:

> "I have everything I need. Let me put together your website brief."

Generate `website-brief.md` using the template below and save it at the root.

---

### website-brief.md template

```markdown
# Website Brief

## Session language
[e.g. English, Spanish, French]

## Website format
[one-page or multi-page]

## Business Identity
- **Business name**: [client value]
- **Tagline / one-sentence description**: [client value]
- **Target audience**: [client value]
- **Differentiator**: [client value]
- **Tone**: [client value]
- **Words to avoid**: [client value]
- **Region / country**: [client value]

## Business Goal
- **Primary visitor action**: [client value]
- **CTA pattern selected**: [from home page template CTA patterns table]

## SEO
- **Primary keyword**: [client value]
- **Secondary keywords**: [client values]
- **Location**: [client value]
- **Domain**: [client value or "not yet defined"]
- **Reference website**: [client value or "none"]

## Branding
- **Primary color**: [hex code or mood]
- **Secondary color**: [hex code or mood]
- **Logo**: [format / shape / icon version: yes or no]
- **Logo file**: [filename and path, or "not yet provided"]
- **Heading font**: [name or mood]
- **Body font**: [name or mood]

## Creative Direction
- **Creative concept**: [one sentence confirmed with the client]
- **Signature motif**: [shape/symbol/object] — source: [logo / brand /
  object / derived from story]
- **Motif file**: [assets/images/brand/filename, or "build with CSS/SVG
  geometry"]
- **Personal story hook**: [client value]
- **Space / material metaphor**: [client value]
- **Shape language**: [e.g. soft arches, rounded corners]
- **Style dials**: Era: classic / modern / balanced · Mood: playful /
  serious / balanced · Richness: minimal / rich / balanced · Temperature:
  warm / cool / balanced · Form: organic / geometric / balanced
- **References**: [URL or name — what specifically the client likes]
- **Anti-references**: [looks, competitors, or patterns to avoid]
- **Imagery style**: [photography / illustration / graphic / type-led]
- **Image mood**: [client value]
- **First impression**: [client value]
- **Design principles**:
  1. [short rule]
  2. [short rule]
  3. [short rule]

## Home page sections
[In order they should appear]
1. Hero
2. About teaser
3. Services
4. [Optional: Testimonials — content details]
5. [Optional: Gallery — number of images, filenames]
6. Closing CTA

## Services / Products
[Repeat for each]

### [Service name]
- **Description**: [client value]
- **Key benefits**: [client value]
- **CTA**: [client value]
- **Image**: [filename and path, or "placeholder", or "none"]
- **Flagship**: yes / no

## Assets
- **Logo**: assets/images/logo/[filename]
- **Hero image**: assets/images/hero/[filename] or [CSS fallback]
- **Service images**:
  - [Service name]: assets/images/services/[filename]
- **Gallery**: assets/images/gallery/ — [count] images: [filenames]
- **Team photos**:
  - [Name, Role]: assets/images/team/[filename]
- **Brand assets**: assets/images/brand/[filename] — [motif, pattern, texture, or reference image]
- **Other**: [any additional]

## Contact
- **Email**: [client value]
- **Phone**: [client value]
- **Address**: [client value or "not provided"]
- **Show address on website**: yes / no
- **Serves**: in person / online / both
- **Preferred contact method**: [client value]
- **Business hours**: [client value or "not provided"]

## Tracking & Marketing Scripts
- **Google Analytics (Measurement ID)**: [G-XXXXXXXXXX or "none"]
- **Hotjar (Site ID)**: [number or "none"]
- **Additional scripts**: [one entry per script, or "none"]
  - [Name] — placement: head / end of body
    ```html
    [exact snippet or ID provided by the client]
    ```

## Site Map
[If multi-page:]
- Home
- About
- [Service: name]
- Contact
- [Other: name]

[If one-page — sections in order:]
- Hero
- About
- Services
- [Optional sections]
- Contact

## Agent notes
[Flags, preferences, edge cases. E.g. "One-page format — use anchor links
for nav. No hero image — use CSS gradient with primary color. Gallery: 8
images. Service descriptions short — apply content expansion strategy."]
```

After saving, tell the user it is ready and remind them to save image files
in the correct `assets/` folders before building.

---

## MODE B — Build a page or section (website-brief.md exists)

Use this mode when `website-brief.md` exists and the user asks you to build.

### Reading order — every time, no exceptions

```
1. framework/INSTRUCTIONS.md
2. framework/guidelines/design-guidelines.md
3. framework/guidelines/creative-direction.md
4. framework/guidelines/content-guidelines.md
5. framework/guidelines/seo-guidelines.md
6. framework/pages/[relevant template]
7. website-brief.md
```

### What to output

Two files per page:
- `[page-name].html`
- `[page-name].css`

File naming:
- Home → `index.html` / `index.css`
- About → `about.html` / `about.css`
- Service → slug from brief (e.g. `web-design.html` / `web-design.css`)
- Contact → `contact.html` / `contact.css`

**If one-page format:** everything goes into `index.html` / `index.css`.
Use the section list from the brief's Site Map to build the page in order.
Use anchor `id` attributes on each section for navigation links.

Build one page (or the full one-page site) per session.

### Tracking and marketing scripts

The brief's **Tracking & Marketing Scripts** section applies to every page
you build or modify, every time. Include Google Analytics (gtag.js) and
Hotjar when an ID is given, plus every additional script, in the placement
the brief specifies. Never drop them when editing an existing page. If the
section is missing from the brief, ask the client once and save the answer
to `website-brief.md`.

### Creative direction

The brief's **Creative Direction** section is a hard requirement, not
inspiration. Apply `framework/guidelines/creative-direction.md` to every page:
use the signature motif in at least three roles, express the style dials as
CSS custom properties, vary the layout rhythm, include one signature section,
and avoid every listed anti-reference. If the brief has no Creative Direction
section, ask the client for the signature shape or object before building.

### Image handling

All image paths must match exactly what is listed in the brief's Assets
section. Do not invent paths. Do not use placeholder image services unless
the brief says so.

If an image is listed as "placeholder" in the brief, output an HTML comment
and a CSS-styled placeholder div with the correct dimensions for that context:
`<!-- Placeholder: hero image — replace with assets/images/hero/[filename] -->`

If an image is listed as "none", do not output an image element or placeholder
for that slot.

### If something is missing

Ask the user one specific question. Never guess. Never ask more than one
question at a time.

If the guidelines define a default, apply it silently and comment in the HTML:
`<!-- Defaulted to guidelines spec: [reason] -->`

---

## General rules — both modes

- Never invent client content. If it is not in the brief, ask.
- Never duplicate content across pages unless the template explicitly allows it.
- The `lang` attribute on `<html>` must match the session language in the brief.
- Framework files are the source of truth for rules. The brief is the source
  of truth for client data. When they conflict, ask before proceeding.
