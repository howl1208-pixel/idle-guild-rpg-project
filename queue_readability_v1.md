# Queue Readability v1

Status: FINAL
Scope: Queue readability polish only
Non-goal: new combat system, combat tempo rewrite, UI overhaul

## Purpose

Queue functionality already exists. This pass improves readability and anticipation without making the queue loud or attention-demanding.

Formal philosophy:

- Readability First
- Low Fatigue
- Subtle Guidance

Queue should feel informative and natural, not flashy.

## Rules

- Increase queue readability for portrait gameplay.
- Extend queue width by roughly 30% so the queue reads more like a timeline than an icon cluster.
- First slot represents the next important action.
- First slot uses 125% scale and subtle brightness.
- Later slots use light hierarchy: second 100%, third 95%, fourth and later 90%.
- Player queue entries use a small upward slide and fade.
- Enemy queue entries use a small downward slide and fade.
- Queue exit uses soft fade and slight shrink.
- Queue reflow uses a short micro slide.

## Motion Limits

- Default duration: 0.15 seconds.
- Entry movement stays within a small 12 to 28 px range.
- No bounce, spring, overshoot, spin, strong pulse, large glow, warning flash, or cinematic behavior.

## Success Condition

Players should naturally understand:

- who acts next
- who acts later
- that combat events are progressing through a timeline

The queue should remain quietly helpful during long-term viewing.
