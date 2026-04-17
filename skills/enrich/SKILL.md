---
name: enrich
description: Enrich entity pages in the VT brain. 7-step protocol for people, companies, and projects. Triggers on "enrich [entity]", "create page for [entity]", or "look up [entity]". Adapted from gbrain (Garry Tan).
effort: max
---

# Entity Enrichment

7-step protocol for enriching knowledge about people, companies, and projects in the VT brain.

## When to Fire

- "Enrich [entity name]"
- "Create a page for [person/company]"
- "Look up [entity]"
- "What do we know about [entity]?"
- After signal detection flags a Tier 1 or Tier 2 entity with thin information

## The 7-Step Protocol

### Step 1: Identify the Entity

What type? Person, company, or project?
What tier? Check existing page or use auto-escalation rules.

### Step 2: Check Brain State

Search existing memory files for the entity:
- Check `~/.claude/projects/-Users-vibetokens/memory/` for existing pages
- Check `~/claude-brain/` for SOPs or references that mention them
- Check git history for commits related to the entity

**If page exists:** UPDATE path (add timeline, refine compiled truth if material)
**If no page:** CREATE path (check notability first)

### Step 3: Extract Signal from Source

Don't just capture facts. Capture TEXTURE:
- For people: role, company, relationship to Jason/VT, communication style, what they care about
- For companies: what they do, how they relate to VT, size, industry
- For projects: status, stack, goals, blockers, next steps

### Step 4: External Data Lookups (by tier)

**All tiers:** Brain cross-reference (search memory, check related pages)

**Tier 1 & 2:**
- Web search for public info (WebSearch tool)
- Check Notion for project docs
- Check GitHub for repos/issues
- Check Vercel for deployment status

**Tier 1 only:**
- Deep dive on social media presence
- Full business context
- Relationship mapping

### Step 5: Save Raw Data

If external lookups return substantial data, note the source:
```
[Source: web search, YYYY-MM-DD]
[Source: Notion, YYYY-MM-DD]
[Source: GitHub issues, YYYY-MM-DD]
```

### Step 6: Write to Brain

**CREATE path:**
1. Check notability: "Will we interact with them again?"
2. Create memory file with compiled truth + timeline format
3. Fill compiled truth with cited facts
4. Add first timeline entry
5. Leave unknown sections empty (no boilerplate filler)

**UPDATE path:**
1. Add new timeline entries (newest first, append-only)
2. Update compiled truth ONLY if new info materially changes the picture
3. Flag contradictions between new and existing info
4. Don't overwrite Jason's direct statements — they take precedence

### Step 7: Cross-Reference (MANDATORY)

- If enriching a person → update their company's page too (and vice versa)
- Add back-links from every mentioned entity (bidirectional)
- Update MEMORY.md index if a new page was created

## Compiled Truth Sections (by entity type)

### People
- Who they are (role, company, location)
- Relationship to VT/Jason
- What they care about / believe
- Communication preferences
- Key interactions

### Companies
- What they do
- Relationship to VT (client? partner? competitor?)
- Key people we know there
- Technical details if relevant

### Projects
- Status and goals
- Technical stack
- Key decisions made
- Blockers and next steps

## Citation Rules

Every fact needs a source. Source precedence:
1. Jason's direct statements (highest trust)
2. Existing compiled truth
3. Timeline entries (raw evidence)
4. External sources (web, APIs)

Format: `[Source: provider, YYYY-MM-DD]`

## Anti-Patterns

- Don't create pages for entities we'll never see again
- Don't write boilerplate ("No data yet") — leave sections empty
- Don't overwrite Jason's assessments with external data
- Don't enrich Tier 3 entities beyond brain cross-reference
- Don't forget back-links — they're mandatory, not optional
