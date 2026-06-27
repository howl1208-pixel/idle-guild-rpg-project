# travel_loop_current.md

Status: CURRENT / SINGLE SOURCE SUMMARY
Purpose: Current single-source recovery document for the travel and expedition loop after context loss.
Sources: GAME_CURRENT_VERSION.md, CURRENT_PROJECT_STATE.md, CHANGELOG.md, DEVLOG.md, WORK_LOG.md.

This document consolidates already-recorded current direction only. It does not add new features, new routes, new reward rules, new economy rules, or new expedition logic.

---

## 1. Core Direction

The travel loop belongs to the project's locked direction:

- Low-fatigue, readability-first portrait idle RPG with travel atmosphere.
- Player control feeling is higher priority than pure travel feeling.
- Tavern-first home scene: Hub Tavern.
- Long-term comfortable watching.
- Low-interference UI.

Travel atmosphere must be preserved when uncertain.

---

## 2. Formal High-Level Flow

Formal current flow:

```text
Hub Tavern
-> six-seat round table / World Map entry
-> World Map / route selection direction
-> Expedition begins
-> Battle loop
-> Player retreat
-> Return / report flow
-> Tavern
```

Older recorded MVP flow also exists as:

```text
Tavern -> map table -> expedition -> battle -> return tavern
```

Current runtime alignment after Safe Merge Stage 1:

- `project.godot` starts at `res://scenes/HubTavernPrototype.tscn` for verification.
- `res://scenes/WorldMapPrototype.tscn` is entered through the six-seat round table prototype flow.
- Existing `res://scenes/TavernMainScene.tscn` is preserved unchanged as rollback / legacy implementation.
- The safe merge did not add expedition logic, combat behavior, or worldbuilding changes.

---

## 3. Formal Expedition / Idle Loop

Formal expedition loop:

```text
Encounter enemy
-> auto battle
-> obtain drops
-> scene / journey progression
-> encounter event
-> elite monster randomly
-> Boss randomly
-> loop
```

Formal rules:

- Player does not leave the selected area before retreat.
- Bag full stops pickup.
- Gold and EXP accumulate up to 12 hours.
- Bag uses party capacity, not grid inventory.
- Capacity progression recorded in the formal version: 120 -> 180 -> 260 -> 360 -> 500 -> 800+.

Expedition pickup modes recorded in the formal version:

- Balanced Exploration
- Material Collection
- Equipment Hunting
- High Value Exploration

These modes are recorded as direction / UI state only where implementation notes say they are placeholders. Do not treat them as implemented economy behavior unless a later current document explicitly says so.

---

## 4. Chapter 1 Route Direction

The formal Chapter 1 area is Kingdom Borderlands / Kingdom Border direction.

Recorded Chapter 1 routes:

- Grassland Trade Road
- Border Camp
- Swamp

Known implementation state from route-selection notes:

- `ExpeditionRoutePanel` was added as a low-interference route overlay opened from the tavern map table in the older TavernMainScene flow.
- Route selection passes only the selected route ID into BattleScene.
- Route selection currently does not modify enemy encounters, reward pools, or battle background.
- Expedition preference remains display / selection state only until expedition rules are built.

Current Hub Tavern v2.2 / World Map prototype does not change these expedition rules.

---

## 5. Formal Travel Segment Shape

Battle should not move directly from one finished fight into the next fight like a continuous monster generator.

The current travel-feel direction is:

```text
Battle End
-> Recovery & Gather
-> Travel
-> Optional Micro Event
-> Encounter Foreshadow
-> Battle Start
```

Purpose:

- Make the expedition party feel like it is moving through a route.
- Give the player a quiet travel beat between readable combat encounters.
- Preserve travel atmosphere without adding high-interference UI.
- Keep combat from feeling like monsters are being spawned back-to-back.

Pure travel segment rule:

- Surviving characters may recover 15% to 30% of max HP during pure travel segments.
- This recovery matters because living party HP persists into the next encounter in the prototype.
- This is a travel-feel / recovery rule, not a new combat balance system.

Micro event direction:

- Gathering.
- Merchant traces.
- Lost coin pouch.
- Low-frequency treasure chest.
- Third-party skirmish / melee in the distance.

Log direction:

- Travel events, drops, gathering results, and travel finds may share Loot Log / Story Log presentation.
- Use low-frequency, low-interference records.
- Do not create a separate noisy travel message system unless explicitly requested.

This section records direction only. It does not add formal event tables, rewards, inventory mutation, or implementation requirements.

---

## 6. Travel Loop Prototype v1

Travel Loop v1 is recorded as a REVIEW-stage expedition travel-feel prototype.

