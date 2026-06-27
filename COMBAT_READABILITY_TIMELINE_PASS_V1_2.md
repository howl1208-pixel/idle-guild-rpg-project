# COMBAT_READABILITY_TIMELINE_PASS_V1_2

Version: v1.2
Status: Implemented
Target: Godot Combat Prototype
Scope: Combat animation timing / readability / action focus

## Purpose

Test a slightly wider micro stagger without reducing the underlying battle pace.

The concern is not attack speed or skill cooldown speed. The concern is that multiple visible actions can still land close enough together to feel chaotic when skills and background attacks overlap.

## Implemented Adjustment

- Normal action visual stagger: 0.40 seconds.
- Summon action visual stagger: 0.30 seconds.
- Major skill action visual stagger: 0.45 seconds.
- Normal attack cooldowns are unchanged.
- Skill cooldowns are unchanged.
- Focus Window remains 1.8 to 3 seconds.
- Focus Gap remains 1.4 to 3 seconds.
- Background auto attack remains active during skill focus.

## Goal

- Improve source/target readability during overlapping skill moments.
- Preserve the real-time auto-combat feel.
- Avoid adding a full-stop turn-based sensation.
- Keep summons present but visually lighter than player/enemy unit actions.

## Protected Areas

This pass does not change portrait layout, travel atmosphere, low number readability, class design, damage values, monster stats, skill cooldowns, or encounter duration targets.
