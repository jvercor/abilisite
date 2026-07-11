# SEO Guidelines

## Overview
This document defines the SEO rules and best practices that the agent must follow when generating every page of the website. These guidelines apply universally across all pages unless a page-specific template explicitly overrides a rule. The agent must treat these rules as mandatory unless the client explicitly requests an override after being warned of the SEO consequences.

---

## Meta Title

### Rules
- **Length**: Between 50 and 60 characters (including spaces). Never exceed 60 characters.
- **Structure**: Primary Keyword + Secondary Descriptor + Brand Name
  - Example: `Landscaping Services in Denver | Green Yard Co.`
- The primary keyword should appear as close to the beginning of the title as possible
- Each page must have a **unique meta title**—never reuse the same title across pages
- Avoid keyword stuffing—the title should read naturally
- Always include the brand name, typically at the end separated by a pipe `|` or dash `–`

### Per-Page Guidance
- **Home**: Focus on the primary business keyword and location if applicable
- **About**: Focus on the brand name and a trust-building descriptor
- **Service pages**: Focus on the specific service name and location if applicable
- **Contact**: Keep simple—"Contact Us | Brand Name" is acceptable

---

## Meta Description

### Rules
- **Length**: Between 150 and 160 characters (including spaces). Never exceed 160 characters.
- Should summarize the page content clearly and compellingly
- Must include the primary keyword naturally within the text
- Should include a soft call to action where appropriate *(e.g., "Learn more", "Get in touch", "Discover our services")*
- Each page must have a **unique meta description**—never reuse across pages
- Avoid keyword stuffing—write for humans first, search engines second
- Do not use quotes inside meta descriptions as they can break HTML attributes

### Per-Page Guidance
- **Home**: Describe the overall business value proposition and primary service
- **About**: Describe the company story, mission, or values
- **Service pages**: Describe the specific service and its key benefit to the client
- **Contact**: Invite the visitor to reach out and mention preferred contact method

---

## Heading Structure

### H1 — MANDATORY: One Per Page
- Every page must have exactly one H1 tag. This is a strict SEO requirement.
- The H1 must include the primary keyword for that page
- The H1 should clearly communicate what the page is about
- > ⚠️ **Agent Warning**: If the client requests more than one H1 on any page, the agent must warn: *"Using more than one H1 tag per page violates SEO best practices and will negatively impact your search engine rankings. Only one H1 is allowed per page."* Do not add a second H1 unless the client explicitly overrides after being warned.

### H2 — Section Headers
- Use H2 tags to introduce major sections within a page
- H2s should support the page's primary topic and naturally include secondary keywords where appropriate
- Do not skip heading levels (e.g., do not jump from H1 to H4)

### H3 — Subsection Headers
- Use H3 tags for subsections within H2 sections
- H3s can include long-tail keywords naturally if relevant

### General Heading Rules
- Headings should always read naturally—never stuff keywords awkwardly
- Maintain a clear, logical hierarchy throughout the page

---

## Keywords

### Keyword Usage Principles
- Every page should have one clearly defined **primary keyword** and up to three **secondary keywords**
- The primary keyword should appear in:
  - The meta title
  - The meta description
  - The H1
  - The first paragraph of body content
  - At least one H2 (where natural)
  - The page URL slug
- Secondary keywords should be distributed naturally throughout the body content
- **Keyword density**: Aim for 1% to 2% keyword density for the primary keyword. Avoid over-optimization.
- Keywords should always read naturally within the content—never forced or repetitive

### Location-Based Keywords
- If the business serves a specific geographic area, include location-based keywords where relevant
- Example: "plumbing services in Austin" rather than just "plumbing services"
- Location keywords should appear in the meta title, meta description, H1 (where natural), and body content

---

## URL Structure

### Rules
- URLs should be short, descriptive, and lowercase
- Use hyphens `-` to separate words—never underscores or spaces
- URLs should include the primary keyword for the page
- Avoid unnecessary words like "and", "the", "of" in URLs where possible
- Never use auto-generated IDs or meaningless strings in URLs

### Examples
- Home: `/` (root)
- About: `/about`
- Services listing: `/services`
- Individual service: `/services/service-name`
- Contact: `/contact`

---

## Image SEO

### Alt Text — MANDATORY
- Every image must have a descriptive `alt` attribute
- Alt text should describe the image content naturally and include a relevant keyword where it fits organically
- Never keyword-stuff alt text
- If the image is purely decorative, use `alt=""`
- If the client does not provide alt text, the agent must generate it based on the image context and page content
- Maximum recommended alt text length: 125 characters

### File Names
- Image file names should be descriptive and keyword-relevant before uploading
- Use hyphens to separate words
- Example: `landscaping-services-denver.jpg` not `IMG_0032.jpg`

### Image Size and Performance
- Images should be compressed and optimized for web before use
- Large unoptimized images negatively impact page speed, which is a ranking factor
- Recommend WebP format for best performance where supported

---

## Internal Linking

### Rules
- Every page should link to at least one other relevant page on the website
- Service preview sections on the home page must link to their corresponding service detail pages
- The navigation menu counts as internal linking but should be supplemented with contextual links within page content
- Use descriptive anchor text—never use "click here" or "read more" alone as anchor text
  - Good: "Learn more about our landscaping services"
  - Bad: "Click here" or "Read more"
- The about page should link to the contact page
- Each service page should link to the contact page with a relevant CTA

---

## Page Speed Considerations

### Agent Recommendations
- Recommend that the client use compressed images
- Avoid embedding large videos directly—use YouTube or Vimeo embeds instead
- Minimize the use of heavy third-party scripts
- These are recommendations only—the agent cannot control hosting or server configuration

---

## Structured Data (Schema Markup) — OPTIONAL BUT RECOMMENDED

### LocalBusiness Schema
- If the business has a physical location or serves a specific area, recommend adding LocalBusiness schema markup
- Key fields to include:
  - Business name
  - Address
  - Phone number
  - Business hours
  - URL
  - Description

### Service Schema
- For each service page, recommend adding Service schema markup
- Key fields: service name, description, provider (business name), area served

> **Agent Note**: Inform the client that schema markup helps search engines better understand the website content and can improve visibility in search results. Ask if they would like it included.

---

## Open Graph and Social Meta Tags — RECOMMENDED

### Rules
- Every page should include Open Graph meta tags for better appearance when shared on social media
- Required Open Graph tags:
  - `og:title` — Can match the meta title
  - `og:description` — Can match the meta description
  - `og:image` — Should be a high-quality image representing the page (minimum 1200x630px recommended)
  - `og:url` — The canonical URL of the page
  - `og:type` — Typically `website` for most pages

---

## Canonical Tags

### Rules
- Every page must include a canonical tag pointing to its own URL to avoid duplicate content issues
- Example: `<link rel="canonical" href="https://www.yourdomain.com/about" />`

---

## Agent Checklist — Before Finalizing Any Page

The agent must verify the following before considering a page complete:

- [ ] Meta title is between 50 and 60 characters and includes the primary keyword
- [ ] Meta description is between 150 and 160 characters and includes the primary keyword
- [ ] Exactly one H1 exists on the page and includes the primary keyword
- [ ] H2s and H3s follow a logical hierarchy
- [ ] Primary keyword appears in the first paragraph of body content
- [ ] All images have alt text
- [ ] At least one internal link exists within the page content
- [ ] URL slug is short, lowercase, and keyword-relevant
- [ ] Canonical tag is present
- [ ] Open Graph tags are present
