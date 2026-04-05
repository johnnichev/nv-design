# The Vibe Design Methodology

## Origin

The term "Vibe Design" evolves from "Vibe Coding" — coined by a former OpenAI engineer to describe coding by directing AI rather than writing code manually. Vibe Design applies the same principle to visual design: instead of manually designing interfaces, you supervise AI with the right technique and references.

The methodology was developed by Rodrigo Tadewald at [Asimov Academy](https://hub.asimov.academy/trilha/ia-designer/) through extensive empirical testing across multiple AI models. The key insight was discovered by accident: feeding AI source code instead of images or text descriptions produces dramatically better results.

## Why AI Fails at Design (Without This Methodology)

AI language models are trained on the entire internet. The vast majority of websites are simple, functional, and visually basic. When you ask AI to "create a beautiful website," it generates the statistical average of what it learned — which means:

- Purple/blue gradients (the "AI default" palette)
- Excessively clean layouts with too much whitespace
- No animations, backgrounds, or micro-interactions
- Generic, template-like appearance

This happens regardless of how elaborate your prompt is. Even prompts like "You are an award-winning UI/UX designer..." produce mediocre results because the fundamental problem is input quality, not instruction quality.

**Anthropic confirmed this** in a blog post discussing why AI struggles with front-end design aesthetics.

## The Key Insight: Source Code as Reference

The breakthrough: AI works with text (tokens). When you give it an image, it internally describes it in tokens — losing fonts, exact colors, animation details, gradients, and spacing. But when you give it the **source code** of a site, it has perfect access to every CSS class, animation keyframe, color value, and component pattern.

```
Image → AI translates to tokens → loses detail → mediocre output
Source code → AI reads directly → perfect fidelity → professional output
```

This is why a bad model with source code reference outperforms a good model with only screenshots.

## Design Systems: The DNA of Design

A Design System is a structured extraction of a site's visual rules:

- **Typography**: fonts, weights, sizes, line-heights, letter-spacing for each heading level
- **Colors**: exact hex/RGB values, gradients, opacity variants, semantic roles
- **Components**: buttons (all states), cards, inputs, badges, navbars — with exact CSS classes
- **Layout**: grid patterns, containers, spacing, section padding
- **Motion**: entrance animations, hover effects, transitions, scroll behaviors
- **Icons**: icon system, sizes, color inheritance

The Design System file (`design-system.html`) references the same CSS and JS as the original site, so all behaviors are preserved perfectly. It's self-documenting — each section demonstrates the pattern visually.

## The "Prompt de Mil Dólares"

The core extraction prompt (StrackDesignSystemV2) was optimized through $1,000+ in token testing across multiple models. It instructs the AI to:

1. Clone the original hero section exactly (only adapting text)
2. Create a typography spec table with live previews
3. Document colors and surfaces with real swatches
4. Render all UI components with all interaction states
5. Show layout patterns from the original
6. Build a motion gallery demonstrating every animation
7. Display the icon system

**Hard rules**: no redesigning, no new styles, no approximations. The DS must use the exact same classes, animations, and assets as the original.

## Recombination: Creating Unique Identities

The creative act in Vibe Design is **recombination** — mixing 2-3 design systems to create something new. Take the typography from one reference, the animation patterns from another, and the color system from a third. The AI handles the technical merging; you direct the creative vision.

This is how professional designers work too — finding and combining references. The difference is AI does the implementation in minutes instead of days.

## Section-by-Section Building

Sites are built one section ("dobra") at a time:

1. **Hero** (most critical — 70% of visitors never scroll past it)
2. **Features/Benefits**
3. **Technology/Specs**
4. **Social Proof/Testimonials**
5. **CTA/Pricing**
6. **Footer**

Each section gets its own prompt, its own review cycle, and its own Git checkpoint. This prevents the AI from cutting corners and allows focused refinement.

## Modernization Workflow

For existing sites, the methodology uses a two-phase approach:

1. **Extract**: Create an intermediate `site.md` file with the original copy and ASCII layout diagrams for each section. This prevents the AI from hallucinating or changing content during redesign.

2. **Rebuild**: Generate a new `index.html` using the extracted content + a new design system. All original text is preserved; only the visual presentation changes.

The key insight: always build from zero rather than modifying old code. Old sites (especially WordPress/Elementor/Wix) carry too much technical debt.

## The Role of the Vibe Designer

In traditional design, there's a UI Designer (Figma) and a Front-End Developer (code). In Vibe Design, AI handles both operational roles. The human acts as:

- **Director**: defines the vision, style, and objectives
- **Curator**: selects and combines references
- **Reviewer**: evaluates AI output and requests refinements

You don't need to write code. You need to know what good design looks like, find good references, and communicate clearly what you want changed.
