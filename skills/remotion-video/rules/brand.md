# Vibe Tokens Brand — Remotion Style Guide

Use these values when building VT-branded videos unless explicitly told otherwise.

## Colors

```ts
const VT = {
  bg:        "#080A0F",  // primary background
  bgAlt:     "#0c0e13",  // secondary background / cards
  border:    "#1e2028",  // subtle borders
  mint:      "#00FFB2",  // primary accent — neon mint green
  mintDim:   "#00cc8e",  // dimmed mint for secondary elements
  white:     "#FFFFFF",
  textPrimary:   "#e2e2e9",
  textSecondary: "#b9cbbe",
  textMuted:     "#52526b",
};
```

## Typography

```ts
// Font stack (Google Fonts or system)
const FONTS = {
  display: "Space Grotesk",  // headings, labels, caps
  body:    "Inter",           // body copy, paragraphs
};

// Typical heading
// fontSize: 64-96, fontWeight: 900, textTransform: "uppercase", letterSpacing: "-0.02em"

// Typical label
// fontSize: 11, fontWeight: 700, textTransform: "uppercase", letterSpacing: "0.3em"
```

## Layout

- 1920×1080 (16:9) for general/LinkedIn
- 1080×1080 (1:1) for Instagram/social square
- 1080×1920 (9:16) for Stories/TikTok/Reels

## Aesthetic

- Dark, editorial, cinematic — no stock photo energy
- Geometric / architectural — grids, borders, sharp edges
- Mint green is the only color that pops against the dark bg
- No gradients except subtle dark-to-darker
- Monospace font for code/terminal elements

## Standard intro sequence (6 seconds / 180 frames at 30fps)

```tsx
// Frame 0-20:    background fades in
// Frame 15-35:   accent dot appears (w-1.5 h-1.5 bg-[#00FFB2])
// Frame 25-50:   label slides up ("Vibe Tokens · Claude Code")
// Frame 40-80:   headline enters with spring
// Frame 70-100:  subtext fades in
// Frame 120+:    content / demo / CTA
```

## Terminal / code block style

```tsx
<AbsoluteFill style={{
  backgroundColor: "#0c0e13",
  border: "1px solid #1e2028",
  fontFamily: "monospace",
  fontSize: 18,
  color: "#b9cbbe",
  padding: 40,
}}>
  <span style={{ color: "#52526b" }}>$ </span>
  <span style={{ color: "#00FFB2" }}>{typedText}</span>
</AbsoluteFill>
```
