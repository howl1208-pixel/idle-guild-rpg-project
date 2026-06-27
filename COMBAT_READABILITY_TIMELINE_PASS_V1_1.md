# COMBAT_READABILITY_TIMELINE_PASS_V1_1

Version: v1.1
Status: Implemented
Target: Godot Combat Prototype
Scope: Combat animation timing / readability / action focus

## Purpose

Tune the micro stagger action timeline after prototype observation.

The overall combat speed remains acceptable. The issue is visual density: multiple ready actions can still appear too close together, making it hard to identify who attacked whom.

## Implemented Adjustment

- Old ordinary action stagger interval: approximately 0.15 seconds in prototype feel.
- New ordinary action stagger interval: 0.35 seconds.
- Allowed tuning range: 0.30 to 0.45 seconds.
- Normal attack cooldown and skill cooldown are unchanged.
- Major skill spacing remains longer than ordinary action spacing.
- Combat remains real-time auto combat, not traditional full-stop turn-based combat.

## Goal

- Increase combat readability.
- Increase visual breathing room.
- Preserve real-time feeling.
- Avoid traditional full-stop turn-based sensation.
- Improve idle viewing comfort.

## Notes

This pass changes visual timing separation only. It does not change class design, attack speed, skill cooldowns, damage values, enemy rules, or encounter duration targets.
