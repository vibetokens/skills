# Rendering & Export

## Render commands

```bash
# MP4 (default, best for social)
npx remotion render <CompositionId> out/video.mp4

# WebM (smaller, web-only)
npx remotion render <CompositionId> out/video.webm --codec=vp8

# GIF (short loops, max 10s recommended)
npx remotion render <CompositionId> out/animation.gif

# Single frame as PNG
npx remotion still <CompositionId> --frame=0 out/thumbnail.png

# Specific frame range
npx remotion render <CompositionId> out/video.mp4 --frames=0-60
```

## Quality settings

```bash
# High quality (client deliverable)
npx remotion render <CompositionId> out/video.mp4 --crf=18

# Balanced (social media)
npx remotion render <CompositionId> out/video.mp4 --crf=23

# Fast preview
npx remotion render <CompositionId> out/preview.mp4 --crf=28 --scale=0.5
```

## Social media output specs

| Platform     | Size       | Format | Duration  |
|-------------|------------|--------|-----------|
| LinkedIn    | 1920×1080  | MP4    | 3–30s     |
| Twitter/X   | 1280×720   | MP4    | under 2m  |
| Instagram   | 1080×1080  | MP4    | 3–60s     |
| Stories     | 1080×1920  | MP4    | under 60s |
| YouTube     | 1920×1080  | MP4    | any       |

## Development preview

```bash
npm run dev
# Opens browser at localhost:3000
# Hot reloads on save
# Scrub timeline to preview any frame
```

## Bundle size check

```bash
npx remotion bundle  # checks for errors before render
```
