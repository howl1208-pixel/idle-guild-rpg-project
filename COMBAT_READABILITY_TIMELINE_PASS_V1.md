# COMBAT_READABILITY_TIMELINE_PASS_V1

Version: v1  
Status: Implemented  
Target: Godot Combat Prototype  
Scope: Combat animation timing / readability / action focus

## Purpose

Improve combat readability without changing the game into traditional full-stop turn-based combat.

The current tempo is acceptable, but simultaneous unit actions made it difficult to identify who attacked whom. This pass adds a micro stagger action timeline so actions remain real-time while visual events are separated enough to read.

## Implemented Rules

- Ordinary attacks reserve a short action-focus window before the next action can begin.
- Summon attacks use an even lighter action-focus window.
- Major skills reserve a longer action-focus window and still respect the existing major skill queue.
- Single-target skill hits are delayed slightly after the attacker motion.
- Area skill hit feedback is staggered per target.
- Existing v3 combat tempo, no-knockback rule, and low floating-number density remain unchanged.

## Notes

This pass changes visual readability timing, not class design, skill identity, enemy roster, or advancement routes.
