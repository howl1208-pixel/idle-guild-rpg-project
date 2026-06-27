# COMBAT_SKILL_QUEUE_VISIBILITY_PASS_V1

Version: v1
Status: Implemented
Target: Godot Combat Prototype
Scope: Skill Queue visibility / source-target readability

## Purpose

Improve combat readability without redesigning the combat system.

This pass focuses on two current issues:

- Players need to know who will cast next before the skill fires.
- Players still feel unclear who attacks whom during overlapping actions.

## Implemented Adjustment

- Skills enter the visible Global Skill Queue about one base rhythm tick before Ready, approximately 3.6 seconds in the current prototype.
- Queue display sorts by true `ready_at` time, then by ready order.
- Queued skills do not cast early; they only cast once their cooldown reaches Ready.
- Boss skill cooldown resets on actual queued cast attempt, not when it first appears in the visible queue.
- Ranged normal attacks now show a short, low-opacity source-target line.
- Melee normal attacks do not show Target Line and read through motion, attacker cue, and hit reaction.
- Attackers briefly micro-highlight when their action cue starts.
- Summon melee attacks do not show Target Line.
- Skill and heal focus events reuse the same source-target readability cue.

## Protected Areas

This pass does not change:

- Travel atmosphere.
- Low-number RPG direction.
- No front/back row system.
- Overall battle pace.
- Damage values.
- Monster HP.
- Skill multipliers.
- Skill cooldown targets.
- Encounter duration targets.
- Portrait layout.

## Goal

Players should more naturally understand:

- Who is about to cast.
- Which unit started the current action.
- Which unit is being hit or healed.

The cue must remain low-interference and should not become an MMO-style target lock UI. Target Line is reserved for ranged or specified-target actions; melee exchanges should not use line clutter.
