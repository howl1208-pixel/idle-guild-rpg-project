# combat_readability_prototype_v1

Version: v1
Status: LOCK
Scope: Prototype validation for combat readability

## Purpose

This file defines prototype validation for combat readability.

Goal:

Verify whether current combat is understandable during dense combat situations.

This prototype validates:

- `combat_tempo_v2`
- `combat_readability_v1`

This is not balance tuning, combat redesign, skill redesign, or monster redesign.

Purpose:

Real gameplay readability testing.

## Prototype Scenario

Fixed scenario:

4 player units vs 6 enemies.

Reason:

Simulate high-density combat conditions during beta gameplay.

## Validation Goal

Combat should feel readable, understandable, continuous, and idle-friendly.

Combat should not feel chaotic, visually overloaded, MMO spam-like, or traditional full-stop turn-based.

## Target Recognition Test

Players should naturally understand:

- Who attacks whom.
- Who gets targeted.
- Who casts a skill.
- Who receives damage.
- What the Boss is doing.

Success condition:

Players understand naturally without thinking.

Failure condition:

Players feel confused despite combat activity.

## Multi-unit Readability Test

Validate micro-staggered combat readability.

Combat should feel like:

`A attacks -> understandable -> B attacks -> understandable -> C skill -> understandable`

Not:

`everyone acts simultaneously`

Combat is not intended to become slower. Combat is intended to become clearer.

## Adjustment Priority

If combat still feels visually crowded, first adjust:

`ACTION_STAGGER_INTERVAL`

Current direction:

- 0.35 seconds.

Possible prototype adjustment:

- 0.40 to 0.45 seconds.

Forbidden direction:

- Stretching important combat events into traditional full-stop turn-based pacing.
- Increasing spacing into long pauses.

## Important Event Readability

Important events include:

- Player skills.
- Enemy skills.
- Elite skills.
- Boss telegraphs.
- High-priority combat moments.

Important event readability target:

- Focus Window: 1.8 to 3 seconds.
- Focus Gap: 1.4 to 3 seconds.

Meaning:

Enough space to understand what happened.

Not:

Traditional full-stop turn-based pauses.

Combat remains continuous real-time combat.

## Hit Feedback Fatigue Test

Current direction:

- Micro hit flash.
- Duration: 0.08 seconds.

Expected feeling:

- Readable.
- Low fatigue.
- Lightweight.

Failure signs:

- Too bright.
- Annoying.
- Visually tiring.
- Excessive flashing.

## Skill FX Readability Test

Question:

Can players still understand combat during skills?

Failure condition:

Skill effects hide combat information.

Expected direction:

- Localized FX.
- Readable battlefield.
- Low rendering density.
- Low fatigue.

## Damage Number Readability Test

Question:

Can players understand damage naturally?

Failure condition:

Unreadable number spam.

If failed, first improve damage stagger readability, not remove damage numbers.

## Low-presence Target Line Test

Only test if players still struggle to understand target recognition.

If needed, implement a low-presence target line.

Requirements:

- Short duration.
- Low opacity.
- Subtle.
- Non-intrusive.
- Non-laser feeling.

Purpose:

Readability assistance, not UI decoration.

## Explicit Restrictions

Codex must not:

- Redesign combat.
- Redesign monsters.
- Rebalance skills.
- Modify encounter structure.
- Invent new combat systems.
- Slow combat excessively.
- Convert combat into traditional full-stop turn-based pacing.

This file exists for readability validation only.

## Success Condition

Players should naturally understand:

- Who attacked.
- Who got hit.
- What happened.
- Who is dangerous.
- What the Boss is doing.

without fatigue.

Formal target:

Readable real-time idle combat.
