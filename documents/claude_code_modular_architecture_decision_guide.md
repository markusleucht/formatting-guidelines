# Claude Code — Modular Architecture Decision Guide

## 1. Understand the Four Capabilities and Their Core Purpose

Each capability in Claude Code serves a distinct architectural role:

**MCP Servers** connect to external integrations (databases, Jira, APIs). Bundle multiple services together and expose them with specific capabilities.

**Subagents** isolate and parallelize workflows. Context is NOT persisted after execution. Use when you want parallel execution and can lose context afterward.

**Skills** provide automatic agent-triggered behavior with dedicated modular structure. Context-efficient via progressive disclosure (metadata → instructions → resources). Highly composable — can call other skills, MCP servers, slash commands, and subagents.

**Slash Commands** are manual triggers for one-off tasks. Simple, explicit control when you want the agent to execute on your command, not automatically.

## 2. The Modularity Distinction — Skills Win Here

Skills have the HIGHEST modularity due to their dedicated directory structure:

```
.claude/skills/[skill_name]/
├── SKILL.md           # Core instructions
├── workflows/         # Task-specific implementations
└── assets/            # Templates, references
```

**Why this matters:** Skills give you a standardized, repeatable way to build modular solutions that agents can invoke automatically. They aren't just "smart prompts" — they're architectural components.

Slash commands CAN be modular if you build custom directory structures yourself (e.g., `.claude/commands/[category]/[command].md`), but this is manual organization. Skills provide structure out of the box.

**Critical insight:** Modularity enables composability. Skills can combine MCP servers, call other skills, trigger subagents, and use slash commands. This makes skills the architectural "glue" for complex workflows.

## 3. The Core Decision Framework — Trigger vs. Integration vs. Isolation

Use this decision tree:

**Step 1: Is this an external integration?**
- YES → MCP Server (database queries, Jira, weather APIs, third-party services)
- NO → Continue to Step 2

**Step 2: Do you need parallelization with isolated context?**
- YES → Subagent (security audits, fixing failing tests at scale, parallel development)
- NO → Continue to Step 3

**Step 3: Should this happen automatically or manually?**
- AUTOMATIC → Skill (PDF extraction, style guide violations, consistent behavior)
- MANUAL → Slash Command (generate commit messages, create React components, one-off tasks)

**Step 4: Do you need to compose multiple capabilities?**
- YES → Skill (combine MCP + subagents + other skills into a unified workflow)
- NO → Keep it simple (single MCP server, single slash command, single subagent)

## 4. When Skills Are the Right Choice — Context Efficiency + Automatic Behavior

Skills shine when you want:

1. **Automatic triggering** — Agent decides when to use the skill based on context
2. **Context efficiency** — Progressive disclosure prevents exploding context window (unlike MCP servers which load everything on bootup)
3. **Modularity** — Dedicated directory structure for repeatable solutions
4. **Composability** — Combine multiple tools (MCP, subagents, other skills) into one workflow

**Example use cases:**
- Automatically extract text/data from PDFs whenever working with PDF files
- Detect style guide violations during code review
- Apply consistent formatting rules across documentation
- Implement multi-step workflows that should trigger automatically (e.g., test → fix → commit)

**When NOT to use skills:**
- Simple one-step tasks → Use slash commands instead
- External integrations → Use MCP servers
- Need parallelization → Use subagents
- Rarely used workflows → Keep as slash commands for explicit control

## 5. Skills vs. Slash Commands — The Nuance

These two are VERY similar in capability. The key difference:

**Skills:**
- Agent-triggered (automatic)
- Dedicated modular structure (`.claude/skills/`)
- Progressive disclosure (context-efficient)
- Best for: Repeat behavior you want encoded permanently

**Slash Commands:**
- User-triggered (manual)
- Simple markdown files (`.claude/commands/`)
- Full instructions loaded immediately
- Best for: One-off tasks you want explicit control over

**The critical question:** How often do you want this to happen?

- **Always/Often** → Skill (e.g., always extract PDF text when encountering PDFs)
- **Sometimes/Rarely** → Slash Command (e.g., manually generate commit message when I ask)

**Common mistake:** Converting ALL slash commands to skills. This removes explicit control. Keep manual tasks as slash commands.

## 6. Modularity Enables Multi-Step Workflows — Use Progressive Complexity

Skills support progressive complexity through their directory structure:

```
.claude/skills/git-workflow/
├── SKILL.md                   # Core instructions
├── workflows/
│   ├── branch.md              # Create branch workflow
│   ├── commit.md              # Commit workflow
│   ├── pr.md                  # Pull request workflow
└── assets/
    └── commit_template.txt    # Reusable templates
```

