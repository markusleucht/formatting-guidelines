# Agent Skills - Claude Documentation

## Overview

Agent Skills are modular capabilities extending Claude's functionality. Each Skill packages instructions, metadata, and optional resources that Claude uses automatically when relevant.

## Why Use Skills

Skills provide domain-specific expertise as reusable, filesystem-based resources. Key benefits include:

- **Specialization**: Tailor capabilities for specific tasks
- **Efficiency**: Create once, use automatically across conversations
- **Composition**: Combine multiple Skills for complex workflows

Unlike one-off prompts, Skills eliminate repetitive guidance by loading on-demand.

## How Skills Work

Skills operate within Claude's VM environment with filesystem access. They use **progressive disclosure**, loading information in stages rather than consuming context upfront.

### Three Content Levels

**Level 1: Metadata (Always Loaded)**
- YAML frontmatter with name and description
- Minimal token cost (~100 per Skill)
- Enables discovery without context penalty

**Level 2: Instructions (Loaded When Triggered)**
- Main SKILL.md body with procedures and guidance
- Loaded via bash when Skill matches user request
- Typically under 5k tokens

**Level 3: Resources and Code (Loaded As Needed)**
- Additional markdown files, scripts, templates
- Accessed only when referenced
- Scripts execute without loading code into context

### Architecture

Skills exist as filesystem directories. When triggered, Claude reads SKILL.md via bash. Referenced files load similarly. Executable scripts run through bash, returning only output—never loading code into the context window.

## Where Skills Work

| Platform | Pre-built Skills | Custom Skills |
|----------|-----------------|---------------|
| **Claude API** | Yes (via skill_id) | Yes (upload via API) |
| **Claude Code** | — | Yes (filesystem-based) |
| **Agent SDK** | — | Yes (via configuration) |
| **Claude.ai** | Yes (automatic) | Yes (zip upload) |

### API Requirements

Using Skills via Claude API requires three beta headers:
- `code-execution-2025-08-25`
- `skills-2025-10-02`
- `files-api-2025-04-14`

## Skill Structure

Every Skill requires a `SKILL.md` file with YAML frontmatter:

```yaml
---
name: your-skill-name
description: What this does and when to use it
---

# Skill Name
[Instructions, examples, guidance]
```

**Naming rules**:
- Maximum 64 characters
- Lowercase letters, numbers, hyphens only
- Cannot contain "anthropic" or "claude"

## Pre-built Agent Skills

Anthropic provides four production Skills:
- **PowerPoint (pptx)**: Create and edit presentations
- **Excel (xlsx)**: Build spreadsheets with data analysis
- **Word (docx)**: Generate formatted documents
- **PDF (pdf)**: Create PDF reports

## Security Considerations

Skills from untrusted sources pose risks. They can direct Claude to invoke tools or execute code unexpectedly. Recommendations:

- Audit all bundled files thoroughly
- Review scripts for unusual patterns
- Be cautious with external data fetching
- Treat Skills like software installations

## Limitations

**Cross-surface Availability**
- Custom Skills don't sync between surfaces
- API uploads don't appear in Claude.ai
- Separate management required per platform

**Sharing Scope**
- Claude.ai: Individual user only
- Claude API: Workspace-wide access
- Claude Code: Personal or project-based

**Runtime Constraints**
- **Claude API**: No network access; pre-installed packages only
- **Claude Code**: Full network access available
- **Claude.ai**: Variable access depending on user settings

## Next Steps

- **Getting Started**: See the [quickstart tutorial](/en/docs/agents-and-tools/agent-skills/quickstart)
- **API Implementation**: Review [Skills guide](/en/docs/build-with-claude/skills-guide)
- **Best Practices**: Consult [authoring guidelines](/en/docs/agents-and-tools/agent-skills/best-practices)
- **Code Examples**: Explore the [Skills cookbook](https://github.com/anthropics/claude-cookbooks/tree/main/skills)

---

#author: Anthropic
#published: January 2025
#source: https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview
#background: Anthropic is an AI safety company that builds advanced AI systems, including the Claude family of models. Known for pioneering research in AI alignment and developing tools for safer AI deployment.
#decade: #2020s
