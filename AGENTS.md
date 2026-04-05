# nv-design

Web design skill distribution. Ships SKILL.md + 6 reference files to `~/.claude/skills/nv-design/`.

## Commands

```bash
# Install
npx skills add johnnichev/nv-design -g -y

# Test
/nv-design

# Verify line counts
wc -l skills/nv-design/SKILL.md                    # MUST be under 250
wc -l skills/nv-design/references/*.md              # Each MUST be under 200
```

## Stack

- Pure markdown skill — no runtime, no dependencies
- SKILL.md (210 lines) routes to 6 reference files via progressive disclosure
- Based on Asimov Academy "Trilha IA Designer" methodology

## Boundaries

### Always
- Run `wc -l` after editing SKILL.md or any reference file
- MUST use positive instructions ("MUST use X" not "don't use X")
- Preserve the 6 Core Laws in SKILL.md
- Keep SKILL.md routing table in sync with actual reference files

### Ask First
- Changing the Extract Design System prompt (the "$1000 prompt" — StrackDesignSystemV2)
- Modifying the 7 Principles framework for image prompts
- Adding or removing capabilities (currently 6)
- Changing the quality audit checklist criteria

### Never
- NEVER modify `references/extract-design-system.md` lines 15-152 without explicit approval — this is the "$1000 prompt" optimized through $1000+ in token testing
- NEVER combine multiple capabilities into a single reference file
- NEVER add runtime dependencies to package.json
- NEVER use soft negative instructions ("don't", "avoid", "do not") — MUST rewrite as positive "MUST use Y"

## Landmines

- `references/extract-design-system.md` (169 lines): The sacred "$1000 prompt". Lines 15-152 are the verbatim StrackDesignSystemV2. Changing even one word can degrade extraction quality. The prompt was optimized empirically — not theoretically.
- `SKILL.md` (210 lines): 40 lines from the 250-line cap. The routing table (lines 48-56) MUST match the actual reference files. Adding a capability costs ~20 lines of routing + a new reference file.
- Soft negatives in reference files: The course material (Portuguese) uses "não faça" / "do not" naturally. These MUST be rewritten as positive MUST instructions in the skill — research shows negative instructions increase the probability of the prohibited behavior.
- `references/video-media.md`: Newest capability (v2.0). Less battle-tested than the original 5. Google Whisk/Flow URLs may change.

## Patterns

```markdown
<!-- CORRECT: Positive instruction -->
MUST use exact CSS classes from the design system

<!-- WRONG: Negative instruction (backfires) -->
Don't invent new styles
```

```markdown
<!-- CORRECT: One section at a time -->
Build the hero section only. Do not touch other sections.

<!-- WRONG: Full site in one prompt -->
Build the entire site with hero, features, pricing, and footer.
```
