# Framework Instructions

This file is written for the agent that builds website pages. Read it
completely before touching any other file or writing any code.

---

## What this framework is

A set of rules and templates that tell you how to build a website, one page
at a time, for a specific client. Every client project provides a
`website-brief.md` at the root — that file contains all the client-specific
data you need. The framework files tell you how to apply that data.

---

## Your role

You are a page-building agent. You are responsible for one page per session.
You receive:

1. This `INSTRUCTIONS.md`
2. The `website-brief.md` for the current client
3. A request specifying which page to build (e.g. "build the home page")

You output two files:
- `[page-name].html` — the full page markup
- `[page-name].css` — all styles for that page

No frameworks, no build tools, no JavaScript unless the brief explicitly
requires it. Clean, valid HTML5 and CSS3 only.

---

## Reading order — follow this every time

Read the files in this exact order before writing a single line of code.
Skipping steps will produce output that violates the client's brand or breaks
SEO rules.

### Step 1 — Read the guidelines (all four, every time)

```
/framework/guidelines/design-guidelines.md
/framework/guidelines/creative-direction.md
/framework/guidelines/content-guidelines.md
/framework/guidelines/seo-guidelines.md
```

These apply to every page. Read them fully. They define:
- Colors, typography, spacing, logo rules, responsive behavior
- How to turn the brief's Creative Direction (motif, style dials, anti-references) into a distinctive, non-generic design
- Writing tone, CTA copy rules, content expansion strategy
- Meta title and description rules, H1/H2 keyword placement, alt text

### Step 2 — Read the relevant page template

```
/framework/pages/home.md        → when building the Home page
/framework/pages/about.md       → when building the About page
/framework/pages/service.md     → when building any Service page
/framework/pages/contact.md     → when building the Contact page
```

The page template defines the exact section order, what each section must
contain, and any page-specific SEO rules. Treat it as a strict spec, not
a suggestion.

### Step 3 — Read the client brief

```
/website-brief.md
```

This is the client's data. Use it to populate every variable the guidelines
and templates require — business name, colors, keywords, services, tone,
contact details, and so on.

Cross-reference as you go: if the design guidelines say "use the primary
color for buttons" and the brief says "primary color: #2C5F2E", use
#2C5F2E for buttons.

The brief's **Creative Direction** section is a hard requirement. Apply it
as described in `creative-direction.md`; accessibility and SEO rules in the
other guidelines still take precedence.

---

## How to handle missing information

The brief should contain everything you need. If something is genuinely
missing or ambiguous — for example the brief says "logo: TBD" or a service
has no description — do the following:

1. Do not guess or invent content.
2. Pause and ask the client one specific question.
3. Wait for the answer before continuing.
4. Do not ask more than one question at a time.

If something is missing but has a clear default in the guidelines (e.g. no
font specified → use the guidelines default), apply the default silently and
note it in a comment in the HTML: `<!-- Font defaulted to guidelines spec: no client font provided -->`.

Do not ask the client about things the guidelines already define.

---

## Output rules

### HTML file
- Valid HTML5 with `<!DOCTYPE html>`
- Language attribute on `<html>` must match the brief's language field
- `<head>` must include:
  - `<meta charset="UTF-8">`
  - `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
  - `<title>` — follow SEO guidelines for character count and keyword placement
  - `<meta name="description">` — follow SEO guidelines
  - `<link rel="canonical">` — use the domain from the brief
  - Open Graph tags: `og:title`, `og:description`, `og:url`, `og:type`
  - `<link rel="stylesheet" href="[page-name].css">`
- One `<h1>` per page — no exceptions
- All images must have descriptive `alt` attributes
- All internal links must use descriptive anchor text — never "click here"
- Logo in the nav must link to the home page

### CSS file
- Mobile-first: base styles for mobile, then `@media (min-width: 768px)`
  for tablet, `@media (min-width: 1200px)` for desktop
- Use CSS custom properties (variables) for all colors and fonts defined
  in the brief, declared in `:root`
- No inline styles in the HTML
- No `!important` unless absolutely unavoidable
- Class names must be descriptive and in kebab-case

### File naming
- Home page: `index.html` / `index.css`
- About page: `about.html` / `about.css`
- Service pages: use the service slug from the brief (e.g.
  `residential-landscaping.html` / `residential-landscaping.css`)
- Contact page: `contact.html` / `contact.css`

---

## Quality checklist

Before delivering your output, verify every item on this list:

**SEO**
- [ ] `<title>` is 50–60 characters and includes the primary keyword
- [ ] Meta description is 150–160 characters
- [ ] H1 is present, unique, and includes the primary keyword
- [ ] All images have alt text
- [ ] Canonical tag is present
- [ ] Open Graph tags are present
- [ ] Internal links use descriptive anchor text

**Design**
- [ ] CSS custom properties match the client's colors from the brief
- [ ] Typography follows the design guidelines (heading font, body font,
  scale)
- [ ] Logo is placed correctly in the nav based on its shape (see
  design guidelines logo section)
- [ ] Logo links to the home page
- [ ] Layout is mobile-first and tested at 375px, 768px, and 1200px
- [ ] Creative direction quality gate in `creative-direction.md` passes
  (motif in 3+ roles, style dials in `:root`, varied layout rhythm, one
  signature section, anti-references avoided)

**Content**
- [ ] Tone matches the brief's tone field
- [ ] No content is duplicated from other pages (see page template notes)
- [ ] CTAs use action-oriented, specific text
- [ ] Any short client descriptions have been expanded using the content
  guidelines expansion strategy

**Code**
- [ ] HTML validates (no unclosed tags, no missing attributes)
- [ ] No inline styles
- [ ] File is named correctly per the naming rules above

---

## What you do not do

- Do not build more than one page per session
- Do not create a build system, bundler, or package.json
- Do not use CSS frameworks (Bootstrap, Tailwind, etc.)
- Do not add JavaScript unless the brief explicitly requires it
- Do not invent client content — if it's not in the brief, ask
- Do not fall back on generic layouts or default styling when the brief's Creative Direction gives you a specific alternative
- Do not reuse content across pages unless the template explicitly allows it
