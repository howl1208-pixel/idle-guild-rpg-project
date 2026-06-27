# Combat Tempo v2

Status: SUPERSEDED  
Superseded By: `../combat_system_current.md`  
Retained For: historical background rhythm notes only.
Scope: Global Combat System

## Purpose

Status: SUPERSEDED

Combat is a semi turn-based focus system running on a real-time timeline. It is not traditional full-stop turn-based combat and not fully chaotic real-time combat.

`Combat Focus System v1 (FINAL)` formally overwrites the focus-event timing rules in this file. `Combat Rhythm + Skill Queue UI v1 (FINAL)` overwrites skill queue and normal-attack rhythm rules. This file remains a historical background rhythm reference where not contradicted.

Combat presentation follows `SEE -> UNDERSTAND -> PROCESS`: players must first notice an event, understand who did what to whom, and then have enough time to process it.

The formal direction is `Semi Turn-Based Combat` on a `Real-Time Timeline`:

- Readable.
- Rhythmic.
- Continuous without visual chaos.
- Alive without synchronized action spam.
- Background combat keeps flowing while important events take turns becoming the focus.
- This officially overwrites older anti-focus-timing wording; the forbidden direction is traditional full-stop turn-based combat, not the semi turn-based focus system.

## Battle Duration Targets

| Encounter | Target duration |
| --- | --- |
| Normal battle | 45 to 80 seconds |
| Elite battle | 70 to 110 seconds |
| Boss battle | 120 to 240 seconds |

## Seamless Encounter Flow

Enemy defeat flows into a short pause and a naturally arriving next wave.

- Inter-encounter pause: approximately 0.5 to 1 second.
- Normal enemy arrival: approximately 0.2 to 0.6 seconds.
- Elite arrival: approximately 0.5 to 1 second.
- Boss arrival: approximately 2 to 4 seconds.

Boss presentation should let the environment react, show the Boss arriving, pause briefly, and then start combat. It must not use black screens, warning overlays, or long cutscenes.

## Action Rhythm

| Action | Formal rhythm |
| --- | --- |
| Normal attack | Class rhythm: Guardian 2.6 to 3.0s, Rogue 1.4 to 2.0s, Ranger 1.8 to 2.3s, Mage / Cleric 2.3 to 2.8s |
| Active skill | Approximately 16 to 24 seconds, with mild desynchronization |
| Boss skill | Approximately 24 to 36 seconds |

Normal attacks remain the main output source. Agility affects normal attack rhythm only and does not affect skill cooldown. Active skills enter Global Skill Queue when ready.

## Skill Window Queue

- Only one major skill presentation may play at one time.
- All important events enter Focus Queue.
- Normal attacks are background rhythm and do not enter Focus Queue.
- Recommended spacing between ordinary visible actions is approximately 0.30 to 0.60 seconds.
- A skill may slightly expand spacing to preserve readability without slowing combat excessively.
- Focus Window should last approximately 1.8 to 3 seconds for understanding one focus event.
- Focus Gap should last approximately 1.4 to 3 seconds for breathing room and information digestion.
- The battlefield should read as exchanges of actions rather than continuous group movement.
- Ready actions use a micro stagger timeline: ordinary attacks, summon attacks, and major skills each reserve a short action-focus window so multiple units do not visually act on the same frame.
- Ordinary and summon ready actions use an action stagger interval of approximately 0.35 seconds, tunable within 0.30 to 0.45 seconds, without changing the underlying attack cooldown.
- This pacing pass controls event density; it must not change damage values, monster HP, skill multipliers, drops, monster data, chapter rules, class design, or encounter design.
- Combat must not become traditional full-stop turn-based combat, synchronized cooldown execution, or a frozen party-turn system.
- Focus events must not freeze the whole battlefield; background units downgrade motion, FX brightness, and particle presence instead.

## Focus Queue

Important events include active skills, Boss skills, Elite monster skills, large damage events, summon special skills, important healing skills, and important Buff / Debuff skills.

If multiple focus events are ready at the same time, they enter Focus Queue by priority:

1. Boss skill.
2. Elite skill.
3. Player active skill.
4. Important heal.
5. Background event.

Normal attacks are listed only as lowest visual priority; they do not enter Focus Queue.

## Animation Sequence

Every readable action follows:

1. Wind-up.
2. Attack motion.
3. Hit timing.
4. Hit reaction.
5. Damage number.
6. Recovery.

Attack, damage, and reaction should not all happen on the same frame.

## Major Event Priority

Visual focus priority:

1. Boss skill.
2. Elite skill.
3. Player core skill.
4. Enemy skill.
5. Normal attack.

When a higher-priority event plays, lower-priority actions should visually downgrade or delay slightly.

## Background Events

DOT, Buff ticks, auras, minor healing, small Debuffs, and minor attacks should use low animation, low FX, and minimal screen attention. They must not compete with major events.

## Battlefield Density

- Maximum player units: 4.
- Maximum summons: 1.
- Maximum enemies: 6.
- Unit readability has priority over effect spectacle.

## Visual Noise

- Effects must serve readability.
- Combat follows `Combat Readability v1`: readability first, not effect first.
- Information density is controlled through timing, priority, and visual downgrading rather than simply slowing total combat speed.
- Damage numbers and hit flashes should follow the active action focus instead of appearing as simultaneous unrelated bursts.
- Successful hits use micro hit flash timing, approximately 0.05 to 0.08 seconds for ordinary hit confirmation.
- Damage numbers remain visually consistent above the target body and avoid random scatter.
- Approximately 80% of ordinary attack damage should rely on HP-bar movement without floating numbers.
- Critical hits, recovery, major skills, and Boss skills may carry clearer feedback.
- Buff and Debuff information should collapse when necessary.
- DOT and small repeated effects stay visually quiet and should not emit continuous small-number spam.
- Normal attack motion remains restrained, approximately 5 to 8 pixels.
- Hit targets remain anchored in their battlefield positions; hit feedback uses restrained flashes rather than knockback movement.
- Knockback status effects and forced-displacement combat effects are not part of the formal system.

## Camera

- Camera remains fixed for normal combat.
- Only restrained Boss pressure or very small major-skill feedback is permitted.
- Presentation must not compromise viewing comfort.

## Player Settings

Presentation modes are provided without payment:

- Full.
- Simplified (recommended).
- Minimal.

## Final Rule

Combat must remain readable, comfortable, seamless, and full of adventure feeling.

## Prototype Validation

Dense readability validation uses `combat_readability_prototype_v1`.

The prototype scenario is 4 player units versus 6 enemies.

If dense combat remains crowded, first increase `Focus Gap`. Then tune action-focus micro stagger from 0.35 seconds toward 0.40 to 0.45 seconds. The current test pass uses 0.40 seconds for normal actions, 0.30 seconds for lighter summon actions, and 0.45 seconds for major skill starts. Do not stretch combat into slow traditional turn-based pacing.
