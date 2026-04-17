---
name: signal-detector
description: Ambient signal capture — fires at end of substantive conversations. Extracts entities (people, companies, clients) and original ideas. Creates/updates memory pages with timeline entries and back-links. Adapted from gbrain (Garry Tan).
effort: low
---

# Signal Detector

Always-on ambient signal capture. After every substantive conversation (not quick lookups or git ops), capture entities and original thinking.

## When to Fire

- End of a conversation that mentioned people, companies, or clients by name
- When Jason shares an original idea, framework, or strategic insight
- When new information about existing entities surfaces
- When a client interaction reveals something new

**Do NOT fire on:** purely operational tasks (git push, deploy check, file edit), quick questions, or conversations that are entirely about code mechanics.

## What to Capture

### 1. Entity Mentions

Extract named entities from the conversation:
- **People:** Capitalized names (2-4 words). Jason's family, clients, contacts, industry figures.
- **Companies:** Business names mentioned. Clients, tools, competitors.
- **Skip:** VT itself, Claude/Murph, generic terms.

For each entity:
1. Check if a memory page exists (`user_*.md`, `project_*.md`, `reference_*.md`)
2. If YES → add a timeline entry with today's context
3. If NO → evaluate notability: "Will we interact with them again?" If yes, create a page.

### 2. Original Ideas

Capture Jason's original thinking with his EXACT phrasing:
- Strategic decisions ("we should...", "the play is...", "from now on...")
- Frameworks ("the way I think about it is...")
- Insights about the business, market, or product

Save as feedback or project memory with `[Source: Jason, YYYY-MM-DD]`.

## Entity Page Format

New entity pages use the compiled truth + timeline model (see knowledge-model.md):

```markdown
---
name: Entity Name
description: One-line description
type: user | project | reference
tier: 3
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# Compiled Truth

What we know. Facts with sources.

---

## Timeline

- **YYYY-MM-DD** | First mentioned in [context] [Source: conversation]
```

## Tier Assignment

- **Tier 1:** Active clients, family, close contacts (Sarah, Erica, Ilya, MAVON)
- **Tier 2:** Prospects, industry contacts, tools we use
- **Tier 3:** One-time mentions, background entities (default for new entities)

Auto-escalate when mention count grows: 8+ → Tier 1, 3-7 across 2+ contexts → Tier 2.

## Back-Linking (MANDATORY)

When an entity is mentioned in another memory page, that entity's timeline gets a back-link entry:

```
- **YYYY-MM-DD** | Referenced in [page title](filename.md) — brief context [Source: conversation]
```

This is how the knowledge graph compounds. Never skip this step.

## Output

After capturing signals, log a one-line summary:

```
Signals: X entities updated, Y ideas captured, Z new pages created
```

## Anti-Patterns

- Don't create pages for entities we'll never interact with again
- Don't paraphrase Jason's ideas — use exact phrasing
- Don't fire on every single conversation — use judgment
- Don't create duplicate pages — always check existing memories first
- Don't overwrite compiled truth — refine it, add citations
