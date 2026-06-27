# Travel Loop Prototype v1

Version: v1
Status: REVIEW
Scope: Expedition Combat Prototype

## Purpose

Validate whether the expedition party feels like it is traveling between battles.

Prototype flow:

`Battle End -> Recovery & Gather -> Travel -> optional Micro Event -> Travel -> Encounter Foreshadow -> Battle Start`

## Implemented Prototype Rules

- Post-battle loot publishes after a random 0.5 to 1.5 second Recovery & Gather pause.
- Pure travel segments last 4 to 8 seconds.
- Each completed pure travel segment heals living party members for 15% to 30% max HP.
- Encounters occur after 1 to 3 travel segments using 50% / 35% / 15% weighting.
- Micro events occur about once every 5 to 10 completed travel segments.
- Prototype micro events: Wilderness find, Merchant trail, Lost pouch.
- Monster drops and travel finds share the Loot log.
- Encounter foreshadow lasts 0.5 to 1.0 seconds and uses a restrained dust cue.
- Travel Drift stops during Recovery, Micro Event pause, Foreshadow, and combat.
- Background micro-atmosphere remains available; no camera movement, warning icon, screen shake, or push-in is added.

## Validation Only

Validate:

1. Expedition travel feeling.
2. Whether the loop avoids feeling like a monster-spawn simulator.
3. Comfortable pacing.
4. Whether micro events interrupt too often.
5. Whether enemy approach feels natural.
6. Whether Recovery & Gather feels reasonable.

Do not validate art quality, content volume, or numerical balance in this pass.