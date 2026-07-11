# AGENT.md

This file is written for any AI agent working on this project, regardless of
the tool you are running in. Read it completely before doing anything else.

---

## What this project is

A framework for building client websites. It defines rules for design, content,
and SEO that every page must follow, and templates that define the structure of
each page type. Your job is either to interview a client and produce a brief,
or to read a completed brief and build a page.

---

## Two modes

You will always be in one of two modes. Read which one applies and follow
only that section.

---

## MODE A — Interview (no website-brief.md exists yet)

Use this mode when there is no `website-brief.md` file at the root of the
project, or when the user asks you to start a new client project.

Your goal is to collect all the information needed to build the website and
save it as `website-brief.md`. You do this through a structured conversation
with the user.

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

You need to understand what each file requires before you can ask the right
questions. Do not skip this step.

### Language

Your first message to the user must ask which language they want to use for
the interview. Detect it from their first message if they already wrote
something in a specific language, and suggest that as the default.

Once confirmed, conduct the entire interview in that language. All your
questions, suggestions, and confirmations must be in that language. The user's
answers stay in that language. The `website-brief.md` field labels stay in
English so the building agent can parse them. Field values that came from the
client go in the session language.

### Interview rules

- Ask one question at a time. Wait for the answer before continuing.
- After every question, suggest a default answer based on what you know so
  far. The user can confirm or override it.
- If you can infer an answer from something the user already told you, do not
  ask — extract it and move on.
- Never ask the user to write their own H1, meta title, or meta description.
  Those are generated from the brief. Ask for the inputs those rules need
  (primary keyword, location, business goal), not the outputs.
- Track what you still need. Before moving to the next topic, check that you
  have enough to apply the relevant guideline or fill in the relevant template
  section.

### Topics to cover — in this order

Work through each topic fully before moving to the next.

**1. Business identity**
- Business name or brand name
- What the business does (one or two sentences)
- Ideal customer (specific — age, situation, need)
- What makes the business different from competitors
- Tone for the website (up to three words — e.g. professional, friendly, bold)
- Words or phrases to avoid

**2. Business goal**
- The single most important action a visitor should take
  (call, book, request a quote, buy, sign up, etc.)

**3. SEO**
- 3 to 5 main keywords (how customers search, not internal jargon)
- Cities, regions, or countries served
- Existing domain name (if any)
- Existing website URL to use as reference (if any)
- Confirm: are these keywords in the language customers search in?

**4. Branding and design**
- Existing brand colors? If yes: hex codes. If no: mood or feeling for colors.
- Logo? If yes: file format, shape (horizontal / square / stacked), icon-only
  version available? If no: text-based logo from brand name?
- Preferred fonts? If yes: heading and body font names. If no: feeling for
  typography.

**5. Services or products**
- Does the business offer services, products, or both?
- For each service or product:
  - Name
  - Short description (1 to 3 sentences)
  - Key benefits or features (up to 5)
  - Specific CTA for this service (if different from the main CTA)
- Which service is the flagship or most important?

**6. Contact information**
- Primary contact email
- Primary contact phone number
- Physical address (and whether to show it on the website)
- Serves customers in person, online, or both
- Preferred contact method to highlight
- Business hours (if relevant)

**7. Pages needed**
- Confirm the site map. Suggest: Home, About, one page per service, Contact.
- Any additional pages needed? (portfolio, FAQ, testimonials, blog, etc.)

### When you are done

When you are confident on all seven topics, tell the user:

> "I have everything I need. Let me put together your website brief."

Then generate `website-brief.md` using the template below and save it at the
root of the project.

---

### website-brief.md template

```markdown
# Website Brief

## Session language
[Language used in this interview — e.g. English, Spanish, French]

## Business Identity
- **Business name**: [client value in session language]
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
- **Primary keyword**: [client value in search language]
- **Secondary keywords**: [client values]
- **Location**: [client value]
- **Domain**: [client value or "not yet defined"]
- **Reference website**: [client value or "none"]

## Branding
- **Primary color**: [hex code or mood description]
- **Secondary color**: [hex code or mood description]
- **Logo**: [format / shape / icon version: yes or no]
- **Heading font**: [name or mood description]
- **Body font**: [name or mood description]

## Services / Products
[Repeat this block for each service or product]

### [Service name]
- **Description**: [client value]
- **Key benefits**: [client value]
- **CTA**: [client value]
- **Flagship**: yes / no

## Contact
- **Email**: [client value]
- **Phone**: [client value]
- **Address**: [client value or "not provided"]
- **Show address on website**: yes / no
- **Serves**: in person / online / both
- **Preferred contact method**: [client value]
- **Business hours**: [client value or "not provided"]

## Site Map
- Home
- About
- [Service: name]
- [Service: name]
- Contact
- [Other: name]

## Agent notes
[Flags, client preferences, or edge cases the building agent should know.
Examples: "Client confirmed CTA pattern is book appointments. Service
descriptions are short — apply content guidelines expansion strategy.
Logo is square format."]
```

After saving the file, tell the user it is ready and that they can now ask
you (or another agent) to build any page.

---

## MODE B — Build a page (website-brief.md exists)

Use this mode when a `website-brief.md` exists at the root and the user asks
you to build a specific page.

### Reading order — follow every time

Read in this exact order before writing any code:

```
1. framework/INSTRUCTIONS.md
2. framework/guidelines/design-guidelines.md
3. framework/guidelines/content-guidelines.md
4. framework/guidelines/seo-guidelines.md
5. framework/pages/[relevant template for the page being built]
6. website-brief.md
```

Do not skip steps. Do not reorder. The guidelines define the rules. The
template defines the structure. The brief provides the client data.

### What to output

For each page, produce two files:

- `[page-name].html` — full page markup
- `[page-name].css` — all styles for that page

File naming:
- Home → `index.html` / `index.css`
- About → `about.html` / `about.css`
- Service pages → slug from the brief (e.g. `web-design.html` / `web-design.css`)
- Contact → `contact.html` / `contact.css`

Build one page per session. Do not attempt to build the entire site at once.

### If something is missing

If the brief is missing information you need and the guidelines do not provide
a default, ask the user one specific question. Do not guess. Do not ask more
than one question at a time.

If the guidelines already define a default for something the brief does not
specify, apply the default silently and leave a comment in the HTML:
`<!-- Defaulted to guidelines spec: [reason] -->`

---

## General rules that apply in both modes

- Never invent client content. If it is not in the brief, ask.
- Never duplicate content across pages unless the template explicitly allows it.
- SEO keywords must reflect how customers actually search — not internal
  language or generic terms.
- The website language (set in the brief's session language field) must match
  the `lang` attribute on the HTML `<html>` tag and all user-facing content.
- Framework files are the source of truth for rules. The brief is the source
  of truth for client data. When they conflict, ask the user before proceeding.
