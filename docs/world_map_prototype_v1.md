# World Map Prototype v1

Status: PROTOTYPE / INTERACTION VALIDATION
Formal alignment source: `GAME_CURRENT_VERSION.md`

## Goal

Validate:

```text
Hub Tavern
-> six-seat round table
-> 1.2 second zoom transition
-> World Map
-> Region selection
```

## Current Pass: Mobile Portrait Navigation Screen

- Central Kingdom as a non-selectable map center.
- Six clickable available regions arranged around the central kingdom.
- Fogged unavailable-region silhouettes reserved for future expansion.
- Low-interference single-selection highlight.
- Selected region name display.
- Selected region status display: `Available`.
- Return to Hub Tavern button.

## Excluded

- Final art.
- Travel content.
- Region content.
- Chapter or stage lists.
- Chapter selection menus.
- Save data and progression unlock logic.
- Camera, Drag, or Zoom.
- Large draggable world map behavior.

## Acceptance Command

```powershell
& 'C:\Users\User\Desktop\Godot_v3.6.1-stable_win64.exe' `
  --path . --headless -s res://scripts/world_map_acceptance.gd
```

The acceptance script verifies:

- Clicking the six-seat round table starts and locks the transition.
- Six available regions are visible and clickable.
- Selecting a region displays its name and `Status: Available`.
- Selecting a second region replaces the first selected state.
- Fog placeholder regions exist for future expansion.
- Return to Hub Tavern button wiring remains valid.

## Open Regions

- 王國邊境
- 旅人荒境
- 骷髏荒原
- 沙漠遺城
- 聖堂國境
- 森靈秘境

Unavailable regions are represented only as fogged silhouettes for future
expansion. They are not selectable and do not start travel.
