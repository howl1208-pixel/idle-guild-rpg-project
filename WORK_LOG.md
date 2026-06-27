# WORK_LOG

## 2026-06-02

### Current Focus

Combat Prototype Phase 2:

- Combat Event Scheduler
- Global Skill Queue
- Global Normal Attack Beat
- Skill Focus Slow
- Queue Readability v1 polish and readability validation

### Current Implementation Target

- `res://scripts/battle_scene.gd`
- `res://scenes/BattleScene.tscn`

### Current State

- Boss readability prototype is implemented.
- Skill Queue preview and positioning are implemented.
- Buff panel placement has been adjusted.
- Summon reserve readability pass is implemented.
- Global Skill Queue already exists in `battle_scene.gd`.
- Global Normal Attack Beat already exists in `battle_scene.gd`.
- Skill Focus Slow already exists in `battle_scene.gd`.
- Battle speed is fixed at `x1` through `_get_battle_speed()`.
- Godot 3 parser error at `battle_scene.gd:550` is fixed by using explicit `bool` typing instead of ambiguous `:=` inference.
- Godot 3 parser error at `battle_scene.gd:565` is fixed by validating loaded summon icon resources before returning them as `Texture`.
- Godot 3 parser error at `battle_scene.gd:567` is fixed by explicitly casting the validated resource with `as Texture`.
- Combat Prototype Phase 2 cleanup is implemented.
- Deterministic 4v6 acceptance path is available through `--phase2-4v6-acceptance`.
- Legacy layout and tempo docs are marked superseded where appropriate.
- Combo Exception Rule is DESIGN LOCKED / NOT IMPLEMENTED in `docs/combat_phase2_cleanup_notes.md`.
- `CURRENT_PROJECT_STATE.md` is created as the recovery handoff after context loss.
- `queue_readability_v1.md` is added as FINAL queue readability polish direction.
- Queue Readability v1 is implemented in `battle_scene.gd`: wider timeline, larger queue slots, first-slot 125% emphasis, later-slot hierarchy, and quiet entry/exit/reflow motion.
- BattleScene `_apply_button_style()` Nil runtime error is fixed by removing the obsolete missing `QuickToggleButton` style target and adding null guards to shared style helpers.

### Protected Scope

Do not change:

- Combat pacing
- Travel atmosphere
- Portrait layout
- Low-fatigue philosophy
- Damage values
- Monster HP
- Skill cooldown targets
- Active summon count rules
- Boss focus direction

### Current Validation Direction

Phase 2 should validate scheduler behavior through:

- Placeholder Skill Queue UI
- Queue readability and timeline progression
- Battle log entries
- Headless Godot startup checks
- Direct `BattleScene.tscn` startup checks

Do not add:

- Formal FX
- Polish animations
- Cinematic pauses
- Large warning UI
- New combat systems outside the scheduler scope

### Latest Completed Pass

Queue Readability v1:

- Skill Queue width is extended by roughly 30%.
- Queue slots and portraits are larger for portrait readability.
- First slot is emphasized at 125%; later slots step down to 100%, 95%, and 90%.
- Player queue entries micro-slide upward into the queue; enemy/Boss entries micro-slide downward.
- Queue exit and reflow use short low-fatigue transitions.

### Known Issues

- `WORK_LOG.md` was missing before this pass and is now created.
- Summon reserve icons reuse existing buff/debuff/state icons until dedicated summon icons are produced.
- Portrait viewport review is still needed for:
  - Skill Queue placement
  - Queue Readability v1 scale, hierarchy, entry motion, exit fade, and reflow
  - Boss queue emphasis
  - Boss ready body brightness
  - Summon reserve bar placement
  - Target Line opacity and duration

### Recommended Next Step

Run Phase 2 acceptance from Godot with `--phase2-4v6-acceptance`, then review whether Queue Readability v1 makes the next caster and later timeline naturally understandable.

## 2026-06-05 Safe Merge Stage 1

- Merged Hub Tavern v2.2 / World Map Prototype v1 files back into the real Godot project from `C:\Users\User\Documents\Codex\2026-06-04\hub-tavern-v2-1-2-3`.
- Added `res://scenes/HubTavernPrototype.tscn`, `res://scenes/WorldMapPrototype.tscn`, `res://scripts/hub_tavern_prototype.gd`, `res://scripts/world_map_prototype.gd`, `res://scripts/world_map_acceptance.gd`, and `res://docs/world_map_prototype_v1.md`.
- Switched `project.godot` main scene to `res://scenes/HubTavernPrototype.tscn` for startup verification.
- Kept `res://scenes/TavernMainScene.tscn` unchanged as the existing tavern scene and rollback point.
- Did not modify combat systems, BattleScene, expedition logic, or worldbuilding rules.

## 2026-06-06 Travel / Traveller Current Spec Documentation

### Added

- Updated `travel_loop_current.md` with the formal travel segment shape: Battle End -> Recovery & Gather -> Travel -> Optional Micro Event -> Encounter Foreshadow -> Battle Start.
- Recorded travel atmosphere intent: expeditions should feel like the party is moving, not like a continuous monster generator.
- Recorded pure travel recovery direction: surviving characters may recover 15% to 30% max HP during travel segments.
- Recorded travel micro-event examples: gathering, merchant traces, lost coin pouch, low-frequency treasure chest, and third-party skirmish.
- Updated `traveller_system_current.md` with Upper / Lower traveller areas, Day / Dusk / Night refresh direction, passerby replacement, prerequisite-profession weighting, hidden-profession safety, and non-chapter-locked appearance direction.

### Protected

- Documentation only.
- Did not modify Godot scenes.
- Did not modify scripts.
- Did not modify combat systems.
- Did not implement recruitment logic.
- Did not add characters.
- Did not change class trees.

## 2026-06-07 Material Usage Master Database Chapter 01

### Added

- Added `material_usage_master_database.md` as a material usage category mapping database subordinate to `monster_material_master_database.md`.
- Completed Chapter 01 / Kingdom Borderlands material usage category mapping.
- Added reserved empty sections for Chapter 02, Chapter 03, Chapter 04, and Chapter 05.

### Protected

- Did not create new materials.
- Did not modify material names.
- Did not create numerical values.
- Did not create drop rates.
- Did not create recipes.
- Did not modify Godot scenes or scripts.
- `裝備設計.txt` is marked NOT REQUIRED FOR CURRENT PHASE because this pass only maps material -> source monster -> usage category. Equipment-design references should be requested again for `semi_finished_material_database.md`, `recipe_database.md`, or `equipment_database.md`.

