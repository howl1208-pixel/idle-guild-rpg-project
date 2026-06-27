# Expedition Route Panel v1

## Purpose

`ExpeditionRoutePanel` creates the first playable main loop entry:

```text
Tavern Main Base
-> Map Table
-> Expedition Route Panel
-> Choose One Route
-> Confirm Expedition Preference
-> Start Expedition
-> Battle Scene
```

The panel is a restrained modal overlay over the visible tavern. It is not a complex world map and does not add free movement.

## Scene Integration

- Tavern scene: `res://scenes/TavernMainScene.tscn`
- Panel scene: `res://scenes/ExpeditionRoutePanel.tscn`
- Panel controller: `res://scripts/expedition_route_panel.gd`
- Tavern entry point: `MapTablePoint`
- Battle destination: `res://scenes/BattleScene.tscn`

## Chapter 1 Fixed Region Data

Region: `kingdom_border` / 王國邊境

Routes:

| Route ID | Route | Danger | Type | Monsters | Drops |
|---|---|---|---|---|---|
| `grassland_trade_road` | 草原商路 | 低 | 平衡型 | 野狼、哥布林 | 基礎素材 |
| `border_camp` | 邊境營地 | 中低 | 人型敵人 | 流亡士兵、盜匪 | 裝備素材 |
| `swamp` | 潮濕沼地 | 中 | 毒系生態 | 污染史萊姆、毒蟲 | 中毒素材 |

Data is deliberately fixed in script for v1. It is not database-backed.

## Interaction Rules

- One route may be selected at a time.
- Selected route gains a warm highlighted border and slightly brighter card.
- Start expedition requires a selected route.
- Close returns the player to the visible tavern.
- Escape also closes the panel.

## Expedition Settings Placeholder

Modes:

- 平衡探索
- 素材收集
- 裝備狩獵
- 高價值探索 (default)

Priority display is currently informational only:

- 普通素材：低
- 中階素材：中
- 高階素材：高
- Boss素材：最高
- 裝備：中

## Transition

On start, the panel stores the selected route ID as scene-tree metadata before entering the battle scene:

- `selected_expedition_route`

The viewport is restored from tavern landscape to battle portrait before changing to `BattleScene`.

## Known Limits

- Route choice is stored but does not yet alter encounter tables or rewards.
- Expedition preference is UI placeholder state only and is not passed to battle.
- Route card visuals currently use UI styles pending final pixel artwork.
