# Content Attribution Rules

When collecting and archiving content from external sources (especially higher volumes of text), proper attribution is essential for educational use and reference.

## Required Metadata

Every piece of externally sourced content must include these five fields at the **end** of the document:

1. **author** - Full name of the author or institution name (treat institutions and IP owners as authors)
2. **published** - Original publication date (month and year required, e.g., "October 2015")
3. **source** - Direct link to the original content (can be multiple sources if needed, still use singular tag)
4. **background** - Short paragraph providing context about the author's/institution's expertise and credentials
5. **decade** - Decade representing the author's peak influence (not birth year)

## Design Format

Use **5 tags only** with `#` prefix and lowercase:

```
#author: [Name]
#published: [Month Year]
#source: [URL]
#background: [Brief paragraph]
#decade: #[decade]
```

## Template

```markdown
# [Title]

[Content begins immediately...]

---

#author: [Name or Institution]
#published: [Month Year]
#source: [URL]
#background: [Brief paragraph on expertise/credentials]
#decade: #[decade based on peak influence]
```

## Examples

### Individual Author
```markdown
# Write Like You Talk

The core advice is straightforward...

[Rest of content...]

---

#author: Paul Graham
#published: October 2015
#source: https://paulgraham.com/talk.html
#background: Computer scientist, entrepreneur, and essayist. Co-founder of Y Combinator. Known as a "hacker philosopher" whose essays shaped startup culture.
#decade: #2000s
```

### Institution as Author
```markdown
# Agent Skills Overview

Agent Skills are modular capabilities...

[Rest of content...]

---

#author: Anthropic
#published: January 2025
#source: https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview
#background: Anthropic is an AI safety company that builds advanced AI systems, including the Claude family of models. Known for pioneering research in AI alignment and developing tools for safer AI deployment.
#decade: #2020s
```

### Official Repository
```markdown
# Document Skills Analysis

These skills represent...

[Rest of content...]

---

#author: Anthropic (Official GitHub Repository)
#published: November 2025
#source: https://github.com/anthropics/skills/tree/main/document-skills
#background: Anthropic is an AI safety company that builds advanced AI systems, including the Claude family of models. Known for pioneering research in AI alignment and developing tools for safer AI deployment.
#decade: #2020s
```

## Important Notes

- **Tag Format**: All metadata fields use `#` prefix with lowercase tags (e.g., `#author:` not `#Author:`)
- **Institutions as Authors**: Treat organizations, publications, and IP owners as authors (e.g., The Economist, Anthropic, McKinsey)
- **Month + Year Required**: Always include both month and year in published field (never just year alone)
- **Clean Format**: No asterisks, no bold - just clean text with `#` prefix and colons
- **Singular Tags**: Even for multiple sources, use "#source:" (singular) not "#sources:"
- **Peak Influence**: Decade represents when the author/institution had peak influence, not founding/birth date
