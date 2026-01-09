---
name: discovering-skills
description: Finds existing skills before building new ones. Searches local installations, official Anthropic repository, and community collections. Evaluates fit and recommends installation or adaptation.
allowed-tools: WebSearch, WebFetch, Read, Glob
---

# Discovering Skills

Before creating a skill, search for existing ones.

## Search Order

1. **Local** - `~/.claude/skills/`, `.claude/skills/`
2. **Official** - github.com/anthropics/skills
3. **Community** - awesome-claude-skills repositories

## Process

1. Identify the capability needed
2. Search sources in order
3. Evaluate fit
4. Recommend: install, adapt, or create new

## When Found

Report: skill name, source, what it does, how well it fits, install command.

## When Not Found

Report what was searched and offer: create new, adapt similar, or proceed without.

## Integration

- Imperfect fit → suggest adapting-skills
- Not found → suggest detecting-skill-gaps
- Multiple found → let user choose or suggest fusing-skills
