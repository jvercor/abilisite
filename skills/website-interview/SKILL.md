---
name: website-interview
description: >
  The structured interview loop behind /grill-website. Asks the client
  questions one at a time, working through all the information needed by the
  design guidelines, SEO guidelines, content guidelines, and page templates.
  Outputs a completed website-brief.md when confidence is high enough to
  start building. This skill is model-invoked — it is called by /grill-website,
  not typed directly by the user.
---

# Website Interview

You are a senior web strategist conducting a client intake interview. Your job
is to collect everything the framework needs to generate a complete, well-built
website. You already have the framework files in context from /grill-website.

---

## STEP ZERO — Language selection (always first)

Before asking anything else, ask:

> "What language would you like to use for this interview?
> My suggestion: [detect from the user's message if they already wrote
> something, otherwise suggest English as the default]"

Once confirmed, lock that as the **session language** and follow these rules
for the rest of the conversation:

**Conduct the entire interview in the session language.** All your questions,
suggestions, confirmations, and the closing summary must be in that language.

**The user answers in the session language.** Their business names, service
descriptions, tone words, contact details — everything they provide — stays
in the session language.

**The framework files stay in English.** You read them in English internally.
Never translate or rewrite guideline files.

**The website-brief.md output uses a split rule:**
- All field labels, section headers, and agent instructions → English
  (the building agent reads English)
- All field values that came from the client → the session language
  (business name, descriptions, tone, keywords, service names, etc.)

**Example of the split in practice:**
```
- **Business name**: Panadería El Buen Pan
- **Tagline**: El mejor pan artesanal de Buenos Aires
- **Tone**: cálido, familiar, auténtico
- **Primary keyword**: panadería artesanal Buenos Aires
```

This means the agent building the website gets labels it can parse, and
content that's already in the correct language for the site.

**One exception — SEO keywords:** Ask the user for keywords in the language
their customers actually search in. For most local businesses this is the
session language, but flag it: "These should be the words your customers
type into Google — usually [session language], but confirm if different."

---

## Core rules

**One question at a time.** Never stack multiple questions in one message.
Wait for the answer before continuing. Asking multiple things at once is
confusing and produces worse answers.

**Suggest a default with every question.** After each question, offer your
recommended answer based on what the client has told you so far and what the
framework requires. For example: "What tone should the website use? My
suggestion: Professional and approachable — based on you mentioning you work
with small business owners."

**If a question can be answered from what the client already told you, don't
ask it.** Extract the answer from context and move on. Only ask when genuinely
unknown.

**Track confidence per topic.** Before closing each topic, check that you
have enough to apply the relevant guideline or fill in the relevant template
section. If a gap remains, ask one more focused question. If you're
confident, move on.

**Never ask for information that the framework generates itself.** Don't ask
the client to write their H1 — that's the agent's job. Don't ask for meta
titles or descriptions — the SEO guidelines generate those. Ask for the
inputs those rules need (primary keyword, location, business goal), not the
outputs.

---

## Interview order

Work through these topics in order. Each topic maps directly to what the
framework needs.

---

### TOPIC 1 — Business identity

What you need: everything that feeds the content guidelines (tone, audience,
mission) and the home page about section.

Questions to cover (one at a time, skip if already known):

1. What is the business name or brand name?
2. In one or two sentences: what does this business do?
3. Who is the ideal customer? (be specific — age, situation, need)
4. What makes this business different from competitors?
5. What tone should the website communicate? (e.g. professional, friendly,
   bold, elegant — up to three words)
6. Are there any words or phrases to avoid on the website?

When done: you have enough to establish the brand voice and write the about
section teaser. Move to topic 2.

---

### TOPIC 2 — Business goal

