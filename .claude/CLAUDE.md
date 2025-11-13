# Project Context

Content archiving and attribution system for educational resources with focus on formatting guidelines and copywriting best practices.

## User Profile
- Skill level: Technisch versiert, präzise Anforderungen
- Präferenzen: Clean, minimalistisch, regelbasiert
- Language: Deutsch/English mixed, direkte Kommunikation

## Project Structure
- `/sources/`: Original source materials (Kleist, Lee Robinson essays, etc.)
- `/output/`: Reference guides, author portraits, archived content
  - `author_portraits.md`: Consolidated author biographies (focus on PERSON)
  - `*_reference.md`: Comprehensive guides distilled from source materials
  - `/leerob/`: Lee Robinson's essays
- `/meta/`: Writing process documentation (4-stage iterative process)
  - `1_thinking.md`: Pre-writing - purpose, reader, message, structure
  - `2_drafting.md`: First draft - door closed, momentum, discovery
  - `3_revising.md`: Restructure - door open, logic, 10% cut
  - `4_refining.md`: Polish - clarity, word choice, final details
- `/documents/`: Technical documentation and guides (legacy)

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
- **Maximum 2 lines (30-50 words)** - extreme compression to essence
- Only most important career points: Origin → Breakthrough → Current approach
- Background tags provide biographical context - where they came from, what shaped them, their journey
- Works may be mentioned but only to illuminate the person, never as the primary focus
- For institutions (The Economist, Anthropic), describe the history and character of the institution itself

**Examples:**
- ❌ Bad: "Barbara Minto's Pyramid Principle revolutionized business communication..."
- ✅ Good: "Barbara Minto boldly applied to Harvard Business School without an undergraduate degree, graduating in 1963 as one of eight women in 600 men. McKinsey hired her as their first female MBA consultant, where she developed the Pyramid Principle and MECE framework."

### Decade Assignment Examples
- Paul Graham: #2000s (Y Combinator era)
- Barbara Minto: #1970s (McKinsey/Pyramid Principle)
- Lee Robinson: #2020s (current peak at Cursor)
- Stephen King: #1970s (breakthrough with Carrie, peak horror era)
- Rolf Hichert: #2000s (IBCS development)
- Heinrich von Kleist: #1800s (active 1777-1811)
- Anthropic: #2020s (Claude development)

## Content Types and Guidelines

### Reference Guides (`/output/*_reference.md`)
**Purpose:** Comprehensive, educational reference documents distilled from source materials

**Structure:**
- Title + Overview
- Table of Contents (10-20 sections)
- Part I, II, III... (major sections)
- Conclusion with synthesis from all sources
- Full attribution at end (all 5 tags)

**Length guidance:**
- Standard: 20-40 KB (Stephen King, Minto, Economist)
- Comprehensive: 100 KB+ when completeness requested (Hichert SUCCESS)
- Completeness before brevity when specified

**Key principles:**
- Synthesize, don't just summarize
- Include concrete examples and checklists
- Cross-reference related concepts
- Make actionable and practical

### Author Portraits (`/output/author_portraits.md`)
**Critical rule:** Focus on the PERSON, not their works

