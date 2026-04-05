# Capability 4: Modernize Existing Site

Transform an old or outdated website into a modern design while preserving all original content. This is a two-phase process: extract content, then rebuild with a new design system.

## When to Use

The user has an existing website (old, ugly, outdated) and wants to modernize it without losing any content, copy, or functionality.

## Critical Recommendation

**Always create a fresh build from zero** instead of trying to modify the old site's code. Old sites (especially WordPress, Elementor, Wix exports) carry massive amounts of unnecessary code and dependencies. It's faster and cleaner to:

1. Extract the content
2. Create a new design system
3. Build the new site from scratch using the content + design system

## Workflow

### Phase 1: Extract Content to Intermediate File

Use a fast/cheap model for this step — it's mechanical extraction, not creative work.

**Prompt:**

---

I'm doing a redesign of this site. Help me with this process.

Create an intermediate file called `site.md` that will be used as the starting point for the new site. This file should contain, section by section ("dobra" by "dobra"), the copy present in the site, as well as a simple ASCII representation of the layout.

The file should follow this pattern:

## Dobra [number]
Copy here
ASCII layout here

Example:
## Dobra 1
[site text]
[simple ASCII drawing]

## Dobra 2
[site text]
[simple ASCII drawing]

---

The intermediate file (`site.md`) prevents the AI from hallucinating or changing the original copy. It's a clean extraction of what exists.

**ASCII Layout Example:**
```
## Dobra 1: Header
Copy: "Arnold Lopes - Criminal Law, Litigation"
ASCII:
=== LOGO ===    === NAV MENU ===
=== CTA BUTTON ===

## Dobra 2: Areas of Expertise
Copy: "Criminal Law, Litigation, etc"
ASCII:
[CARD] [CARD] [CARD]
[CARD] [CARD] [CARD]
```

### Phase 2: Create Design System

Before building the new site, create a design system. Options:

**Option A: Extract from a reference site the user likes**
→ Use Capability 1 (Extract Design System)

**Option B: Recombine multiple references**
→ Use Capability 2 (Recombine Design Systems)

**Option C: Extract from the old site and enhance**
→ Extract the old site's DS, then recombine with modern references to upgrade it

When choosing colors and style, consider the industry:
- Law firm → Blues (trust, security), serious typography
- Creative agency → Bold colors, playful typography
- SaaS → Clean, modern, often dark mode
- E-commerce → Product-focused, clear CTAs

### Phase 3: Build the New Site

**Prompt:**

---

The file `site.md` contains the copy and layout of the original site. The file `@[old-index.html]` contains images and assets to reuse.

Create a new `index.html` in the project root that is a **redesign** of this site.

Use the design system we created (`@design-system.html`) as the **source of truth** for all design decisions. Use its fonts, colors, effects, transitions, hero section patterns, buttons — everything from the design system.

Preserve ALL original copy from site.md. Don't change, remove, or add text content.
Reuse images and assets from the original site.

---

Then follow the section-by-section approach from Capability 3 (Build Landing Page).

### Phase 4: Prepare for Production

1. Organize folder structure:
```
project/
├── Design Systems/          (backup/reference)
│   ├── design-system.html
│   └── old-site/            (original site files)
├── assets/
│   ├── css/
│   ├── js/
│   ├── images/
│   └── fonts/
└── index.html               (new site)
```

2. Ask the AI to reorganize and adjust all import paths
3. Test everything works after reorganization
4. Git commit and deploy

**Prompt for reorganization:**

---

Organize the project structure for production. Move the design system to a `/design-systems/` backup folder, adjust all its internal paths. Move old site files to `/backup/`. Create a proper `/assets/css/`, `/assets/js/`, `/assets/images/` structure for the new site and adjust all imports.

---

## Tips

- The intermediate file (`site.md`) is the key innovation — it prevents copy loss and hallucination
- Use a fast model for extraction (Phase 1) and the best model for building (Phase 3)
- Always verify that ALL original copy made it into the new site
- Images from the old site can be reused directly — just update paths
- Git checkpoint after each phase
- The complete process takes ~2 hours for a typical business site
- This is a monetizable service — clients pay for site modernization
