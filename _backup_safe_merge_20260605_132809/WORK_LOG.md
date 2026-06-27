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