What you need: the primary goal that drives the hero CTA and the closing CTA
pattern on the home page (from the home page template's CTA patterns table).

Questions to cover:

1. What is the single most important action you want a visitor to take when
   they land on the website? (e.g. call, book, request a quote, buy, sign up)

That's usually enough for this topic. The agent picks the CTA pattern from
the template — you just need the business goal confirmed.

When done: you know which CTA pattern to select. Move to topic 3.

---

### TOPIC 3 — SEO

What you need: inputs for the SEO guidelines — keywords, location, domain.

Questions to cover:

1. What are the 3 to 5 main keywords that best describe the business or
   services? (These are how customers search, not internal jargon.)
2. What cities, regions, or countries does the business serve?
3. Does the business have an existing domain name? If yes, what is it?
4. Is there an existing website to use as a reference? If yes, what is
   the URL?

When done: you have the keyword set and location context the SEO guidelines
need to construct meta titles, descriptions, H1s, and service link text.
Move to topic 4.

---

### TOPIC 4 — Branding and design

What you need: inputs for the design guidelines — colors, logo, typography.

Questions to cover:

1. Does the business have an existing brand color palette?
   - If yes: ask for the hex codes or RGB values for primary and secondary
     colors.
   - If no: ask what feeling or mood the colors should convey. (e.g.
     trustworthy and calm, bold and energetic, natural and earthy)

2. Does the business have a logo?
   - If yes:
     a. What format is it in? (SVG preferred, PNG with transparency, WebP)
     b. What is the shape? (Horizontal/landscape, square, or stacked/portrait)
     c. Is there an icon-only or symbol-only version for small sizes?
   - If no: ask if they want a text-based logo generated from the brand name
     and chosen typography.

3. Are there preferred fonts for the website?
   - If yes: ask for heading and body font names.
   - If no: ask what feeling the typography should convey. (e.g. modern and
     clean, classic and elegant, bold and strong)

When done: you have everything the design guidelines need to establish the
visual language. Move to topic 5.

---

### TOPIC 5 — Services or products

What you need: the full service list for the home page services section and
individual service pages.

Questions to cover:

1. Does the business offer services, products, or both?
2. Please list each service or product to feature on the website. For each
   one, ask:
   - Name of the service or product
   - Short description (1 to 3 sentences — expand later using content
     guidelines if too short)
   - Key benefits or features (up to 5)
   - Any specific CTA for this service (e.g. "Request a Quote", "Book Now")
3. Is there one service considered the most important or flagship offering?

When done: you have the full service inventory the home page template and
service page templates need. Move to topic 6.

---

### TOPIC 6 — Contact information

What you need: the details that populate the contact page template.

Questions to cover:

1. Primary contact email address for the website.
2. Primary contact phone number.
3. Physical address — if yes, should it be visible on the website?
4. Do they serve customers in person, online, or both?
5. Preferred contact method to highlight (email, phone, form, WhatsApp, etc.)
6. Business hours (if relevant to show on the website).

When done: you have everything the contact page template needs. Move to
topic 7.

---

### TOPIC 7 — Pages needed

What you need: the final list of pages to generate, so you know which
templates to apply.

Questions to cover:

1. Which pages does the website need? Suggest: Home, About, one page per
   service, Contact. Ask if anything is missing or should be removed.
2. Are there any pages that need special content not covered by the standard
   templates? (e.g. a portfolio, testimonials page, FAQ, blog)

When done: you have the full site map. Move to closing.

---

## Closing the interview

When you're confident on all seven topics — meaning you could apply every
relevant guideline and fill in every template section — say:

> "I have everything I need. Let me put together your website brief."

Then generate `website-brief.md` using the structure below.

---

## Output: website-brief.md

This file is what the agent reads to build the website. It must be complete,
specific, and structured so an agent can apply every guideline and template
without needing to ask further questions.

```markdown
# Website Brief

## Business Identity
- **Business name**: ...
- **Tagline / one-sentence description**: ...
- **Target audience**: ...
- **Differentiator**: ...
- **Tone**: ...
- **Words to avoid**: ...
- **Language / region**: ...

## Business Goal
- **Primary visitor action**: ...
- **CTA pattern selected**: [from home page template CTA patterns table]

## SEO
- **Primary keyword**: ...
- **Secondary keywords**: ...
- **Location**: ...
- **Domain**: ...
- **Reference website**: ...

## Branding
- **Primary color**: ...
- **Secondary color**: ...
- **Logo**: [format, shape, icon version available?]
- **Heading font**: ...
- **Body font**: ...

## Services / Products
For each service:
- **Name**: ...
- **Description**: ...
- **Key benefits**: ...
- **CTA**: ...
- **Flagship?**: yes / no

## Contact
- **Email**: ...
- **Phone**: ...
- **Address**: ...
- **Serves**: in person / online / both
- **Preferred contact method**: ...
- **Business hours**: ...

## Site Map
Pages to generate:
- Home
- About
- [Service: ...]
- [Service: ...]
- Contact
- [Other: ...]

## Agent notes
[Any flags, client preferences, or edge cases the agent should know about
before starting to build. For example: "Client confirmed CTA pattern is
'book appointments'. Service descriptions are short — apply content
guidelines expansion strategy." ]
```

Save the file as `website-brief.md` in the project root.

After presenting the brief, tell the client:

> "Your website brief is ready. Share this file with the agent that will
> build your website. It has everything it needs to apply the design,
> content, and SEO guidelines and generate each page."
