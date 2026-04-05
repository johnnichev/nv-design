# Capability 3: Build Landing Page

Build a professional landing page section-by-section using a design system as the visual foundation. This is the main production workflow of Vibe Design.

## When to Use

The user has a design system file and wants to build a landing page or website. They may also have reference images/screenshots for specific sections.

## Critical Rule: Section by Section

**NEVER generate an entire site in one prompt.** Build one section ("dobra") at a time:

1. Hero (primeira dobra) — most important, 70% of visitors never scroll past it
2. Features / Benefits (segunda dobra)
3. Specs / Technology / How it works (terceira dobra)
4. Social proof / Testimonials (quarta dobra)
5. CTA / Pricing (quinta dobra)
6. Footer

Each section gets its own prompt, its own review cycle, and its own Git checkpoint.

## Workflow

### Step 1: Plan the Sections

Before coding, plan what sections the site needs. Ask the user, or suggest:

"What sections should your site have? Here's a common structure for a [product/service] landing page:
1. Hero — Main headline, video/image, CTA
2. Problem & Solution — Why the product exists
3. Features — Key benefits with visuals
4. Technology / How it Works — Differentiators
5. Social Proof — Testimonials, logos, numbers
6. Pricing / CTA — Final conversion push
7. Footer — Links, contact, legal"

### Step 2: Build the Hero

The hero is the most critical section. Use this prompt structure:

---

Create an `index.html` containing **only a hero section** for [describe the product/site].

Important files:
- **Design system**: @design-system.html — contains all typography, color, layout, and animation rules. This is the source of truth for the design.
- **Video/Image**: @[asset file] — use this as [background video with parallax / hero image / etc.]

**Visual reference**: [paste or attach a screenshot of a reference layout]

Requirements:
- Use the design system's fonts, colors, effects, transitions, and hero section patterns
- Include entrance animations (fade in, blur in) for all elements
- Animated background (from design system)
- H1 headline + H2 subtitle + CTA button with hover animation
- [Parallax scroll effect with the video / specific layout instructions]

Use libraries via CDN if needed (GSAP ScrollTrigger, Locomotive Scroll, etc.).

---

### Step 3: Build Remaining Sections

For each subsequent section, add to the existing `index.html`:

---

Now build the **[second/third/etc.] section** of the site.

Use this visual reference for layout: [attach screenshot if available]

Requirements:
- [Describe what this section should contain]
- Use our design system's identity: same fonts, colors, effects, transitions
- Include entrance animations for all elements
- Animated/elegant background
- [Specific requirements: cards, grid, icons, video, etc.]

Build on top of the existing index.html. Don't touch the previous sections.

---

### Step 4: Polish

After all sections are built, do a refinement pass:

---

Polish the site. Focus on:
- Consistent spacing between sections
- Smooth transitions when scrolling between sections
- Background animations in sections that feel flat
- Hover effects on all interactive elements
- Micro-animations (subtle movements, glows, shadows)
- Check that all entrance animations trigger correctly on scroll

Don't break anything that's already working.

---

## Strategies for Each Section

### Strategy 1: Reference-Based (Best Quality)
Take a screenshot of a site you like, ask an LLM to describe what it sees, then use that description + your design system to build the section. Best results, least creative freedom.

### Strategy 2: AI-Creative (More Variation)
Give the AI your design system and a brief description: "Build a features section that highlights these 3 benefits. Be creative. Use the design system." More variation, sometimes surprising results.

### Strategy 3: Hybrid
Use a reference for layout/structure but let the AI be creative with details, animations, and backgrounds.

### Strategy 4: Iterative Refinement
Build a basic version, then ask for 2-3 rounds of improvements:
- "Make it more polished. More details, animations, background effects."
- "Improve the background. Make it more elegant with subtle animation."
- "Add micro-interactions to buttons and cards."

## Parallax Video (Apple-style)

For hero sections with video controlled by scroll:

```
Requirements:
- Video plays as user scrolls (not auto-play)
- Video is sticky/fixed during its scroll range
- Smooth scrubbing tied to scroll position
- Use GSAP ScrollTrigger or similar library via CDN
- Video should be muted for autoplay compatibility
- Use view-height units for scroll range
```

## Copy / Text

For product sites, use terms that add perceived value:
- "Swiss engineering", "aerospace aluminum", "precision-crafted"
- "Engineered for [professionals/creators/etc.]"
- Be specific and aspirational, not generic

Ask the user for their product details, or let the AI be creative with placeholder copy that sounds premium.

## Tips

- Run 2-3 versions in parallel for important sections (especially hero) and pick the best
- Use Git checkpoint after each section: `git commit -m "section: hero complete"`
- If a section breaks a previous one, use `git checkout` to restore and try again
- Force refresh browser (Cmd+Shift+R / Ctrl+Shift+R) when testing locally
- The entire process should take 1-2 hours for a complete landing page
- References = better quality. Always prefer working with references over pure prompts.
