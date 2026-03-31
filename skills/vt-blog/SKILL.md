---
name: vt-blog
description: Publish a new blog post to the Vibe Tokens website. Use when asked to publish, deploy, or add a blog post. Creates the MDX file, generates the cover image, commits, and pushes.
disable-model-invocation: true
effort: max
---

# VT Blog Publisher

Publish a complete blog post to vibetokens.io.

## Steps

1. **Write the post** — MDX format, frontmatter required (see vt-content skill for voice/format)
2. **Save to** `C:/Users/jason/vibetokens/data/posts/[slug].mdx`
3. **Generate cover image**:
   ```bash
   cd C:/Users/jason/vt-content-hopper
   python generate.py "[visual prompt]" --category [category] --name [slug]-cover
   ```
   Copy output PNG to `C:/Users/jason/vibetokens/public/blog-images/[slug]-cover.jpg`
4. **Verify build**:
   ```bash
   cd C:/Users/jason/vibetokens && npm run build 2>&1 | tail -5
   ```
5. **Commit and push**:
   ```bash
   git add data/posts/[slug].mdx public/blog-images/[slug]-cover.jpg
   git commit -m "Blog: [title]"
   git push origin main
   ```
6. **Deploy** (if git build fails, force-deploy):
   ```bash
   npx vercel --prod
   ```
7. **Verify live**:
   ```bash
   curl -s -o /dev/null -w "%{http_code}" "https://www.vibetokens.io/blog/[slug]"
   # Must return 200
   ```
8. **Write LinkedIn adaptation** using the vt-content voice rules

## Category → image category mapping

| Post category | Image category        |
|---------------|-----------------------|
| claude-code   | builder-moody         |
| the-layer     | philosophy-attention  |
| research      | architecture-systems  |
| build         | builder-moody         |
| work          | brand-general         |
