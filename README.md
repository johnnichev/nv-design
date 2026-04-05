# nv:design

**Professional web design with AI — the methodology that actually works.**

```bash
npx skills add johnnichev/nv-design -g -y
```

A skill that transforms AI from a "beginner intern" into a "senior design agency" by feeding it design systems extracted from source code instead of vague prompts or screenshots.

> "Bad models + right technique (Design Systems) > Good models + wrong technique (prompts/screenshots)"
> — Asimov Academy, Trilha IA Designer

---

## The Problem

You ask AI to build you a website. It produces:

| Symptom | Why It Happens |
|---------|---------------|
| Purple/blue gradient everything | AI trained on internet average — most sites are simple |
| Generic, "clean" layouts | Models default to safe, minimal output |
| No animations or micro-interactions | Too abstract to generate from text prompts alone |
| Looks like a template | One-shot prompting gives one-shot results |
| Different every time you run it | Images/screenshots lose detail in token translation |

**Elaborate prompts don't fix this.** Neither do screenshots. Anthropic themselves published why AI struggles with front-end design — the training data is dominated by simple sites.

## The Solution

nv:design uses **Design Systems as source code** — the actual CSS classes, animations, keyframes, and component patterns from professional reference sites — to guide AI with perfect fidelity.

The methodology:

1. **Download** a reference site you admire
2. **Extract** its Design System using the battle-tested "Prompt de Mil Dólares" (a prompt optimized through $1,000+ in token testing)
3. **Recombine** 2-3 design systems to create your own unique identity
4. **Build** your site section-by-section, guided by the design system
5. **Deploy** to Vercel/GitHub Pages in minutes

Result: Sites that look like they were built by a senior design agency. In 1-2 hours instead of weeks.

## What It Does

| Capability | Description |
|---|---|
| **Extract Design System** | Takes any HTML site and produces a `design-system.html` — the complete visual DNA (typography, colors, components, animations, layout patterns) |
| **Recombine Design Systems** | Mixes 2-3 design systems to create a unique hybrid identity |
| **Build Landing Page** | Constructs a professional site section-by-section (Hero → Features → Specs → CTA → Footer) using a design system as the source of truth |
| **Modernize Existing Site** | Redesigns an old site while preserving all content — extracts copy to intermediate file, rebuilds with new design system |
| **Generate Image Prompts** | Creates structured prompts using the 7 Principles framework (Subject, Action, Style, Scene, Color, Framing, Mood) for professional AI image generation |

## Install

**Option 1: Skills CLI (recommended)**
```bash
npx skills add johnnichev/nv-design -g -y
```

**Option 2: One-liner**
```bash
mkdir -p ~/.claude/skills/nv-design && curl -sL \
  https://raw.githubusercontent.com/johnnichev/nv-design/main/skills/nv-design/SKILL.md \
  -o ~/.claude/skills/nv-design/SKILL.md && \
for f in extract-design-system recombine-design-systems build-landing-page modernize-site image-prompts; do \
  mkdir -p ~/.claude/skills/nv-design/references && curl -sL \
  "https://raw.githubusercontent.com/johnnichev/nv-design/main/skills/nv-design/references/$f.md" \
  -o "~/.claude/skills/nv-design/references/$f.md"; \
done
```

**Option 3: Clone**
```bash
git clone https://github.com/johnnichev/nv-design.git
mkdir -p ~/.claude/skills/nv-design
cp -r nv-design/skills/nv-design/* ~/.claude/skills/nv-design/
```

**Then open any project and ask Claude:**
```
Extract the design system from this site
```
```
Build me a landing page using this design system
```
```
Modernize this old website
```

## Quick Example

### Extract a Design System

```
I downloaded this reference site to ./reference/index.html
Extract its design system so I can use it to build my own site.
```

Claude reads the HTML, identifies all CSS/JS assets, and generates a `design-system.html` with:
- Hero section (exact clone with adapted text)
- Typography spec table (every heading, body, caption with exact CSS)
- Color & surface system (backgrounds, gradients, borders)
- UI components with all states (default, hover, active, focus)
- Layout patterns (grids, containers, spacing)
- Motion gallery (every animation class, live demos)
- Icon system (if present)

### Build a Landing Page

```
Use the design system we extracted to build a landing page for my SaaS product.
Start with the hero section — I want a parallax video background like Apple.
```

Claude builds section-by-section, never one-shot:
1. Hero with parallax video, entrance animations, CTA
2. Features section with cards and hover effects
3. Technology/specs section with animated backgrounds
4. Social proof with testimonials
5. Pricing/CTA section
6. Footer

Each section uses the exact CSS classes, animations, and patterns from your design system.

## The 3 Fundamental Principles

These are non-negotiable and apply to every capability:

**1. Simplify instructions** — One section at a time. Never generate an entire site in one prompt. AI gets lazy when asked to do too many things, cutting corners on the details that make a site look professional.

**2. Simplify the stack** — Plain HTML + CSS + JavaScript. No React, Next.js, or complex frameworks unless specifically needed. External libraries (GSAP, ScrollTrigger) via CDN are fine.

**3. Patience with errors** — AI models are stochastic. The same prompt produces different results each run. Errors are normal. Don't fight the AI — ask it to fix its own mistakes. Usually takes 2-3 iterations.

## The 7 Principles for Image Prompts

Every professional AI image prompt must address:

1. **Subject** — Who/what, with specific physical details
2. **Action** — What they're doing, natural and unstaged
3. **Style** — Photographic style, camera, lens, finish
4. **Scene** — Environment, what's NOT there, feeling
5. **Color** — Palette AND lighting setup
6. **Framing** — Camera angle, shot type, composition
7. **Mood** — Emotional feeling to convey

## Methodology Origin

nv:design encodes the complete **Trilha IA Designer** methodology from [Asimov Academy](https://hub.asimov.academy/trilha/ia-designer/), taught by Rodrigo Tadewald. The core technique — using source code as design reference instead of images or text — was discovered empirically and validated through the "Prompt de Mil Dólares" (StrackDesignSystemV2), which cost $1,000+ in token testing to optimize.

The methodology covers 5 courses, 38 lessons, and 5+ hours of content distilled into actionable skill instructions.

## Docs

- [Quickstart](docs/QUICKSTART.md) — 2-minute install and first design system
- [Methodology](docs/METHODOLOGY.md) — the full Vibe Design philosophy and workflow
- [FAQ](docs/FAQ.md) — common questions

## Skill Structure

```
skills/nv-design/
├── SKILL.md                              # Entry point — routing, universal rules
└── references/
    ├── extract-design-system.md          # "Prompt de Mil Dólares" — DS extraction
    ├── recombine-design-systems.md       # Creative DS recombination
    ├── build-landing-page.md             # Section-by-section site building
    ├── modernize-site.md                 # Old site → modern redesign
    └── image-prompts.md                  # 7 Principles image prompt framework
```

Progressive disclosure: SKILL.md loads first (~90 lines), reference files load only when the specific capability is triggered.

## Contributing

nv:design improves when practitioners share what works. Open an issue or PR with:
- Design system extraction edge cases
- Prompt improvements that produced better results
- New reference site patterns
- Industry-specific adaptations (e-commerce, SaaS, portfolio, etc.)

## License

MIT

---

**Built by [johnnichev](https://github.com/johnnichev).** Professional web design with AI.
