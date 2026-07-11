# Abilisite

A markdown-based framework for building client websites with AI agents — works
with Claude, GitHub Copilot, Cursor, Gemini CLI, and any other AI tool that
can read files.

Define the rules once. Interview any client. Build consistent, SEO-optimized
pages every time.

---

## How it works

Abilisite has two steps:

**1. Interview** — an AI agent asks the client structured questions about their
business, brand, SEO, services, and pages needed. The result is a
`website-brief.md` file that captures everything.

**2. Build** — a separate AI agent reads the brief, the design guidelines, the
SEO rules, and the relevant page template, then outputs clean HTML and CSS for
that page. One page per session.

The framework files never change between clients. Only `website-brief.md`
changes.

---

## Works with any AI tool

Abilisite is tool-agnostic. The `AGENT.md` file at the root tells any AI agent
how to run the interview and how to build pages — no setup required beyond
pointing your agent at the project files.

| Tool | How to use |
|---|---|
| Claude (claude.ai) | Use the included `/grill-website` skill for the best interview experience, or use `AGENT.md` directly |
| GitHub Copilot | Point Copilot at `AGENT.md` to start |
| Cursor | Open the project and reference `AGENT.md` in your prompt |
| Gemini CLI | Point the agent at `AGENT.md` |
| Any other AI tool | Same — `AGENT.md` is the universal entry point |

---

## Installation

No package manager needed. Clone the repo directly into your project folder.

**Starting a new project:**

```bash
git clone https://github.com/jvercor/abilisite.git my-client-project
cd my-client-project
```

**Adding to an existing project:**

```bash
cd your-existing-project
git remote add abilisite https://github.com/jvercor/abilisite.git
git fetch abilisite
git merge abilisite/main --allow-unrelated-histories
```

**Getting updates when the framework improves:**

```bash
git pull origin main
```

---

## Repository structure

```
/
├── README.md                     ← you are here
├── AGENT.md                      ← universal entry point for any AI agent
├── website-brief.md              ← generated per client (add to .gitignore)
│
├── framework/
│   ├── INSTRUCTIONS.md           ← building agent reads this before every page
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
├── assets/                       ← client images and media go here
│   └── images/
│       ├── logo/                 ← logo files (SVG, PNG)
│       ├── hero/                 ← hero section background or feature image
│       ├── services/             ← one image per service or product
│       ├── gallery/              ← gallery photos if the site has a gallery
│       └── team/                 ← team member photos for the About page
│
└── skills/                       ← Claude-specific enhancement (optional)
    ├── grill-website/
    │   └── SKILL.md
    └── website-interview/
        └── SKILL.md
```

Each `assets/images/` subfolder contains a `.gitkeep` file so the folder
structure is preserved in Git even before any images are added. You can
delete these files once you add real images — or leave them, they do nothing.

---

## Adding client images

The interview will tell you exactly which files are needed and where to put
them. As a general rule:

| Image type | Folder |
|---|---|
| Logo | `assets/images/logo/` |
| Hero background or feature image | `assets/images/hero/` |
| Service or product photos | `assets/images/services/` |
| Gallery photos | `assets/images/gallery/` |
| Team member photos | `assets/images/team/` |

**Important:** the building agent references image paths exactly as recorded
in `website-brief.md`. Make sure filenames match exactly — including the
extension and capitalisation. If the brief says `assets/images/hero/hero.jpg`,
the file must be named `hero.jpg`, not `Hero.JPG` or `hero.jpeg`.

The interview produces a full asset checklist at the end. Place all files
in the correct folders before asking the agent to start building.

---

## Quickstart

### Using any AI tool

Open your project in your preferred AI tool and say:

```
Read AGENT.md and start the client interview.
```

The agent will ask which language to use, then walk through seven topics:
business identity, business goal, SEO, branding, services, contact info, and
pages needed. At the end it saves `website-brief.md`.

To build a page:

```
Read AGENT.md and build the home page using the website brief.
```

### Using Claude (claude.ai)

For the best experience, use the included skills:

1. Create a new Claude project and add the framework files to it
2. Start a new chat and type `/grill-website`
3. The agent asks one question at a time, suggests defaults, and generates
   `website-brief.md` when done
4. Start a new chat and say `Build the home page using the website brief`

Repeat step 4 for each page in the site map.

---

## .gitignore recommendation

Add these to your project's `.gitignore` so client-specific files don't mix
with the framework:

```
website-brief.md
*.html
*.css
```

---

## Adding a new client

1. Delete or archive the previous `website-brief.md`
2. Run the interview again
3. Build pages from the new brief

The framework files stay the same across every client.

---

## Extending the framework

**New page type** (e.g. portfolio, FAQ, blog):
1. Create a template in `framework/pages/` following the same structure as
   the existing ones
2. Add it to the site map topic in `skills/website-interview/SKILL.md` and
   in `AGENT.md`
3. Reference it in `framework/INSTRUCTIONS.md`

**New guideline** (e.g. accessibility rules, animation principles):
1. Create a new file in `framework/guidelines/`
2. Add it to the reading order in `framework/INSTRUCTIONS.md` and `AGENT.md`

---

## Contributing

Pull requests are welcome. If you improve a guideline, fix a template, or add
a new page type, please update `INSTRUCTIONS.md` and `AGENT.md` to reflect
the change so both Claude and non-Claude users benefit.

Open an issue first if you want to discuss a bigger change before building it.
