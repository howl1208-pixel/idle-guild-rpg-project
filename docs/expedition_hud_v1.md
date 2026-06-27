# Expedition HUD Pass v1

## Purpose

`ExpeditionHUD` adds small expedition context and player retreat control to the existing portrait battle screen without redesigning combat layout.

## Scene Integration

- Host scene: `res://scenes/BattleScene.tscn`
- HUD scene: `res://scenes/ExpeditionHUD.tscn`
- HUD controller: `res://scripts/expedition_hud.gd`
- Retreat destination: `res://scenes/ExpeditionRewardSummaryPanel.tscn`

## Collapsed Strip

The HUD remains visible as a compact top-left strip below the battle header:

- Current route, read from `selected_expedition_route`.
- Expedition elapsed time for the active battle visit.
- Capacity placeholder display: `Bag 0 / 120`.
- One expand/collapse action button.

The strip avoids the right-side `BattleQuickMenu` summary and does not cover the primary unit layout.

## Expanded Actions

The player may expand a small action panel containing:

- `Workshop`: placeholder feedback only.
- `Inventory`: placeholder feedback only.
- `Retreat to Tavern`: records elapsed display time and opens the expedition reward summary report.

Escape closes the action panel when it is open.

## Guardrails

- Combat continues automatically while the HUD is open.
- No combat system, encounter, reward, or capacity logic is introduced.
- The panel is compact and intentionally non-modal.
- No tavern redesign is included.

## Known Limits

- Capacity use is not yet connected to dropped items.
- Elapsed time currently measures time spent in the active battle scene only.
- Workshop and inventory actions are informational placeholders.
- Selected route does not yet change enemy or reward data.
