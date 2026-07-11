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

**6. Home page sections**

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

**7. Services or products**
- Services, products, or both?
- For each: name, description (1–3 sentences), key benefits (up to 5), CTA
- Which is the flagship?

**8. Images and assets**

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
- **Any other images** the client wants to include

**Rule:** Never assume or invent image paths. If an image is needed and the
client hasn't confirmed it exists, always ask. Never use placeholder image
services unless explicitly requested.

When confirming a filename with the client, always mention that the folder
already exists in the project — they just need to drop the file in. Example:
"Save it to `assets/images/hero/` — that folder is already created in the
project, just drop your file in there."

**9. Contact information**
- Primary email
- Primary phone
- Physical address (and whether to show it)
- Serves in person, online, or both
- Preferred contact method
- Business hours (if relevant)

**10. Site map**

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
- **Other**: [any additional]

## Contact
- **Email**: [client value]
- **Phone**: [client value]
- **Address**: [client value or "not provided"]
- **Show address on website**: yes / no
- **Serves**: in person / online / both
- **Preferred contact method**: [client value]
- **Business hours**: [client value or "not provided"]

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
3. framework/guidelines/content-guidelines.md
4. framework/guidelines/seo-guidelines.md
5. framework/pages/[relevant template]
6. website-brief.md
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
