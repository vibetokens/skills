# Animation Patterns

## Fade in

```tsx
const opacity = interpolate(frame, [0, 20], [0, 1], { extrapolateRight: "clamp" });
```

## Slide up

```tsx
const translateY = interpolate(frame, [0, 20], [40, 0], { extrapolateRight: "clamp" });
// style={{ transform: `translateY(${translateY}px)` }}
```

## Spring entrance (preferred for elements that "arrive")

```tsx
const scale = spring({ fps, frame, config: { damping: 14, stiffness: 120 } });
const opacity = interpolate(frame, [0, 10], [0, 1], { extrapolateRight: "clamp" });
// style={{ transform: `scale(${scale})`, opacity }}
```

## Staggered entrance (multiple elements, offset timing)

```tsx
const ITEMS = ["Claude Code", "Coordinator Mode", "Hidden Flags"];

{ITEMS.map((item, i) => {
  const delay = i * 8; // 8 frames between each
  const opacity = interpolate(frame, [delay, delay + 15], [0, 1], {
    extrapolateLeft: "clamp",
    extrapolateRight: "clamp",
  });
  return <div key={item} style={{ opacity }}>{item}</div>;
})}
```

## Typewriter text

```tsx
const TEXT = "npx skills add vibetokens/skills";
const charsToShow = Math.floor(interpolate(frame, [0, 60], [0, TEXT.length], {
  extrapolateRight: "clamp",
}));
const visible = TEXT.slice(0, charsToShow);
// render: <span>{visible}<span style={{ opacity: frame % 20 < 10 ? 1 : 0 }}>|</span></span>
```

## Counter / number animation

```tsx
const value = Math.floor(interpolate(frame, [0, 60], [0, 147], {
  extrapolateRight: "clamp",
}));
// render: <span>${value}</span>
```

## Sequence timing helper

```tsx
// Use <Sequence> to offset child components by frame count
import { Sequence } from "remotion";

<Sequence from={30}>
  <MyComponent /> {/* starts at frame 30 */}
</Sequence>
```

## Loop

```tsx
const LOOP_DURATION = 60;
const loopFrame = frame % LOOP_DURATION;
const progress = loopFrame / LOOP_DURATION;
```

## Easing curves (via interpolate config)

```tsx
import { Easing } from "remotion";

interpolate(frame, [0, 30], [0, 1], {
  extrapolateRight: "clamp",
  easing: Easing.bezier(0.16, 1, 0.3, 1), // expo out
});
```
