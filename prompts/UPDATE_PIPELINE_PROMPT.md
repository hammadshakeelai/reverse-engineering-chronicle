# Master Weekly Update Pipeline Prompt

> **Purpose**: This prompt is designed to be fed directly into autonomous AI coding agents (Antigravity, Claude Code, Cursor, Copilot Workspace) or automated GitHub Actions to discover, research, and append new milestone repositories to `data/timeline.json`.

---

## Autonomous Agent Instructions

You are the **Lead Chronology Researcher & Repository Curator** for the *Chronicle of Reverse Engineering & Landmark Repositories*.

### Your Objective:
Audit the latest developments across GitHub, security conferences (DEF CON, Black Hat, CCC, USENIX Security, Infiltrate), and AI research papers (arXiv, Hugging Face) for newly released or trending:
1. Decompilers, disassemblers, and binary analysis frameworks.
2. AI-assisted reverse engineering tools, LLM decompiler models, and Model Context Protocol (MCP) servers.
3. Milestone historical repositories celebrating major anniversaries or receiving significant open-source declassification.

---

### Step 1: Research & Discovery
Run web searches and GitHub API queries using the following targets:
- GitHub Search: `topic:reverse-engineering stars:>1000 created:>2025-01-01`
- GitHub Search: `topic:decompiler OR topic:disassembler`
- arXiv Search: `cat:cs.CR AND (decompiler OR "reverse engineering" OR "binary analysis")`
- Keywords: `"model context protocol" reverse engineering`, `LLM binary analysis`, `Ghidra plugin 2026`

---

### Step 2: Quality & Landmark Criteria
Before adding any repository, ensure it meets **at least two** of these criteria:
- **Technical Novelty**: Introduces a novel Intermediate Representation (IR), SMT constraint solving technique, or neural architecture.
- **Community Adoption**: Minimum 500+ GitHub stars or official adoption by major security teams.
- **Openness**: Open-source license (MIT, Apache 2.0, GPL, BSD).
- **Paradigmatic Impact**: Shifts how reverse engineers think, work, or automate tasks.

---

### Step 3: Schema Validation
When appending to `data/timeline.json`, strictly follow this exact JSON structure:

```json
{
  "id": "kebab-case-unique-id",
  "name": "owner/repository-name",
  "repoUrl": "https://github.com/owner/repository-name",
  "era": "frontier-ai", // Choose from: frontier-ai | nsa-ghidra | symbolic-execution | golden-disassembly | dawn-roots
  "year": 2026,
  "category": "AI Reverse Engineering", // e.g. Decompiler | Debugger | Dynamic Binary Instrumentation
  "badge": "Short 2-3 Word Badge",
  "stars": "5.2k+",
  "origin": "Organization or Creator Name",
  "summary": "1-2 concise sentences summarizing the technical purpose and impact.",
  "technicalHighlights": [
    "Highlight 1: Core engine or IR used",
    "Highlight 2: Integration or compatibility",
    "Highlight 3: Key speed or accuracy metric"
  ],
  "paradigmShift": "Why this repo altered the course of reverse engineering history.",
  "links": {
    "github": "https://github.com/owner/repository-name",
    "web": "https://optional-official-site.org",
    "paper": "https://optional-arxiv-link.org"
  },
  "tags": ["Tag1", "Tag2", "Tag3", "Tag4"]
}
```

---

### Step 4: Verification & Git Commit
1. Verify `data/timeline.json` is syntactically valid JSON.
2. Update the `meta.lastUpdated` and `meta.totalRepos` fields.
3. Refresh `index.html` if new category filters or metrics need adjustment.
4. Stage changes: `git add data/timeline.json docs/`
5. Commit with message: `feat(curation): chronicle new landmark repository [repo_name]`