**How to design modular skills:**

1. **Start with SKILL.md** — Core instructions and when to trigger
2. **Break down into workflows/** — Separate files for distinct tasks
3. **Store reusables in assets/** — Templates, examples, reference data
4. **Use composition** — Call MCP servers, other skills, subagents as needed

**Example modular workflow:**

```markdown
# SKILL.md - Git Workflow Manager

When user mentions git operations (branch, commit, PR), trigger this skill.

## Workflows

- branch.md: Create feature branch from main
- commit.md: Stage changes, generate message, commit
- pr.md: Push branch, create PR with description

## Composition

Uses:
- gh MCP server for GitHub API calls
- conventional-commits skill for message format
- code-review subagent for pre-PR validation
```

This modular approach lets you build complex workflows from smaller components.

## 7. Composability is the Key to Power — Skills Can Orchestrate Everything

Skills have the HIGHEST composability:

**Skills can use:**
- ✅ Other skills
- ✅ MCP servers
- ✅ Subagents
- ✅ Slash commands (via prompts)

**This enables orchestration patterns:**

```
Main Skill
├── Call MCP Server (fetch data)
├── Call Subagent (parallel processing)
├── Call Another Skill (specialized logic)
└── Output results
```

**Example:** A "documentation generator" skill could:
1. Call Jira MCP server to fetch requirements
2. Trigger code-explorer subagent to analyze codebase
3. Call markdown-formatter skill to structure output
4. Generate final documentation

**Why this matters for modularity:** You build small, focused components (skills, MCP servers) and compose them into complex workflows. This is true modular architecture.

## 8. Context Management — Progressive Disclosure vs. Full Load

**MCP Servers** load ALL capabilities on bootup → Explodes context window

**Skills** use progressive disclosure:
1. Metadata (description, triggers) loaded first
2. SKILL.md instructions loaded when triggered
3. Workflow files loaded only when specific task identified
4. Assets pulled in only when referenced

**Why this enables modularity:** You can build large, comprehensive skills without paying context cost upfront. Agent only loads what it needs when it needs it.

**Design principle:** Structure skills with clear separation:
- Keep SKILL.md focused (high-level instructions)
- Move detailed logic to workflows/
- Store data/templates in assets/

This ensures context efficiency even as your skill grows in complexity.

## 9. When to Use Multiple Capabilities Together — Composition Patterns

**Pattern 1: MCP + Skill**
- MCP provides external data access
- Skill orchestrates how to use that data
- Example: Database MCP + data-analysis skill

**Pattern 2: Subagent + Skill**
- Skill identifies when parallel work needed
- Launches multiple subagents for isolated execution
- Example: Test-runner skill launching parallel test-fix subagents

**Pattern 3: Slash Command + Skill**
- Slash command as explicit trigger
- Skill handles automatic follow-up behavior
- Example: `/start-feature` command triggers feature-development skill

**Pattern 4: Skill + Skill**
- Break complex workflow into focused sub-skills
- Main skill orchestrates by calling others
- Example: Code-review skill calls linting-skill + security-audit-skill + test-coverage-skill

**Key principle:** Start simple (single capability), add composition when complexity justifies it. Don't over-engineer early.

## 10. The Decision Flowchart — Quick Reference

```
Is this an EXTERNAL integration?
├─ YES → MCP Server
└─ NO
   │
   Do you need PARALLELIZATION?
   ├─ YES → Subagent
   └─ NO
      │
      Should this happen AUTOMATICALLY?
      ├─ YES → Skill
      └─ NO
         │
         Is this a ONE-OFF task?
         ├─ YES → Slash Command
         └─ NO
            │
            Do you need to COMPOSE multiple tools?
            ├─ YES → Skill (orchestration)
            └─ NO → Slash Command (keep it simple)
```

**Remember:**
- **Automatic + Modular = Skill**
- **Manual + Simple = Slash Command**
- **External = MCP**
- **Parallel = Subagent**

When in doubt, start with the simplest solution (slash command) and evolve to skills when you find yourself repeating the pattern.

---

> Modularity isn't about using every feature — it's about choosing the right architectural component for each job and composing them when complexity demands it.

---

#author: IndyDevDan
#published: October 2025
#source: https://www.youtube.com/watch?v=kFpLzCVLA20
#background: IndyDevDan is a software engineer who has been using Claude Code since its February release and claims to have generated more code with it in one year than in his previous 15 years as an engineer. He focuses on practical engineering tutorials and Claude Code ecosystem education.
#decade: #2020s
