# combat_readability_expansion_v1_review.md

# Combat Readability Expansion v1

Version: v1
Status: REVIEW
Scope: Combat Prototype

Implementation state:

Prototype implemented in `res://scripts/battle_scene.gd` for review testing. This document remains REVIEW and does not override `GAME_CURRENT_VERSION.md`.

## Purpose

Establish Combat Prototype phase 2:

Large-unit combat readability.

Validation direction:

- 4 player units + 6 enemies readability.
- Semi turn-based readability rhythm.
- Use of the empty standoff space.
- Low-presence Target Line.
- Skill Reading Window.
- Skill FX layering implementation.

Formal philosophy:

Players are not reacting to combat; they are comfortably understanding combat.

## Core Philosophy

This prototype does not pursue high-speed excitement.

It pursues comfortable reading.

Players should:

```text
See
↓
Understand
↓
Feel the battle state
```

Instead of:

```text
Cannot understand
↓
Information explosion
```

## 4 Player Units + 6 Enemies Validation

Prototype validation scale:

```text
4 player units
vs
up to 6 enemies
```

Validation content:

- Is the battle still readable?
- Can players understand who attacks whom?
- Are skills still clear?
- Is Focus Queue effective?
- Is Threat Marker sufficient?
- Is Status Layering clean?

## Battle Layout Direction

Formal direction:

Use the empty standoff space between both sides.

Battlefield structure:

```text
Player area

Guardian Rogue Ranger Mage

======== Empty standoff space ========

Enemy A Enemy B Enemy C Enemy D Enemy E Enemy F

Enemy area
```

Standoff space usage:

- Target Line.
- Projectiles.
- Skill crossing.
- Hit feedback.
- Focus Event.

Formal philosophy:

Let information happen between characters, not on top of characters.

## Skill Reading Window

Formal philosophy:

Understand the skill first, then understand the target.

Avoid:

Target Line stealing focus.

Skill reading flow:

```text
Caster wind-up
↓
Player understands who casts
↓
Low-presence Target Line
↓
Player understands target
↓
Hit
↓
Hit Reaction
```

Formal direction:

Skill is the Primary Read.

Target Line is Secondary Confirmation.

## Skill Reading Timing

Recommended:

Complete full understanding within approximately 3 seconds.

Reading order:

```text
Caster wind-up
(0.15 to 0.30s)

↓

Target Line
(0.08 to 0.15s)

↓

Skill hit
(0.10 to 0.25s)

↓

Hit Feedback
(0.05 to 0.15s)

↓

Return to background rhythm
```

Prototype validation:

Validate whether reading feels comfortable, not whether it is fast enough.

## Target Line

Formal philosophy:

Help confirm the target, not steal focus.

Direction:

Low Presence.

### Enable Conditions

Only for:

- Ranged attacks.
- Magic skills.
- Healing skills.
- Buff skills.
- Debuff skills.
- Boss skills.
- Elite skills.

Do not use for:

- Normal melee basic attacks.

Reason:

Melee already has step-in, Hit Reaction, and attack direction.

### Presentation Specification

Target Line:

```text
High transparency
Low brightness
Low saturation
Thin line
Short duration
```

Duration:

```text
0.08 to 0.20 seconds
```

Formal direction:

Do not make it laser-like.

Avoid:

- High-brightness lines.
- Long-lived lines.
- MMO warning feeling.

### Type Layers

Attack:

Pale white / pale red.

```text
Character --> Enemy
```

Healing:

Pale green.

```text
Cleric --> Ally
```

Buff:

Pale gold.

```text
Bard --> Ally
```

Debuff:

Pale purple / dark tone.

```text
Witch --> Boss
```

Boss skill:

Slightly thicker, but still low presence.

```text
Boss --> Target
```

Paired with:

- Threat Marker.

### Path Direction

Formal direction:

Prioritize the empty standoff space.

Avoid:

Crossing through character bodies.

## Skill FX Layering

Formal philosophy:

Skills are focus, but they must not occupy the whole screen.

Direction:

Octopath-like:

```text
Small but precise
Highly identifiable
Low fatigue
```

### Layer A: Character Identification Layer

Highest priority:

Players first see who is casting.

Examples:

```text
Mage raises staff
Guardian shield bash
Rogue slashes
```

### Layer B: Skill Identification Layer

Second:

Players understand what skill is being cast.

Examples:

```text
Fire
Lightning
Ice
Blessing
Curse
```

### Layer C: Target Line

Support:

Who is targeted.

Low presence.

### Layer D: Hit Layer

Examples:

```text
Hit Flash
Hit Reaction
Status applied
```

### Layer E: Background Rhythm

Normal attacks keep flowing, but reduce presence.

## Prototype Questions

Validate in actual gameplay:

1. Are 4 player units + 6 enemies still clear?
2. Is Target Line necessary?
3. Is the 3-second reading window comfortable?
4. Are skills still identifiable?
5. Is Boss Threat clear enough?
6. Is Comfort Mode still comfortable?

## Prototype Implementation Notes

Implemented for testing:

- Low-presence Target Line for ranged / magic / heal / Boss focus events.
- No Target Line for normal melee basic attacks.
- Skill Reading Window order: caster flash, Target Line, delayed hit feedback.
- Boss skill Target Line uses slightly thicker low-presence line and existing Threat Marker.
- Focus lock timing now uses Focus Window + Focus Gap for important-event queue spacing.
- Background normal attacks keep their 3.6s +/- 0.4s rhythm and do not enter Focus Queue.

Still review-only:

- Target Line necessity.
- Exact line opacity and duration.
- Whether AoE should show one line, multiple lines, or a center-area hint.
- Whether Focus Gap feels too long in actual phone portrait viewing.

## Final Philosophy

Not:

High-speed skill chaos.

Instead:

Background combat continues, and important information naturally rises.
