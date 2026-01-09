# Meta-Skills

Skills that let agents manage their own capabilities.

## Skills

| Skill | Purpose |
|-------|---------|
| `discovering-skills` | Find existing skills before building new ones |
| `adapting-skills` | Modify skills for new contexts |
| `detecting-skill-gaps` | Recognize when a new skill should be created |
| `connecting-agents` | Delegate to external agents (Manus, etc.) |

## Installation

```bash
# Global (all projects)
cp -r .claude/skills/* ~/.claude/skills/

# Or keep in project (already in .claude/skills/)
```

## Usage

Skills activate automatically. Examples:

- "I need to work with PDFs" → searches for existing PDF skills
- "This skill uses the wrong framework" → forks and adapts it
- "Fill out this web form" → delegates to Manus for browser automation

## License

Apache-2.0
