# combat_readability_v1

Version: v1
Status: LOCK
Scope: Combat readability only

## System Purpose

This file defines combat readability, target recognition, hit readability, damage readability, status readability, and skill FX readability.

Core purpose:

Help players understand combat clearly.

This system exists to solve:

Players cannot understand who attacks whom, especially during multi-unit combat with 4 player units and multiple enemies.

Combat readability takes priority over flashy presentation.

Formal philosophy:

Readability First, not Effect First.

## Core Philosophy

Combat should feel understandable, readable, comfortable to watch, idle-friendly, and visually clean.

Combat should not feel like MMO effect spam, chaotic visual stacking, unreadable screen clutter, or constant flashing overload.

## Target Readability

Players should immediately understand who attacks whom.

Combat may display a low-presence target line for target recognition only.

Requirements:

- Subtle.
- Short duration.
- Low opacity.
- Non-intrusive.
- Recommended duration: 0.15 to 0.25 seconds.

Forbidden:

- Laser beam style.
- Strong glowing line.
- Permanent line display.

## Action Order Readability

Attack sequence must follow:

Attack Motion -> Hit Confirmation -> Reaction -> Damage Number.

Damage must not appear before attack motion.

## Hit Readability

On successful hit, the target briefly flashes for hit confirmation.

Recommended micro hit flash duration:

- 0.05 to 0.08 seconds.

Allowed examples:

- Light white flash.
- Weak red flash.

Forbidden:

- Full screen flash.
- Exaggerated bloom.
- High intensity strobe.

Targets may use tiny visual reaction, but must not use exaggerated knockback, long stun-like motion, or dramatic displacement.

## Damage Number Readability

Damage numbers should stagger.

Forbidden:

- Multiple damage numbers appearing on the same frame.

Recommended delay:

- 0.05 to 0.12 seconds.

Damage numbers should remain visually consistent above the target body.

Avoid random screen positions, excessive movement, and chaotic scatter.

DOT effects must avoid screen spam. Poison, Burn, and Bleed should prioritize status duration, final result, and death-related result instead of every-second number spam.

## Buff / Debuff Readability

Formal system:

Status Layering v1.

Status icons should collapse to avoid UI overload.

Forbidden:

- Large icon explosion over units.

Similar effects may merge visually into a stronger state when appropriate.

## Skill FX Philosophy

Skills must remain readable. Effects are not the focus.

Formal philosophy:

Low-fatigue visual combat.

Requirements:

- Low rendering density.
- Low screen clutter.
- Battlefield visibility first.

Fire, Ice, Lightning, Buff, and Debuff FX should be localized, short, and easy to recognize. They must not become full-screen spam or permanent visual noise.

## Boss Readability Priority

Boss skills receive readability priority.

Allowed:

- Clearer telegraph.
- Slightly stronger visual emphasis.
- Stronger focus moment.

Forbidden:

- Cinematic pause.
- Long freeze.
- Unreadable visual overload.

Boss should feel threatening but understandable.

## Success Condition

Players should understand:

- Who attacked.
- Who got hit.
- What happened.
- Who is in danger.
- What skill triggered.

without slowing combat excessively.

Formal target:

Readable real-time idle combat.

## Explicit Restrictions

Codex must not:

- Increase visual clutter.
- Create MMO-style effect spam.
- Turn combat cinematic.
- Reduce battlefield readability.
- Modify monster balance.
- Modify combat pacing philosophy.
- Change combat rules.

Scope:

Combat readability only.
