# Design Guidelines

## Overview
This document establishes the visual and design principles that guide all website pages generated through this framework. These guidelines ensure consistency, accessibility, and professional presentation across all pages while remaining flexible enough to accommodate client branding.

## Color Usage Principles

### Color Roles
- **Primary Color**: Used for main call-to-action buttons, key links, and primary UI elements. Should convey the brand's core identity.
- **Secondary Color**: Used for accents, secondary buttons, hover states, and supporting elements.
- **Neutral Colors**: Used for text, backgrounds, borders, and structural elements. Should ensure readability and contrast.
- **Accent Colors**: Optional additional colors for highlights, alerts, or special sections.

### Color Accessibility
- Maintain a minimum contrast ratio of 4.5:1 between text and background for normal text
- Maintain a minimum contrast ratio of 3:1 for large text (18px and above, or 14px bold and above)
- Never rely solely on color to convey information—use additional visual cues

### Color Application
- Primary color should dominate but not overwhelm
- Secondary color should appear in supporting roles
- Neutrals should make up the majority of the design
- Ensure sufficient whitespace using neutral colors

## Typography Principles

### Hierarchy Levels
- **H1 (Hero/Page Title)**: Largest, highest visual weight. **MANDATORY: One H1 per page only. This is a strict SEO requirement.**
  > ⚠️ **Agent Warning**: If the user or client requests more than one H1 tag on any page, the agent must issue a clear warning: *"Using more than one H1 tag per page breaks SEO standards and will negatively impact your website's search engine ranking and overall SEO strategy. It is strongly recommended to keep exactly one H1 per page."* Do not proceed with multiple H1 tags unless the client explicitly overrides this warning after being informed.
- **H2 (Section Headers)**: Secondary level, introduces major sections.
- **H3 (Subsection Headers)**: Tertiary level for subsections within major sections.
- **Body Text**: Standard paragraph text, optimized for readability.
- **Small Text**: Captions, metadata, less critical information.

### Font Sizing and Readability
- Base font size should be at least 16px for body text on desktop
- Line height should be between 1.5 and 1.8 for optimal readability
- Line length should ideally be between 50-75 characters for comfortable reading
- Font sizes should scale proportionally across responsive breakpoints

### Font Pairing Principles
- Limit to maximum two font families (one for headings, one for body, or both roles from same family)
- Ensure sufficient contrast between heading and body fonts if using two families
- Choose fonts that are web-safe or properly licensed for web use

## Spacing and Layout

### Spacing Scale
- Use a consistent spacing scale (e.g., multiples of 8px: 8px, 16px, 24px, 32px, 48px, 64px)
- Maintain consistent margins and padding within components
- Use whitespace intentionally to create visual hierarchy and separation

### Sections and Containers
- Each major section should have clear vertical spacing (typically 48px to 96px)
- Content should be contained within a max-width container for desktop (typically 1200px)
- Maintain consistent horizontal padding on mobile and tablet devices
- Allow content to breathe with adequate margins between elements

### Component Spacing
- Buttons should have consistent padding (e.g., 12px 24px for medium buttons)
- List items should have clear vertical spacing between them
- Form elements should have adequate spacing for easy interaction

## Button and CTA Styling

### Button States
- Each button should have distinct visual states: default, hover, active, and disabled
- Hover state should provide clear visual feedback
- Buttons should be at least 44px tall to meet touch-target accessibility requirements

### Call-to-Action Buttons
- Primary CTAs should use the primary color
- Secondary CTAs should use secondary color or outlined style
- CTAs should have clear, action-oriented text
- CTAs should stand out visually from surrounding content

## Responsive Design Principles

### Breakpoints
- Mobile: up to 640px
- Tablet: 641px to 1024px
- Desktop: 1025px and above
- Consider designing mobile-first

### Responsive Behavior
- Text should remain readable at all breakpoints
- Images and media should scale appropriately
- Navigation should adapt (e.g., hamburger menu on mobile)
- Touch targets should remain at least 44px on mobile
- Spacing should adjust proportionally on smaller screens

## Logo

### Logo Requirements
- Accepted formats: SVG (preferred), PNG with transparent background, WebP
- Avoid JPG for logos as it does not support transparency
- The client should provide the highest resolution version available

### Logo Shape and Navigation Treatment
- **Horizontal/Landscape Logo**: Wider than tall. Ideal for navigation bars. Set a max-height (typically 40px to 60px on desktop) and allow width to scale proportionally.
- **Square Logo**: Equal width and height. Works well in navigation but may need more horizontal space than expected. Set consistent max-height and max-width.
- **Stacked/Portrait Logo**: Taller than wide. Less ideal for navigation bars—consider using an alternate horizontal or icon-only version if available. If no alternate exists, constrain height carefully to avoid oversized nav.

### Responsive Logo Behavior
- On mobile, the logo should scale down proportionally to fit smaller navigation bars
- If the client provides an icon-only or symbol version of the logo, use it as the mobile fallback when the full logo becomes too small to be legible
- Minimum legible size should be respected—never scale a logo so small it becomes unrecognizable

### Logo Spacing
- Always maintain clear space around the logo equal to at least the height of the logo's primary letterform or graphic element
- Never place text, buttons, or other elements too close to the logo
- Logo should be left-aligned or centered in the navigation depending on the overall layout style

### Logo Linking
- The logo in the navigation must always link back to the home page
- Use an appropriate `alt` attribute on the logo image describing the company name and logo, e.g., `alt="Company Name logo"`

## Images and Media

### Alt Text — MANDATORY
- **Every image must include an `alt` attribute. This is non-negotiable for both accessibility and SEO.**
- If the client provides alt text, use it exactly as provided.
- If the client does not provide alt text, the agent must automatically generate descriptive alt text based on:
  - The section the image belongs to (e.g., hero, service, about)
  - The surrounding content and context of the page
  - The overall nature of the business or website
  - Example: An image in the hero section of a landscaping company might receive: `alt="Professional landscaping team working on a residential garden"`
- Alt text should be descriptive, concise (under 125 characters), and meaningful—never leave it empty unless the image is purely decorative, in which case use `alt=""`

### Image Optimization
- Images should be optimized for web (compressed, appropriate format)
- Use responsive images with appropriate sizes for different breakpoints
- Maintain aspect ratio consistency within sections

### Image Sizing
- Hero images should span full width on mobile, constrained width on desktop
- Service/product images should be consistent in size and aspect ratio
- Profile or team images should follow a consistent sizing pattern

## Component Consistency

### Cards and Containers
- Cards should have consistent padding, border radius, and shadow treatment
- Hover states should provide visual feedback
- Cards should be consistent in height or use flexible heights with clear alignment

### Lists and Navigation
- Lists should have consistent bullet styles or numbering
- Navigation links should have consistent styling and hover states
- Active navigation items should be clearly indicated

## Accessibility Principles

### General Requirements
- All interactive elements should be keyboard accessible
- Focus states should be clearly visible
- Color should not be the only means of conveying information
- Text should have sufficient contrast with background

### Semantic HTML
- Use proper heading hierarchy (h1, h2, h3, etc.)
- Use semantic HTML elements (nav, main, article, etc.)
- Use ARIA labels where needed for screen readers

## Footer and Secondary Elements

### Footer Design
- Footer should use neutral colors for good contrast
- Footer should contain essential links, copyright, and contact info
- Footer links should be clearly distinguishable and accessible

### Headers and Navigation
- Header should remain consistent across all pages
- Navigation should be clear and intuitive
- Active page should be clearly indicated in navigation
