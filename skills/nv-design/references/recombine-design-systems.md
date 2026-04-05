# Capability 2: Recombine Design Systems

Create a new, unique design system by mixing elements from 2-3 existing design systems. This is the creative heart of Vibe Design — taking the best from multiple references to create something original.

## When to Use

The user has 2-3 design system files (or reference HTML sites) and wants to create a new hybrid design system that combines the best elements of each.

## The Recombination Prompt

Adapt this template based on the user's files. The `@` references should point to their actual files.

---

Create a new `design_system.html` in the project's assets folder.

It should be a **creative combination** of the following design systems and files:
@[primary-reference] @[secondary-reference] @[tertiary-reference]

The new design system should be **heavily based on**: @[primary-reference] (especially its [key characteristic the user likes — e.g., "transparent lettering", "dark theme", "glass effects"]).

Use the other references for **inspiration** — grab animations, beautiful elements, and interactions you find there.

**Pay special attention to the first section (hero)**, which should showcase the design system's capabilities. It can contain images found in the references, animations, button effects, backgrounds, details, entrance animations, and glow effects.

Focus on details and **create something outside the box**.

Your design system must reference the **same CSS classes and JS** used in the referenced files.

---

The final design system must contain:

1. **Hero section** — A demonstration of the design system's capabilities. Go all out here.

2. **Typography**
   - Font families (primary, fallback stack, monospace if any)
   - Font loading strategy (local, CDN, weight ranges)
   - Full type scale: h1 → h6
   - body-lg / body / body-sm / captions / labels / helper text
   - For each text role: font-family, font-weight (numeric), font-size, line-height, letter-spacing, text-transform

3. **Color system**
   - Hex, RGB, HSL
   - Opacity variants
   - Gradient participation
   - Semantic role: primary / secondary / accent / neutral / feedback / decorative
   - Contextual usage rules: text / background / border / hover / active / disabled

4. **UI Components** (with animations)
   - Buttons, Inputs, Cards, Navbars, Sections, Modals, Badges, Tooltips
   - Full spec for each detected component

5. **Icons**

6. **Animations**

In **all sections**, repeatedly use background animations, entrance/transition animations, and button/component animations. Make section backgrounds elegant with animated backgrounds where possible.

---

## Execution Strategy

1. **Read all reference files** — understand what each brings to the table
2. **Identify the primary reference** — this defines the base identity (colors, typography, overall feel)
3. **Cherry-pick from secondary references** — animations, specific components, interaction patterns
4. **Generate the combined DS** — one single HTML file that works standalone
5. **Iterate** — first version is rarely final. Ask user to review, then refine

## Tips

- Don't ask the AI to generate 3 design systems at once — it gets lazy and cuts corners on all of them. Do ONE at a time with full attention.
- Use **open prompts** for creativity ("create something outside the box", "go all out") vs **closed prompts** for precision ("use exactly these fonts")
- Repeat animation instructions multiple times in the prompt — the AI tends to forget them in later sections
- If colors don't match the project (e.g., yellow for a law firm), ask to swap: "Replace all yellow with a blue that conveys security and trust"
- Remove italic fonts if they don't fit the project's tone
- Generate multiple versions with different models and compare
- Always Git checkpoint before and after: `git commit -m "design system: v1"`
