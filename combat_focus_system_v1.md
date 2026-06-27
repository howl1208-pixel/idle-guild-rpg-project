# combat_focus_system_v1.md

# Combat Focus System v1

Version: v1
Status: FINAL
Scope: Formal Combat Focus System

## System Position

Combat Focus System v1 formally overwrites:

- `combat_tempo_v2`
- `combat_readability_v1`

Formal direction:

`Semi Turn-Based Combat`

Underlying operation remains:

`Real-Time Timeline Combat`

Formal philosophy:

`Background flow + important moments rise one at a time`

Purpose:

Let players truly understand combat.

This is not simultaneous unit action spam, and it is not traditional turn-based waiting.

## Core Combat Philosophy

Combat priority:

1. Readability.
2. Understandability.
3. Long-session viewing comfort.
4. Combat flow.

Formal direction:

Players should understand what is happening.

Do not pursue only faster combat.

Do not pursue only slower combat.

Core rule:

Understanding matters more than speed.

## Combat Layers

| Layer | Role | Description |
| --- | --- | --- |
| Background Layer | Background rhythm | Keeps the world continuously moving |
| Focus Layer | Focus rhythm | Important events become readable one at a time |

## Background Layer

Background Layer is the continuous battle rhythm.

Includes:

- Normal attacks.
- Small hit reactions.
- Normal minor enemy attacks.
- Minor events.

Formal direction:

It exists, but does not steal focus.

| Item | Formal direction |
| --- | --- |
| Normal attack speed | 3.6s +/- 0.4s |
| Combat role | Background rhythm |
| FX intensity | Low presence |
| Damage numbers | No spam |
| Purpose | Preserve combat flow |

Forbidden:

- Normal attacks stealing focus.
- Large normal attack presentations.
- Normal attacks covering skill readability.

## Focus Layer

Focus Layer contains important events players need to read and understand.

Important events include:

- Boss Skill.
- Elite Skill.
- Player Skill.
- Important Heal.
- High-danger event.

Formal direction:

Important events rise one at a time instead of exploding simultaneously.

## Focus Queue v1

Formal direction:

`One Focus Event Per Readability Window`

Meaning:

Players should understand only one important event at a time.

Do not force multiple skills into a short period.

## Focus Priority

| Priority | Type |
| --- | --- |
| S | Boss Skill |
| A | Elite Skill |
| B | Player Skill |
| C | Important Heal |
| D | Background Event |

## Focus Readability Rules

### Rule 1

Important events must not overlap.

Forbidden:

Boss skill + player skill + major heal all becoming focus at the same time.

Formal direction:

Queue for understanding.

### Rule 2

Within approximately 3 seconds, players should generally understand only one important event.

Purpose:

Humans need time to digest combat information.

Formal direction:

Player understanding matters more than speed.

### Rule 3

Focus events preserve a `Readability Gap`.

Purpose:

Give players time to process information.

Avoid continuous focus bombardment.

## Focus Timing

| Item | Recommended range | Purpose |
| --- | ---: | --- |
| Focus Window | 1.8 to 3 seconds | Understand one focus event |
| Focus Gap | 1.4 to 3 seconds | Breathing room and information digestion |

Formal principle:

If players cannot understand combat, lengthen the Focus Gap first instead of adding more events.

## Expected Feel

Background:

- Normal attacks continue.
- Wolf bite.
- Skeleton slash.
- Small hit reactions.

Focus:

Boss warning -> understand.

Breath.

Guardian shield skill -> understand.

Breath.

Mage fireball -> understand.

Breath.

Cleric major heal -> understand.

Player feeling:

The world is still moving, but important moments are understood one by one.

## Forbidden Example

Forbidden:

```text
0.0 Boss skill
0.3 Player skill
0.5 Major heal
0.7 Elite skill
```

Reason:

Humans cannot read multiple important events in such a short time.

Result:

Players watch noise instead of understanding combat.

## Hit Feedback

| Item | Formal direction |
| --- | --- |
| Hit Flash | 0.08s |
| Feel | Shorter and lower fatigue |
| Goal | Hits are visible but not annoying |

## Combat Speed

| Item | Formal direction |
| --- | --- |
| Battle speed | Fixed 1x |
| Speed button | Removed |

Reason:

Maintain a consistent readability feel.

## Prototype Validation

Formal validation:

`4 player units vs 6 enemies`

Validation items:

1. Can players understand who attacks whom?
2. Can players understand what the Boss is doing?
3. Can players understand important skills?
4. Can players understand who was healed?
5. Can players watch for a long time without fatigue?

## If Combat Still Feels Chaotic

Adjustment order:

1. Increase `Focus Gap`.
2. Then tune `ACTION_STAGGER_INTERVAL` from 0.35 toward 0.40 to 0.45.

Forbidden:

Do not directly stretch combat into slow traditional turn-based pacing.

## Success Condition

Players can naturally say:

- Who just used a skill.
- What the Boss is preparing.
- Who was healed.
- Who received a dangerous attack.

And:

Long-term idle watching remains comfortable and readable.
