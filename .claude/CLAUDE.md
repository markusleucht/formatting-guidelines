# Project Context

Content archiving and attribution system for educational resources with focus on formatting guidelines and copywriting best practices.

## User Profile
- Skill level: Technisch versiert, präzise Anforderungen
- Präferenzen: Clean, minimalistisch, regelbasiert
- Language: Deutsch/English mixed, direkte Kommunikation

## Project Structure
- `/leerob/`: Lee Robinson's essays on developer topics
- `/documents/`: Technical documentation and guides
- `CONTENT_ATTRIBUTION_RULES.md`: Core attribution guidelines
- `author_portraits.md`: Author biographies

## Key Rules

### Content Attribution Format
ALL externally sourced content must include metadata at END of document:

```
---

#author: [Name or Institution]
#published: [Month Year]
#source: [URL]
#background: [Brief paragraph]
#decade: #[decade of peak influence]
```

**Critical:**
- Tags use `#` prefix with lowercase (e.g., `#author:` not `#Author:`)
- Month + Year required in #published (never just year)
- Institutions treated as authors (Anthropic, The Economist, etc.)
- #decade represents peak influence, NOT birth year
- Metadata goes at END, not beginning

### Decade Assignment Examples
- Paul Graham: #2000s (Y Combinator era)
- Barbara Minto: #1970s (McKinsey/Pyramid Principle)
- Lee Robinson: #2020s (current peak at Cursor)
- Anthropic: #2020s (Claude development)

## Important Paths
- Project root: `/Users/markus/formatting_guidelines/`
- Skills installed: `~/.claude/skills/pdf/` and `~/.claude/skills/skill-creator/`
- GitHub: https://github.com/markusleucht/formatting-guidelines

## Session Ending Protocol

When session ends, follow this protocol:

### 1. Analyze Session
- What worked well?
- What mistakes were made?
- What to improve next time?

### 2. Update This File
Add to Session History:
- Date + what was accomplished
- Key learnings and insights
- Pitfalls avoided
- Critical findings (bugs, issues)
- Technical learnings
- Next priorities

### 3. Git Commit & Push (Using GitHub CLI)

**Standard commit and push:**
```bash
git status
git add .
git commit -m "$(cat <<'EOF'
[Title: What was achieved]

- [Main change 1 with details]
- [Main change 2 with details]
- [Bug fixes / improvements]

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude <noreply@anthropic.com>
EOF
)"
git push origin main
```

**Create new repository (first time only):**
```bash
gh repo create [name] --public --source=. --remote=origin --push
```

**GitHub CLI commands available:**
- `gh repo create` - Create new repository
- `gh pr create` - Create pull request
- `gh issue create` - Create issue
- `gh repo view` - View repository details

## Session History

**Session 2025-11-13:**
- Set up content attribution system with proper metadata format
- Created author portraits (Paul Graham, Barbara Minto, Lee Robinson, Rolf Hichert, The Economist)
- Established 5-tag system: #author, #published, #source, #background, #decade
- Installed PDF and skill-creator skills to user's personal directory
- Archived Lee Robinson essays and Anthropic documentation
- Created vision-based table extraction guide
- Key learning: Metadata belongs at END of documents as reference, not at top
- Critical finding: Tags need `#` prefix and lowercase format for consistency
- Next priority: Use system for future content archiving
