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
- **#background describes the AUTHOR'S LIFE, not the work** - biographical context about the person/institution, their journey, character, and impact as human beings

### Author Portraits Philosophy
**Focus on the PERSON, not the work:**
- Author portraits describe the human being - their life, personality, struggles, achievements
- Background tags provide biographical context - where they came from, what shaped them, their journey
- Works may be mentioned but only to illuminate the person, never as the primary focus
- For institutions (The Economist, Anthropic), describe the history and character of the institution itself

**Examples:**
- ❌ Bad: "Barbara Minto's Pyramid Principle revolutionized business communication..."
- ✅ Good: "Barbara Minto started as a secretary earning $400/month, boldly applied to Harvard Business School without an undergraduate degree..."

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

**Session 2025-11-13 (Part 1):**
- Set up content attribution system with proper metadata format
- Created author portraits (Paul Graham, Barbara Minto, Lee Robinson, Rolf Hichert, The Economist)
- Established 5-tag system: #author, #published, #source, #background, #decade
- Installed PDF and skill-creator skills to user's personal directory
- Archived Lee Robinson essays and Anthropic documentation
- Created vision-based table extraction guide
- Key learning: Metadata belongs at END of documents as reference, not at top
- Critical finding: Tags need `#` prefix and lowercase format for consistency

**Session 2025-11-13 (Part 2 - Continued):**
- **Major accomplishment:** Created comprehensive reference guides from all sources
  - Stephen King "On Writing" (20 KB)
  - Barbara Minto "Pyramid Principle" (40 KB)
  - The Economist Style Guide (40 KB)
  - Rolf Hichert SUCCESS Rules (100 KB) - most comprehensive, with visual descriptions
- **Critical correction:** Fixed #background tags and author portraits
  - **Key insight:** #background must describe AUTHOR'S LIFE, not the work
  - Updated all reference guides with biographical context (birth, education, career journey)
  - Rewrote all author portraits to focus on the PERSON (struggles, character, impact)
  - Documented this philosophy in CLAUDE.md with examples
- **Added Heinrich von Kleist:**
  - Archived 1:1 original German text "Über die allmähliche Verfertigung der Gedanken beim Reden" (public domain)
  - Created German author portrait focused on his tragic life (1777-1811)
  - Proper biographical #background in sources file
- **Reorganized project structure:**
  - Moved Lee Robinson essays from root `/leerob` to `/sources/leerob`
  - All author portraits consolidated in `/output/author_portraits.md`
  - Created `/meta` folder for process documentation
- **Major innovation:** Developed 4-stage iterative writing process
  - Stage 1: THINKING (3,417 words) - Purpose, reader, message, structure
  - Stage 2: DRAFTING (3,119 words) - Door closed, momentum, discovery vs. structured
  - Stage 3: REVISING (3,769 words) - Door open, structure, logic, 10% cut, feedback
  - Stage 4: REFINING (3,526 words) - Sentence clarity, word choice, Economist rules, polish
  - Total: 85 KB, 13,831 words of comprehensive writing guidance
  - Synthesizes all sources: King, Minto, Economist, Hichert, Graham, Kleist

**Key learnings:**
- **Author portraits philosophy:** Focus on the PERSON, not their works - life journey, character, struggles, impact
- **Iterative writing process:** Clear separation of thinking → drafting → revising → refining prevents premature optimization
- **Door Closed/Door Open:** King's metaphor is central - write for self (discovery), rewrite for readers (communication)
- **Completeness before brevity:** When requested (Hichert guide), comprehensive trumps concise
- **Public domain 1:1 copying:** Gemeinfrei content can be archived verbatim (Kleist)

**Technical learnings:**
- Large file handling: Hichert guide (100 KB) required careful extraction from 15 MB PDF
- Attribution consistency: All 5 tags (#author, #published, #source, #background, #decade) must be present
- Bilingual handling: German content (Kleist) integrated seamlessly with English framework

**Pitfalls avoided:**
- Initially wrote work-focused #background tags - caught and corrected systematically
- Could have created only 3 stages - recognized 4 stages (separate revising and refining) is clearer
- Avoided over-compression - kept detail in all process guides for practical usefulness

**Critical findings:**
- Writing process documentation is itself best organized iteratively (stages)
- Each stage needs distinct purpose, mindset, checklist
- Synthesis at end of each guide reinforces cross-source learning

**Next priorities:**
- System is now complete for educational archiving with proper attribution
- `/meta` process guides provide comprehensive writing framework
- Ready for future content additions following established patterns
