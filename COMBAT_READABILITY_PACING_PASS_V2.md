# COMBAT_READABILITY_PACING_PASS_V2

Version: v2
Status: Implemented
Target: Godot Combat Prototype
Scope: Combat pacing / skill spacing / readability timing

## Purpose

Combat speed is not the main problem. The current readability issue is dense event timing: too many unit actions and skill events can happen before the player can see, understand, and process them.

This pass lowers major event density without turning combat into a traditional full-stop turn-based system.

## Implemented Rules

- Normal attack base interval: 3.6 seconds.
- Normal attack variation: +/- 0.4 seconds.
- Normal attack effective range: approximately 3.2 to 4.0 seconds.
- Focus Window is superseded by `Combat Focus System v1 (FINAL)`: 1.8 to 3 seconds.
- Focus Gap is superseded by `Combat Focus System v1 (FINAL)`: 1.4 to 3 seconds.
- Player active skill interval target: approximately 16 to 24 seconds.
- Boss skill interval target: approximately 24 to 36 seconds.
- Normal attack floating number chance remains approximately 20%.
- Normal hit reaction delay: 0.08 seconds.

## Event Layers

### A Tier: Major Events

Boss skills, Elite skills, player active skills, large monster skills, important healing, and important buffs.

Only one major event may own the visual focus at a time.

### B Tier: Secondary Events

Small skills, small healing, small Buffs, and ordinary monster skills.

They may exist, but should not steal focus.

### C Tier: Background Events

Normal attacks, DOT, Aura, passive effects, small numbers, and status refreshes.

These should remain low-motion and low-attention.

## Do Not Change

This pass does not change character damage, monster HP, skill multipliers, drops, monster data, chapter rules, or class design.
