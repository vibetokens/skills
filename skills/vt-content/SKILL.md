---
name: vt-content
description: Write blog posts, LinkedIn posts, and content for the Vibe Tokens brand. Use when asked to create any VT content, write a post, draft a blog article, or adapt content for social media.
effort: max
---

# Vibe Tokens Content Skill

## Voice

**Blend:** Dan Koe (elevation/systems thinking) + Tim Denning (raw/honest) + Tom Bilyeu (intensity/transformation).

- Elevated, first-person, builder documenting in public
- Architecture-first framing: problems are structural, solutions are designed
- Claude-forward: Claude is infrastructure, not a productivity tool
- Nerd references welcome — cite research, be specific, respect reader intelligence
- End with a genuine question or observation, not a sales CTA

## Hard rules (never break)

- ZERO ICP language — no niches, no "dental practices", no "if you run a [business type]"
- ZERO pricing in blog content
- ZERO mentions of AI, Claude, or any AI tool in client-facing content
- Never sound like a listicle
- Never use "game-changer", "revolutionary", "unlock your potential"

## Blog post format

```
---
slug: [kebab-case]
title: "[Title — specific, not clever]"
category: [claude-code | the-layer | research | build | work]
date: "YYYY-MM-DD"
author: Murph
excerpt: "[One sentence. What the post says, not what it's about.]"
readTime: "[N] min read"
coverImage: "/blog-images/[slug]-cover.jpg"
faq:
  - q: "[Question users actually search]"
    a: "[Direct answer, 2-3 sentences]"
  - q: "..."
    a: "..."
---

[Content in markdown]
```

## Categories

- `claude-code` — Claude Code hidden features, configuration, architecture
- `the-layer` — philosophy, attention residue, AI as infrastructure
- `research` — Claude ecosystem, MCP, AI automation research
- `build` — how specific systems were built, architecture decisions
- `work` — anonymized patterns from client work, no names

## LinkedIn adaptation

- 3–7 short paragraphs, no headers
- First line is the hook — statement or observation, not a question
- One concrete thing per post
- End with a 1-line observation or question (not a CTA)
- No hashtags unless explicitly asked
- No "here's what I learned" opener

## Image generation

Every post needs a cover image. Generate with:

```bash
cd C:/Users/jason/vt-content-hopper
python generate.py "[prompt]" --category [architecture-systems|builder-moody|philosophy-attention|brand-general] --name [slug]-cover
```

Prompt style: dark background, neon mint green (#00FFB2) accents, VT logo, 16:9, no humans.
