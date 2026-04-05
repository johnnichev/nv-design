# nv:design

Web design skill. Vibe Design methodology: extract design systems from source code, recombine, build sites section-by-section. Ships SKILL.md + 6 reference files to `~/.claude/skills/nv-design/`.

## Commands

```bash
# Install skill globally
npx skills add johnnichev/nv-design -g -y

# Invoke the skill
/nv-design

# Verify line counts after edits
wc -l skills/nv-design/SKILL.md                    # MUST be under 250
wc -l skills/nv-design/references/*.md              # Each MUST be under 200

# Preview site locally
npx serve .

# Git checkpoint after each section
git add . && git commit -m "section: [name]"

# Deploy
vercel
```

## Stack

- Pure markdown skill — no runtime, no dependencies
- SKILL.md (210 lines) routes to 6 reference files via progressive disclosure
- Based on Asimov Academy "Trilha IA Designer" methodology
- Output stack: plain HTML/CSS/JS, CDN libs (GSAP, ScrollTrigger, Locomotive Scroll, AOS)

## Boundaries

### Always
- Run `wc -l` after editing SKILL.md or any reference file
- MUST use positive instructions ("MUST use X") — rewrite all soft negatives
- Preserve the 7 Core Laws in SKILL.md
- Keep SKILL.md routing table in sync with actual reference files
- MUST build sites one section at a time
- MUST use design system as source of truth for all styles
- MUST `git commit` after completing each section
- MUST read the reference file (`references/*.md`) BEFORE starting any capability

### Ask First
- Changing the Extract Design System prompt (the "$1000 prompt" — StrackDesignSystemV2)
- Modifying the 7 Principles framework for image prompts
- Adding or removing capabilities (currently 6)
- Changing the quality audit checklist criteria
- Adding a framework (React, Next.js, Svelte) instead of vanilla HTML
- Changing a design system's color palette or typography
- Deleting or reorganizing existing project files
- Deploying to production

### Never
- NEVER modify `references/extract-design-system.md` lines 15-152 without explicit approval — the "$1000 prompt" optimized through $1000+ in token testing
- NEVER combine multiple capabilities into a single reference file — one capability per file
- NEVER add runtime dependencies to package.json
- NEVER use soft negative instructions ("don't", "avoid", "do not") — MUST rewrite as positive "MUST use Y"
- NEVER generate an entire site in one prompt — one section at a time
- NEVER use screenshots as design reference — MUST use source code (HTML/CSS/JS)
- NEVER skip the design system step and jump straight to site generation

## Landmines

- `references/extract-design-system.md` (169 lines) is **SACRED**. Lines 15-152 are the verbatim StrackDesignSystemV2 ("$1000 prompt"). Changing even one word can degrade extraction quality. Optimized empirically, not theoretically.
- `SKILL.md` (210 lines): 40 lines from the 250-line cap. Exceeding 250 degrades agent context quality. The routing table (lines 74-91) MUST match actual reference files.
- Each reference file MUST stay under 200 lines. Exceeding triggers token bloat in skill loading.
- `design-system.html` files reference the SAME CSS/JS assets as the original site — changing asset paths breaks the DS silently.
- `site.md` intermediate file prevents copy hallucination during modernization — skipping it causes the AI to invent text.
- `references/video-media.md`: Newest capability (v2.0). Less battle-tested than the original 5. Google Whisk/Flow URLs may change.
- Soft negatives in reference files: Course material uses "do not" naturally. These MUST be rewritten as positive MUST instructions — research shows negative instructions increase probability of the prohibited behavior.

## Patterns

- **Design system extraction** MUST precede site building — separates professional output from generic purple-gradient templates
- **Recombination** = mix 2-3 design systems. Primary DS defines base; secondary provides accent elements
- **Section naming** uses "dobra" (Portuguese fold): primeira dobra = hero, segunda dobra = features, etc.
- **Model selection**: best model for DS extraction, fast model for content extraction (`site.md`), any decent model for building with a good DS