Implemented prototype behavior in `battle_scene.gd`:

- Victory enters a lightweight post-battle travel state instead of immediately starting the next encounter after a fixed 0.75 second gap.
- Recovery & Gather phase exists after battle.
- Travel segments last 4 to 8 seconds.
- Encounter travel uses weighted 1 / 2 / 3 segment selection: 50% / 35% / 15%.
- Living party members heal during travel for 15% to 30% max HP.
- Living party HP persists into the next encounter so travel-only healing matters.
- Low-frequency travel micro events may occur.
- Equipment drops, travel finds, and micro-event rewards publish through the shared Loot log.
- Travel Drift uses the existing depth overlay as a restrained prototype cue.
- Defeated enemies are hidden between encounters while party formation and fixed camera are preserved.

Protected scope from the prototype pass:

- Did not change combat rules.
- Did not change combat readability.
- Did not change damage values.
- Did not change monster stats.
- Did not change Skill Queue.
- Did not change Boss behavior.
- Did not change party formation.
- Did not change camera.
- Did not finalize travel atmosphere direction.

Known issues / not finalized:

- Travel timing requires live-feel validation.
- Healing amount requires live-feel validation.
- Micro-event frequency requires validation.
- Encounter weighting requires validation.
- Route materials are Loot-log prototype entries only.
- No material inventory mutation exists yet.

---

## 7. Encounter Progression

Current combat / journey progression notes include:

- Ordinary travel battles, elite encounters, and Boss encounters are weighted route encounters.
- Boss chance increases while travelling and resets after a Boss appears.
- Fixed every-fifth-encounter Boss appearance was removed.
- Ordinary route encounters can use 3 to 6 ground enemies.
- Airborne enemies are disabled throughout currently playable Chapter 1 routes and reserved for later chapters.
- Normal / Elite / Boss duration targets remain combat-system governed.

Do not invent route-specific enemy tables here. Monster and drop naming must follow monster_database.md when used.

---

## 8. Expedition HUD / Retreat / Report

Implemented prototype state:

- `ExpeditionHUD` exists as a compact collapsible expedition strip inside `BattleScene`.
- It displays selected route as readable route name.
- It displays active-scene expedition elapsed time.
- It shows capacity placeholder display: `Bag 0 / 120`.
- It has placeholder Workshop and Inventory actions.
- Player-controlled retreat exists.
- Retreat routes through `ExpeditionRewardSummaryPanel` before returning to tavern in the older TavernMainScene loop.

Reward summary implemented presentation:

- Shows selected route name with fallback.
- Shows active battle-visit duration.
- Shows mocked gold, EXP, materials, defeated enemies, elite encounter, Boss encounter, and capacity result.
- Confirm / close returns to tavern.

Known limitations:

- Reward, encounter, and capacity report values are mocked presentation only.
- Duration measures active battle scene visit only.
- Capacity consumption is not connected to loot data.
- Expedition elapsed time does not persist across scene changes.
- Workshop and Inventory buttons remain placeholder feedback only.
- No real economy or reward settlement is applied from the report.

---

## 9. Current Runtime Scenes

Current recorded scene state:

- Current project main scene after Safe Merge Stage 1: `res://scenes/HubTavernPrototype.tscn`.
- World Map Prototype: `res://scenes/WorldMapPrototype.tscn`.
- Existing tavern scene retained unchanged: `res://scenes/TavernMainScene.tscn`.
- Battle scene remains the combat / expedition battle runtime: `res://scenes/BattleScene.tscn`.
- Older route selection overlay exists: `res://scenes/ExpeditionRoutePanel.tscn`.
- Expedition HUD exists: `res://scenes/ExpeditionHUD.tscn`.
- Reward summary exists: `res://scenes/ExpeditionRewardSummaryPanel.tscn`.

Do not assume these flows are fully unified. The safe merge explicitly did not add expedition logic.

---

## 10. Explicit Non-Goals

Do not add or infer:

- New expedition logic.
- New route reward pools.
- New material inventory mutation.
- New route enemy tables.
- New worldbuilding.
- New combat behavior.
- New economy settlement.
- New market / black market systems.
- New traveller recruitment implementation.

Do not modify combat to support travel unless explicitly requested.

---

## 11. Verification History

Recorded verification:

- Godot 3.6.1 headless `BattleScene.tscn` startup passed after Travel Loop Prototype v1.
- Godot 3.6.1 startup passed for `TavernMainScene`, `ExpeditionRoutePanel`, and project main scene after WorldMap / Expedition Route Select Pass v1.
- Safe Merge Stage 1 verified Hub Tavern v2.2 / World Map Prototype startup and acceptance separately.