**What to include:**
- Birth, early life, education (forming years)
- Career journey with struggles and breakthroughs
- Character traits and driving motivations
- Key relationships and influences (e.g., Goethe's rejection of Kleist)
- Impact and legacy (how others see them)
- Tragic or remarkable life events that shaped them

**What to avoid:**
- Describing their works in detail
- Academic summaries of their theories
- Lists of publications
- Focus on output rather than person

**Language:**
- German for German authors (Kleist) if appropriate
- English for international figures
- Match the cultural context

### Source Materials (`/sources/`)
**For public domain content:**
- Archive 1:1 verbatim when copyright-free (e.g., Kleist 1811)
- Full original text preserved
- Minimal formatting changes
- Attribution metadata at end

**For copyrighted content:**
- Reference guides only (fair use, educational)
- Never reproduce copyrighted work verbatim
- Distill principles and create new synthesis

## The 4-Stage Iterative Writing Process

**Core philosophy:** Writing is iterative. Separate thinking from drafting, drafting from revising, revising from refining.

### Stage 1: THINKING (Before Writing)
**Goal:** Clarify before you write
- Answer 3 fundamental questions: Why? For whom? What message?
- Know your purpose (inform, persuade, explore)
- Understand your reader deeply
- Define your one message (complete sentence)
- Choose structure (Pyramid, SCQA, Discovery mode)
- **Output:** Clear plan, ready to draft

### Stage 2: DRAFTING (First Draft)
**Goal:** Get words on page without self-censorship
- **King's "Door Closed":** Write for yourself, not audience
- Two modes: Discovery (Kleist - finding your message) or Structured (Minto - filling framework)
- Maintain momentum - don't edit while drafting
- Accept imperfection - first drafts are for getting it down, not right
- **Output:** Complete rough draft, ready to revise

### Stage 3: REVISING (Restructure & Strengthen)
**Goal:** Make it work for readers
- **King's "Door Open":** Now write for readers
- Fix structure (SCQA, Pyramid logic)
- Test logic (Minto's MECE, vertical/horizontal relationships)
- **Cut 10%:** Kill your darlings ruthlessly
- Improve flow and transitions
- Get feedback from trusted readers
- **Output:** Solid structure, sound logic, tight content

### Stage 4: REFINING (Polish to Excellence)
**Goal:** Perfect every detail
- Sentence-level clarity (every sentence crystal clear)
- Word choice (simple, precise, concrete - Economist standards)
- Eliminate weak constructions (adverbs, passive voice, hedging)
- Rhythm and pace (vary sentence length, read aloud)
- Final checks (grammar, consistency, typos)
- **Output:** Publication-ready excellence

**Key insight:** Premature optimization kills progress. Don't polish sentences before structure is solid. Don't edit while drafting. Each stage has its purpose.

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

**Session 2025-11-13 (Part 3 - YouTube System Enhancement):**
- **Major accomplishment:** YouTube extraction system now fully dynamic and automated
  - Extended `fetch_youtube_transcript.py` with automatic metadata extraction
  - Added `channel_name` extraction via oEmbed API `author_name` field
  - Added `published_date` (YYYY-MM-DD) and `published_formatted` ("Month YYYY") extraction
  - Script uses oEmbed API + HTML scraping for complete metadata (no API key needed)
  - Graceful degradation: Works without requests library, returns null for metadata
- **Compression requirement:** Drastically reduced verbosity by 60%
  - Author Portraits: 4 lines → 2 lines (30-50 words) in `/output/author_portraits.md`
  - #background Tags: 120+ words → 3 sentences (40-60 words) in documents
  - Updated ALL existing portraits (Paul Graham, Barbara Minto, Lee Robinson, etc.)
  - Updated both YouTube extraction documents with compressed #background tags
- **Documentation enhancement:** Complete guideline updates
  - `youtube_extraction_guidelines.md`: Clear separation of Author Portrait vs. #background tag
  - `/youtube` command: Explicit instruction "MAXIMUM 3 SENTENCES (40-60 words)"
  - Added good vs. bad examples with word counts
  - CLAUDE.md: Updated with new compression rules
- **Document formatting fixes:**
  - Added newlines between metadata tags for clean Markdown preview
  - Corrected publication dates (Daniel Miessler: September 2025, Anthropic: September 2024)
- **Two YouTube extractions completed:**
  - Daniel Miessler: "Building Your Own Unified AI Assistant Using Claude Code"
  - Anthropic: "AI prompt engineering: A deep dive" (Roundtable with 4 participants)

**Key learnings:**
- **Compression is clarity:** 60% reduction forced focus on essence, not detail
- **Metadata automation:** oEmbed API + HTML scraping provides complete info without manual entry
- **Author Portrait ≠ #background tag:** Two distinct artifacts with different purposes
  - Author Portrait: For `/output/author_portraits.md` collection (2 lines)
  - #background tag: For document metadata (3 sentences)
- **Edge case handling:** Roundtable videos use channel owner as #author, list participants separately
- **Dynamic date extraction:** System now pulls correct publish dates automatically from YouTube

**Technical learnings:**
- oEmbed API provides: `title`, `author_name` (channel)
- HTML scraping needed for: `uploadDate` (JSON-LD structured data)
- Regex pattern: `r'"uploadDate":"(\d{4}-\d{2}-\d{2})'`
- Windows command line: Pipe handling issues with Python JSON output
- Script return structure includes all metadata in single JSON response

**Pitfalls avoided:**
- Initially shortened Author Portraits when user meant #background tags in documents
- Recognized distinction between two artifacts after clarification
- Updated both artifacts appropriately with different compression targets

**Critical findings:**
- PAI (Personal AI Infrastructure) mobility requires centralized context system
- All templates now in `~/.claude/context/projects/formatting-guidelines/`
- Script modifications tested immediately on both videos to verify functionality
- Compression improves readability - long biographical paragraphs lose focus

**Next priorities:**
- YouTube extraction system fully automated and ready for production use
- All future extractions will automatically use new compression rules
- System dynamically extracts: date, title, channel name, transcript
- No manual metadata entry required going forward

**Session 2025-11-13 (Part 4 - YouTube Command Architecture Fix):**
- **Problem identified:** /youtube command lost context after loading transcript
  - User requests after transcript load became separate conversations
  - All guidelines (70-110 lines, numbered list, action-oriented) were lost
  - Command context did not persist through processing
- **Solution implemented:** Dual-mode architecture for /youtube command
  - **Mode 1 (Interactive):** `/youtube <url>` - loads transcript, waits for queries
  - **Mode 2 (Direct Extraction):** `/youtube <url> "prompt"` - loads and processes immediately
  - Mode 2 keeps command context active throughout execution
  - All guidelines remain enforced: OUTPUT_FORMAT, PROJECT_EXTRACTION_GUIDELINES
- **Command updates (537 lines total):**
  - Added Usage Modes section explaining both modes
  - Updated argument-hint: `<youtube-url> [optional-prompt]`
  - Rewrote INSTRUCTIONS with Step 0 (mode detection logic)
  - Added Technical Implementation Notes (argument parsing)
  - Added Example Workflows showing both modes in action
  - Added Session Start Verification section
- **Session Start Verification:**
  - Command must work reliably without prior context
  - All guidelines explicitly stated (no assumptions)
  - Self-contained: paths absolute, examples embedded
  - Quality checklist for self-verification
  - Testing protocol documented
- **Critical insight:** Slash commands lose context when follow-up is in normal conversation
  - Original: `/youtube <url>` → [load] → User asks → separate conversation (guidelines lost)
  - Fixed: `/youtube <url> "prompt"` → [load + process] → command context active (guidelines enforced)

**Key learnings:**
- **Command architecture matters:** Follow-up prompts outside command context lose all guidelines
- **Mode 2 solves persistence:** Optional second argument keeps command active during processing
- **Self-contained commands:** Must work at session start without explanation
- **Testing requirement:** User insisted command work "without context at session start" - all guidelines embedded

**Technical learnings:**
- Argument parsing: `$ARGUMENTS` split into URL (first token) + optional prompt (remaining text)
- Mode detection: Check if text exists after URL → Mode 2, else Mode 1
- Python script call: Only URL passed to fetch_youtube_transcript.py, not full $ARGUMENTS

**Pitfalls avoided:**
- Initially tried to "fix" output style without understanding root cause
- Recognized the architectural problem: context loss between command and follow-up
- User correctly diagnosed: "Guidelines should persist when command is running"

**Critical findings:**
- /youtube command now 537 lines (from ~370) - necessary for complete documentation
- Session Start Verification section ensures reliability without context
- All paths absolute, all examples concrete, all guidelines explicit

**Next priorities:**
- Test Mode 2 with real extraction to verify guidelines enforcement
- Update other commands that might have similar context-loss issues
- Consider Mode 2 pattern for other interactive commands

**Session 2025-11-13 (Part 5 - Lessons Learned & Simplicity):**
- **Key learning:** User wants EINFACHHEIT, nicht Optimierung
- Over-engineering Fehler: Vorschlag komplexer Skills-Migration für simple Modularitäts-Frage
- **Correct answer:** Skills statt Slash Commands für Multi-Step-Workflows (offiziell dokumentiert)
- **But:** Aktueller dual-mode Command funktioniert gut - "don't fix what isn't broken"
- Migration nur wenn wirklich separate kombinierbare Module benötigt werden
- Pitfall: Zu viele Features auf einmal (Token Reduction, Code Execution, etc.) ohne User-Request
- **What to do better:** Erst einfache Antwort, dann fragen ob Details gewünscht
- Current solution (537-line dual-mode command) ist angemessen für den Use-Case
- No changes needed unless user explicitly requests modularization

**Critical findings:**
- User's need for simplicity > optimization
- Working solution > theoretically better architecture
- Answer the question asked, not the question you think they should ask
