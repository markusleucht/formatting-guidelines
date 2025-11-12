# Agent Skills - Claude Code Documentation

## Overview

Agent Skills extend Claude's capabilities in Claude Code through modular, discoverable capabilities. Each skill contains a `SKILL.md` file with instructions plus optional supporting files like scripts and templates.

**Key distinction**: Skills are "model-invoked"—Claude autonomously determines when to use them based on your request and the skill's description, unlike slash commands which are user-triggered.

## Creating Skills

### Storage Locations

**Personal Skills** (`~/.claude/skills/`): Individual workflows, experimental skills, and productivity tools available across all projects.

**Project Skills** (`.claude/skills/`): Team-shared expertise, project-specific knowledge, and utilities checked into git for automatic team availability.

**Plugin Skills**: Bundled with Claude Code plugins and work identically to personal and project skills.

## SKILL.md Structure

Every skill requires a `SKILL.md` file with YAML frontmatter:

```yaml
---
name: skill-name-lowercase
description: Clear description of what skill does and when to use it
---
```

Key requirements:
- `name`: lowercase letters, numbers, hyphens only (max 64 characters)
- `description`: explains functionality and triggers (max 1024 characters)

The description field is critical for discovery. It should specify "both what the Skill does and when Claude should use it."

## Supporting Files

Skills can include optional files alongside `SKILL.md`:
- Reference documentation
- Example files
- Scripts (in `scripts/` subdirectory)
- Templates (in `templates/` subdirectory)

Claude reads these progressively, only accessing them when needed.

## Tool Restrictions

Use the `allowed-tools` frontmatter field to limit Claude's tool access:

```yaml
allowed-tools: Read, Grep, Glob
```

This enables read-only skills or security-sensitive workflows without requiring permission requests. Note: `allowed-tools` is Claude Code-specific only.

## Discovery and Testing

Skills are automatically discovered from all three sources. Test your skill by asking questions matching your description—Claude will autonomously activate it if relevant.

## Common Issues

**Skills not activating**: Ensure your description is specific, includes both capabilities and usage triggers, and uses concrete terminology users would mention.

**File location problems**: Verify correct paths:
- Personal: `~/.claude/skills/skill-name/SKILL.md`
- Project: `.claude/skills/skill-name/SKILL.md`

**YAML syntax errors**: Validate frontmatter formatting with proper opening/closing `---` delimiters and correct indentation (spaces, not tabs).

## Team Sharing

**Recommended approach**: Distribute through plugins added to marketplaces.

**Direct sharing**: Commit project skills to git at `.claude/skills/`. Team members automatically gain access upon pulling changes.

## Best Practices

Keep skills focused on single capabilities. Write descriptions that help Claude understand specific triggers—include file types, formats, or operations users would mention. Test with teammates and document version history for tracking changes.

**Poor description**: "Helps with documents"

**Strong description**: "Extract text and tables from PDF files, fill forms, merge documents. Use when working with PDF files or when user mentions PDFs."

## Maintenance

Edit skills by modifying `SKILL.md` directly. Changes take effect after restarting Claude Code. Remove skills by deleting the directory and committing changes to git.

---

#author: Anthropic
#published: January 2025
#source: https://code.claude.com/docs/en/skills
#background: Anthropic is an AI safety company that builds advanced AI systems, including the Claude family of models. Known for pioneering research in AI alignment and developing tools for safer AI deployment.
#decade: #2020s
