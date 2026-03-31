# @vibetokens/skills

Claude Code skills for video generation, content creation, and blog publishing.

## Install

```bash
npx skills add vibetokens/skills
```

Installs all three skills globally. Available in every Claude Code session immediately.

## Skills

### remotion-video

Create programmatic videos and animations with Remotion. Claude scaffolds projects, writes compositions, handles timing math, and renders to MP4/WebM/GIF.

```
Make a 10-second intro animation for the OPERATOR launch.
Dark background, neon green text, typewriter effect on the headline.
```

```
Build a 30-second product demo video showing the Claude Code audit flow.
Terminal window, typewriter text, score counter animating from 0 to 6.
```

### vt-content

Write blog posts and LinkedIn content in the Vibe Tokens voice. Elevated, builder-documenting-in-public, Claude-forward. Enforces voice rules, post format, and FAQPage schema.

```
Write a blog post about why most CLAUDE.md files are context dumps, not operating systems.
```

```
Adapt the coordinator mode blog post for LinkedIn.
```

### vt-blog

Full publish pipeline — writes post, generates cover image, commits, deploys, verifies live URL.

```
/vt-blog publish the CLAUDE.md architecture post
```

## What Remotion is

[Remotion](https://remotion.dev) is a React-based framework for creating videos programmatically. Every frame is a React component. Animations are pure math on the current frame number. No timeline scrubber — you write the functions, Remotion renders the video.

The `remotion-video` skill teaches Claude the API so you can prompt your way to a rendered MP4.

## Links

- [vibetokens.io](https://vibetokens.io)
- [vibetokens.io/tools](https://vibetokens.io/tools) — free Claude Code tools
- [vibetokens.io/mcp](https://vibetokens.io/mcp) — @vibetokens/mcp server
- [hello@vibetokens.io](mailto:hello@vibetokens.io)

## License

MIT
