# Claude-Specific: nv:design

@AGENTS.md
@docs/METHODOLOGY.md
@docs/FAQ.md
@docs/QUICKSTART.md

## Session Management

When context gets heavy (~40 messages or after reading multiple reference files):
1. Update HANDOFF.md with current progress
2. `/clear`
3. Start fresh: "Read HANDOFF.md and continue where I left off"

## Compounding Engineering

When you make a mistake a rule could have prevented:
1. Fix the mistake
2. Add one line to AGENTS.md that prevents it

## Claude-Specific

- The $1000 prompt in `references/extract-design-system.md` is SACRED. Read AGENTS.md boundaries before touching it.
- SKILL.md MUST stay under 250 lines. Run `wc -l skills/nv-design/SKILL.md` after every edit.
- Each reference file MUST stay under 200 lines.
- MUST read the capability's reference file BEFORE starting work — SKILL.md routes to the correct one.
- MUST build one section ("dobra") at a time. Git checkpoint after each.
