# Capability 1: Extract Design System

This is the core technique of the Vibe Design methodology — the "Prompt de Mil Dólares" (StrackDesignSystemV2). It transforms a downloaded HTML reference site into a reusable Design System file.

## When to Use

The user has a downloaded HTML file (usually `index.html`) from a reference site and wants to extract its visual DNA into a `design-system.html` file.

## The Prompt

Use this prompt **verbatim** — it was optimized through $1,000+ in token testing. Replace `$ARGUMENTS` with the path to the user's HTML file.

---

# Extract HTML Design System v2

You are a **Design System Showcase Builder**.
You are given a reference website HTML:

`$ARGUMENTS`

Your task is to create **one new intermediate HTML file** that acts as a **living design system + pattern library** for this exact design.

---

## GOAL

Generate **one single file** called: `design-system.html` and place it in the same folder of the html file.

This file must preserve the **exact look & behavior** of the reference design by **reusing the original HTML, CSS classes, animations, keyframes, transitions, effects, and layout patterns** — not approximations.

---

## HARD RULES (NON-NEGOTIABLE)

1. Do **not redesign** or invent new styles.
2. Reuse **exact class names, animations, timing, easing, hover/focus states**.
3. Reference the **same CSS/JS assets** used by the original.
4. If a style/component is not used in the reference HTML, **do not add it**.
5. The file must be **self-explanatory by structure** (sections = documentation).
6. Include a **top horizontal nav** with anchor links to each section.

---

## OBJECTIVE

Build a **single page** composed of **canonical examples** of the design system, organized in sections.

---

### 0) Hero (Exact Clone, Text Adapted)

The **first section MUST be a direct clone of the original Hero**:

- Same HTML structure
- Same class names
- Same layout
- Same images and components
- Same animations and interactions
- Same buttons and background
- Same UI components (if any)

**Allowed change (only this):**

- Replace the hero text content to present the **Design System**
- Keep similar text length and hierarchy

**Forbidden:**

- Do not change layout, spacing, alignment, or animations
- Do not add or remove elements

---

### 1) Typography

Create a **Typography section** rendered as a **spec table / vertical list**.

Each row MUST contain:

- Style name (e.g. "Heading 1", "Bold M")
- Live text preview using the **exact original HTML element and CSS classes**
- Font size / line-height label aligned right (format: `40px / 48px`)

Include ONLY styles that exist in the reference HTML, in this order:

- Heading 1
- Heading 2
- Heading 3
- Heading 4
- Bold L / Bold M / Bold S
- Paragraph (larger body, if exists)
- Regular L / Regular M / Regular S

Rules:

- No inline styles
- No normalization
- Typography, colors, spacing, and gradients MUST come from original CSS
- If a style uses gradient text, show it exactly the same
- If a style does not exist, do NOT include it

This section must communicate **hierarchy, scale, and rhythm** at a glance.

---

### 2) Colors & Surfaces

- Backgrounds (page, section, card, glass/blur if exists)
- Borders, dividers, overlays
- Gradients (as swatches + usage context)

---

### 3) UI Components

- Buttons, inputs, cards, etc. (only those that exist)
- Show states side-by-side: default / hover / active / focus / disabled
- Inputs only if present (default/focus/error if applicable)

---

### 4) Layout & Spacing

- Containers, grids, columns, section paddings
- Show 2–3 real layout patterns from the reference (hero layout, grid, split)

---

### 5) Motion & Interaction

Show all motion behaviors present:

- Entrance animations (if any)
- Hover lifts/glows
- Button hover transitions
- Scroll/reveal behavior (only if present)

Include a small **Motion Gallery** demonstrating each animation class.

---

### 6) Icons

If the reference uses icons:

- Display the **same icon style/system**
- Show size variants and color inheritance
- Use the **same markup and classes**

If icons are not present, omit this section entirely.

---

## How to Execute in Claude Code

1. Read the user's HTML file to understand its structure
2. Identify all CSS/JS files it references
3. Apply the prompt above, generating `design-system.html` in the same folder
4. The generated file must reference the same CSS/JS assets as the original
5. Verify the file opens correctly and renders the design system

## Tips

- **Use the best available model for extraction** — the quality of the design system determines everything downstream
- A good DS extracted with a cheap model beats a bad DS from an expensive model
- If the first attempt misses components, ask Claude to add them in a second pass
- Common issues: missing animations, wrong fonts, simplified gradients — check each section
- The DS is reusable indefinitely — invest time getting it right
