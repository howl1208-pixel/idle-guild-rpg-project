# combat_tempo_v2

Version: v2
Status: SUPERSEDED
Superseded By: `combat_system_current.md`
Retained For: historical background rhythm notes only.
Scope: Combat pacing / action sequencing / readability spacing / animation timing philosophy

## System Purpose

This file defines combat pacing, action sequencing, readability spacing, and animation timing philosophy.

This system exists to solve multi-unit simultaneous combat readability problems.

`Combat Focus System v1 (FINAL)` overwrites this file's focus-event timing. This file remains the reference for background rhythm, asynchronous action timers, and ordinary action staggering.

Core issue:

Players cannot understand who attacks whom when multiple units act simultaneously.

This system must improve readability through semi turn-based focus timing without becoming traditional full-stop turn-based combat and without slowing combat excessively.

## Core Philosophy

Combat should feel readable, alive, continuous, understandable, and comfortable for long-term idle watching.

Combat should not feel like chaotic MMO spam, synchronized action spam, unreadable visual clutter, or traditional full-stop turn-based combat.

Formal direction:

Semi Turn-Based Combat running on a Real-Time Timeline.

This officially overwrites older anti-focus-timing wording. The forbidden direction is traditional full-stop turn-based combat or whole-battlefield freeze, not the semi turn-based focus system.

## Combat Tempo Core Rule

No simultaneous action burst.

Forbidden:

- Multiple units attacking at the same frame.
- Overlapping skill spam.
- Stacked damage numbers at identical timing.

Allowed:

- Slight stagger.
- Visual breathing room.
- Readable action chain.

Combat should feel like:

`background combat continues -> important event takes focus -> background combat continues`

instead of:

`everyone explodes together`

## Actor Interval System

Every unit owns an internal action timer.

Units act independently.

System type:

Asynchronous timeline.

Not a traditional party turn system.

Focus events may queue without freezing the background rhythm.

Not synchronized cooldown execution.

## Action Spacing Rule

Between actions:

- Recommended spacing: 0.30 to 0.60 seconds.

Purpose:

- Readable target recognition.
- Readable hit source.
- Readable reaction timing.

## Animation Sequence Order

Each action follows:

1. Wind-up.
2. Attack motion.
3. Hit timing.
4. Hit reaction.
5. Damage number.
6. Recovery.

Formal sequence:

Attack Motion -> Hit Confirmation -> Reaction -> Damage Result.

Not:

Attack + Damage + Reaction at the same frame.

## Combat Readability Window

Every action should preserve a minimum readable window of 0.20 to 0.35 seconds.

The player should visually understand the attacker, target, and result before the next major event overlaps.

## Skill Priority Rule

When a skill happens, it becomes a focus event and enters the Focus Queue.

The goal is to preserve readability, not maximize speed.

## Focus Queue Rule

All important events enter Focus Queue.

Important events include active skills, Boss skills, Elite skills, large damage events, summon special skills, important healing skills, and important Buff / Debuff skills.

Only one focus event may present at a time.

Normal attacks remain background rhythm and do not enter Focus Queue.

## Boss Readability Rule

Boss actions receive priority spacing.

Boss focus timing follows `Combat Focus System v1 (FINAL)`:

- Focus Window: 1.8 to 3 seconds.
- Focus Gap: 1.4 to 3 seconds.

Boss skills must remain readable.

Avoid instant unreadable burst and overlapping Boss spam.

Boss should feel threatening but understandable.

## Damage Number Timing

Damage numbers should stagger.

Forbidden:

- 10 numbers popping on the same frame.

Recommended:

- 0.05 to 0.12 seconds stagger.

Goal:

Readable combat flow.

## Multi-unit Combat Priority

Priority:

1. Boss Skill.
2. Elite Skill.
3. Player Skill.
4. Basic Attack.

Lower priority actions may wait slightly for combat focus clarity.

## Explicit Restrictions

Codex must not:

- Convert combat into a traditional full-stop turn-based system.
- Freeze the entire battlefield for focus events.
- Synchronize all cooldowns.
- Slow combat excessively.
- Add cinematic pauses.
- Change monster stats.
- Change skill balance.
- Modify encounter design.
- Invent new combat rules.

Scope:

Combat pacing and readability only.

## Success Condition

Player should understand who attacked, who was targeted, what happened, and why damage happened without slowing gameplay too much.

Formal target:

Understandable combat at idle speed.
