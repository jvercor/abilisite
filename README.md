# Website Generation Framework

A markdown-based framework for building client websites with AI agents.
Define the rules once. Interview any client. Generate consistent, SEO-optimized
HTML pages every time.

---

## How it works

This framework has two parts:

**The interview** — an AI skill that asks the client structured questions and
produces a `website-brief.md` with all the information needed to build the
site.

**The builder** — an AI agent that reads the framework guidelines and the
client brief, then generates one HTML + CSS page per session.

You run the interview once per client. You run the builder once per page.

---

## Repository structure

```
/
├── README.md                  ← you are here
├── website-brief.md           ← generated per client, not committed to repo
│
├── framework/
│   ├── INSTRUCTIONS.md        ← agent reads this before building any page
│   ├── guidelines/
│   │   ├── design-guidelines.md
│   │   ├── content-guidelines.md
│   │   └── seo-guidelines.md
│   └── pages/
│       ├── home.md
│       ├── about.md
│       ├── service.md
│       └── contact.md
│
└── skills/
    ├── grill-website/
    │   └── SKILL.md
    └── website-interview/
        └── SKILL.md
```

---

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/website-framework.git
cd website-framework
```

### 2. Open a new Claude project

Create a new project in Claude and upload or sync the repository files.
The `framework/` and `skills/` folders must be available to the agent.

### 3. Run the client interview

Start a new chat inside the project and type:

```
/grill-website
```

The agent will ask you which language you want to use, then walk you through
a structured interview covering the business, branding, SEO, services, and
pages needed. At the end it generates a `website-brief.md` file.

Save that file at the root of your project.

### 4. Build a page

Start a new chat inside the same project and tell the agent which page to
build:

```
Build the home page using the website brief.
```

The agent reads `INSTRUCTIONS.md`, the relevant guidelines, the page
template, and the `website-brief.md`, then outputs the HTML and CSS files
for that page.

Repeat for each page in the site map.

---

## Adding a new client

1. Start a new Claude project (or clear the current `website-brief.md`)
2. Run `/grill-website` again
3. Save the new `website-brief.md`
4. Build pages as above

The framework files never change between clients. Only `website-brief.md`
changes.

---

## Adding new page types

To support a new type of page (e.g. a portfolio page or FAQ page):

1. Create a new template file in `framework/pages/` following the same
   structure as the existing templates
2. Add the page type to the site map section of `website-interview/SKILL.md`
   so the interview knows to ask about it
3. Reference the new template in `INSTRUCTIONS.md` under the reading order

---

## Contributing

Pull requests welcome. If you add a new guideline or page template, make
sure `INSTRUCTIONS.md` is updated to reference it.
