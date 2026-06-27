# Battle Quick Menu v1

## Purpose

`BattleQuickMenu` is a low-interference portrait overlay for quick expedition-side organization during auto battle.

It exists so the player can review or prepare small inventory, equipment, workshop, enhancement, and Buff/Debuff information without frequently returning to the horizontal tavern base.

## Scene Integration

- Scene: `res://scenes/BattleScene.tscn`
- Controller: `res://scripts/battle_quick_menu.gd`
- Host controller: `res://scripts/battle_scene.gd`
- Orientation: portrait only

## Allowed Entries

- Bag
- Equipment
- Field workshop simplified page
- Enhance simplified page
- Buff/Debuff scroll status page

## Forbidden Entries

- Tavern main base
- Tavern recruitment
- Tavern events
- Horizontal scenes
- Full market or black market pages

## UI Rules

- Uses a small quick entry button.
- Opens a compact right-side overlay panel.
- Does not switch orientation.
- Does not pause battle timers or background motion.
- Can be closed with one tap.
- Avoids full-screen menu behavior.

## Visual Pass v1

Goal: reduce debug-panel feeling and make the quick menu read more like a tactical scroll / caravan status note.

Changes:

- Idle state uses a compact status summary strip instead of a lone debug-like button.
- Expanded category buttons use pixel icon placeholders instead of abstract `B / E / W / + / S` letters.
- Summary categories:
  - Buff
  - Debuff
  - World
  - Aura
  - Summon
- Overlay remains compact and portrait-only.
- No tavern, recruitment, tavern event, horizontal scene, market, or full black market entry is added.

## Current Known Limits

- Bag, equipment, workshop, and enhancement pages are v1 placeholders.
- Status page reads current battle status effects.
- Final icon art is not implemented yet; Visual Pass v1 uses simple pixel color-block placeholders.
