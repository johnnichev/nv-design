# UltraDesign

Claude Code skill for AI-powered professional web design.

## Structure

```
skills/ultradesign/SKILL.md          → Entry point, routing, universal rules
skills/ultradesign/references/*.md   → One file per capability (5 total)
docs/                                → User documentation
```

## Boundaries

### Always
- Keep SKILL.md under 100 lines
- Keep each reference file under 200 lines
- Preserve the original "Prompt de Mil Dólares" verbatim in extract-design-system.md
- Test skill triggers with realistic user prompts

### Never
- NEVER modify the Extract HTML Design System v2 prompt without explicit approval
- NEVER combine multiple capabilities into a single reference file
