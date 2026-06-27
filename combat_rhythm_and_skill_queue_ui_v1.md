# combat_rhythm_and_skill_queue_ui_v1.md

# Combat Rhythm + Skill Queue UI v1

Version: v1
Status: FINAL
Scope: Combat Prototype

Implementation state:

Implemented in `res://scripts/battle_scene.gd` as the first playable prototype.

## Purpose

Establish the latest Combat Prototype direction:

Normal attacks keep flowing.

Skills are read one at a time.

Core goals:

- Preserve expedition party combat feeling.
- Prevent skill FX from fighting each other.
- Prevent simultaneous skill-cast confusion.
- Improve combat readability.
- Reduce UI noise.
- Improve idle viewing comfort.

Formal philosophy:

Normal attacks make the world flow.

Skills make the world slow down.

## Core Philosophy

This system is not true turn-based combat.

It is not chaotic real-time combat.

It is:

Real-Time Combat + Global Skill Queue.

In one sentence:

The world keeps fighting, but skills take turns becoming the focus.

## Global Skill Queue

Formal direction:

Skills enter the queue when their own cooldown is ready.

When a skill is ready, add it to:

```text
Global Skill Queue
```

Sorting:

```text
Ready Time
```

### Skill Queue Example

```text
0.00 Guardian skill ready
0.15 Mage skill ready
0.48 Wolf skill ready
0.82 Cleric skill ready
```

Actual cast order:

```text
Guardian skill
↓
Mage skill
↓
Wolf skill
↓
Cleric skill
```

Formal direction:

Read one skill at a time.

Avoid:

- Skill explosions overlapping.
- FX fighting each other.
- Information confusion.

## Skill and Agility Separation

Formal proposal:

Agility does not affect skill cooldown.

Agility only affects normal attack rhythm.

Avoid:

High-agility characters monopolizing skill frequency.

## Queue and Death Rule

Formal direction:

If a queued unit dies before casting, cancel its skill.

Example:

```text
Mage queued
↓
Killed
↓
Removed from Queue
```

Avoid:

Dead units casting.

## Skill Focus Slow

When any skill is cast, the battlefield enters Slow State.

Formal philosophy:

A skill is a moment where the world slows down.

### Slow State Rule

Not:

```text
Freeze
```

Instead:

The world rhythm slows by approximately 50%.

Keep:

- Breathing.
- Idle.
- Buff / Debuff subtle motion.
- Status FX.
- Normal attacks.

Pause:

- Other skill casts.

Avoid:

Multiple skills presenting at the same time.

## Normal Attack Handling During Skills

During skills:

Normal attack rhythm slows by approximately 50%.

Example:

Original:

```text
2 seconds per attack
```

During skill:

```text
approximately 4-second feel
```

Purpose:

The world stays alive, but skills become the focus.

Formal philosophy:

During skills, time slows slightly.

## Normal Attack Rhythm

Formal proposal:

Agility only affects normal attack rhythm.

Formula direction:

```text
Attack Interval = Base Rhythm * SPD Modifier
```

## Class Rhythm Direction

### Guardian

Role:

Heavy.

Feel:

```text
2.6 to 3.0 seconds
```

### Rogue

Role:

Fast.

Feel:

```text
1.4 to 2.0 seconds
```

### Ranger

Role:

Medium-high speed.

Feel:

```text
1.8 to 2.3 seconds
```

### Mage / Cleric

Role:

Slower.

Feel:

```text
2.3 to 2.8 seconds
```

Formal philosophy:

Class difference comes from rhythm, not effect count.

## Skill Queue UI

Formal philosophy:

Players watch the battle state, not cooldowns.

In one sentence:

Skill information is centralized.

## UI Position

Portrait layout position:

Battlefield lower area, above the battle log.

Arrangement:

Single horizontal row.

Direction:

```text
Left -> Right
```

Rule:

Left = next caster.

Right = later casters.

Example:

```text
[Guard][Mage][Wolf][Cleric][Ranger][Wolf]
```

Formal direction:

Understand the near-future battle flow at a glance.

## Display Content

Only show:

Unit small portrait.

Do not show:

- Skill name.
- Skill icon.
- Cooldown number.
- Countdown.
- Progress bar.
- Text.

Formal philosophy:

Knowing who will act is enough.

## Maximum Display Count

Formal proposal:

Maximum 6 queued units.

If more exist:

Do not display extras.

Reasons:

- Portrait mobile layout.
- Low interference.
- Avoid information anxiety.

Formal philosophy:

Players only need to understand the near future.

## First Slot Hint

Leftmost slot:

Next caster.

Use only:

- Slight border.
- Subtle glow.
- Small arrow.

Avoid:

- Bright flashing.
- Large animation.
- Exaggerated scaling.

Formal direction:

Low-presence hint.

## Empty Slot Rule

If fewer than 6 slots are queued, leave the rest empty.

Do not use:

- Plus signs.
- Placeholder frames.
- Debug empty boxes.

Keep the screen clean.

## Remove Skill Cooldown Beside Characters

Formal proposal:

Completely remove:

- Skill icon beside characters.
- Cooldown circle.
- Countdown number.
- Cooldown bar.

Reason:

With 4 players + 6 enemies, Threat Marker, Status Layering, Target Line, and Skill Queue, information is already sufficient.

Formal philosophy:

Players watch the battle, not cooldown UI.

## Summon Reserved Slots

Position:

Upper-right of player unit area.

Direction:

Slightly upper-right.

Formal proposal:

Maximum 4 slots.

Un-summoned:

High-transparency empty frame.

After summoned:

Naturally filled.

Avoid:

Competing with Skill Queue visual focus.

## Prototype Questions

Validate:

1. Is Skill Queue comfortable?
2. Does world slowing feel natural?
3. Does normal attack rhythm still preserve expedition party feeling?
4. Are 6 queue slots enough?
5. Is this cleaner than character-side cooldown UI?
6. Are 4 player units + 6 enemies still readable?

## Final Philosophy

Not:

Full-screen skill chaos.

Instead:

The world keeps fighting, and skills naturally take turns being understood.

## Implementation Notes

Implemented:

- Player skills and Boss skills enter `Global Skill Queue` when cooldown becomes ready.
- Queue order follows ready order.
- Dead queued units are removed before casting.
- Skill focus uses Focus Window + Focus Gap timing.
- During skill focus, ordinary action timers advance at approximately 50% speed.
- Class-specific normal attack rhythm is implemented for Guardian, Ranger, Mage, and Cleric; other units use speed-based fallback timing.
- Skill Queue UI appears above the battle log and displays up to 6 queued unit portraits.
- The leftmost slot uses a subtle border as the next-caster hint.
- Character-side skill cooldown text is hidden.
- Normal melee attacks keep flowing without Target Line or cooldown UI.
- Four summon reserve UI slots are prepared as visual reservation only.

Still needs visual review:

- Whether Skill Queue UI is too close to existing support / buff panels.
- Whether 6 slots are enough for dense fights.
- Whether Slow State feels natural on a real portrait screen.
- Whether class-specific attack rhythm values need further tuning after portrait testing.
