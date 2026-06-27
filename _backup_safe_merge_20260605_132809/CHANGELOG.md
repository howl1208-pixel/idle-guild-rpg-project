# Changelog

## 2026-06-04

### Added

- Added `travel_loop_prototype_v1.md` as a REVIEW-stage expedition travel-feel prototype.
- Added post-battle Recovery & Gather, 4-to-8-second travel segments, low-frequency micro events, and restrained encounter foreshadow.

### Changed

- Victory now flows into the Travel Loop prototype instead of starting the next encounter after a fixed 0.75-second gap.
- Travel segments heal living party members for 15% to 30% max HP and use 1/2/3 segment encounter weighting of 50% / 35% / 15%.
- Living party HP now persists into the next encounter so travel-only healing has meaningful effect.
- Equipment drops, travel finds, and micro-event rewards now publish through the shared Loot log.

### Protected

- Did not change combat rules, combat readability, damage values, monster stats, Skill Queue, Boss behavior, party formation, camera, or finalized travel atmosphere direction.

### Verified

- Verified Godot 3.6.1 headless `BattleScene.tscn` startup after Travel Loop Prototype v1.
## 2026-06-03

### Added

- Added `queue_readability_v1.md` as the FINAL Queue readability polish direction.
- Added a third `Story` battle-log tab with a non-blocking unread marker for new important events.
- Added Story event records for Boss arrival, Boss major skills, player-character deaths, and Boss defeat.
- Added Death Recap v1: player deaths include the latest three damage/healing records and their sources.

### Changed

- Implemented Queue Readability v1 polish in `battle_scene.gd`: the Skill Queue is wider, larger, brighter, and more timeline-like for portrait readability.
- Added Queue visual hierarchy: first slot 125%, second slot 100%, third slot 95%, and later slots 90%.
- Added quiet Queue entry, exit, and reflow motion using short fade and micro-slide transitions.

### Protected

- Did not change combat tempo, skill cooldowns, target-line behavior, damage values, monster HP, Boss rules, or combat system direction.
- Did not change SUP placement, Skill Queue behavior, Loot rules, Boss behavior, damage values, or combat rules while adding Story logs.

### Verified

- Verified Godot 3.6.1 headless `BattleScene.tscn --phase2-4v6-acceptance` startup after Queue Readability v1.
- Verified Godot 3.6.1 headless `BattleScene.tscn` and `BattleScene.tscn --phase2-boss-readability-acceptance` startup after Story log and Death Recap v1.

## 2026-06-02

### Added

- Added `docs/combat_phase2_cleanup_notes.md` for Phase 2 cleanup status, deterministic 4v6 acceptance usage, and Combo Exception Rule implementation state.
- Added a CLI-only `--phase2-4v6-acceptance` BattleScene path for deterministic 4 player vs 6 enemy validation.
- Added active-state visuals for the four summon reserve slots in `battle_scene.gd`.
- Added compact summon icons to the active summon slot and reserve bar using existing low-interference icon assets.
- Added `COMBAT_SKILL_QUEUE_VISIBILITY_PASS_V1.md` to document the implemented skill queue preview and source-target readability pass.
- Added `combat_target_line_rule_v2.md` as a REVIEW-stage Target Line usage rule for ranged and specified-target actions.
- Added `combat_normal_attack_rhythm_v2.md` as a REVIEW-stage normal attack rhythm rule.
- Added `combat_global_normal_attack_beat_v1.md` as a REVIEW-stage Global Normal Attack Beat rule.
- Added `boss_focus_weight_v1.md` as a FINAL Boss focus readability rule.
- Added low-interference source-target readability cues for normal attacks, summon attacks, skills, Boss skills, and heals.

### Changed

- Updated README combat prototype notes to remove obsolete speed button, fixed 5-enemy, fixed Boss cycle, and character-side cooldown UI descriptions.
- Updated `docs/battle_ui_current_layout_v2.md` to describe current Skill Queue, fixed 1x playback, 6 enemy slots, and weighted Boss encounters.
- Marked legacy `battle_ui_current_layout.md`, `docs/combat_tempo_rules.md`, and `combat_tempo_v2.md` as superseded historical references.
- Empty summon reserve slots now render as high-transparency frames, while living player summons naturally fill the leftmost reserve slot.
- Summon reserve visuals now refresh during normal UI updates and when a summon dies.
- Skill Queue entries now appear about one base rhythm tick before Ready, approximately 3.6 seconds in the current prototype, while skills still only cast after cooldown reaches Ready.
- Skill Queue display now sorts by true `ready_at` timing, then ready order, so the leftmost visible unit remains the next real caster.
- Boss skill cooldown now resets on actual queued cast attempt instead of visible queue entry, preserving the preview window without changing Boss skill timing.
- Normal attack timing now uses `Base Rhythm × SPD Modifier`, with a hard minimum interval of 1.0 second.
- Retuned normal attack base rhythm slower for readability: Guardian 3.6s, Ranger 2.7s, Mage/Cleric 3.4s, beast enemies 2.6s, minions 3.2s, and Boss/heavy units 4.0-4.4s before speed modifier and jitter.
- Added Global Normal Attack Beat in `battle_scene.gd`: ordinary player, enemy, and summon normal attacks now share a 1.0-second minimum global attack node.
- During Skill Focus Slow, the Global Normal Attack Beat advances at the same slowed schedule rate, so the 1.0-second beat feels approximately 2.0 seconds during skill focus.
- Changed normal attack dispatch from fixed player/enemy scan order to a ready-candidate weighted selection where speed increases the chance to take the next global normal attack node.
- Added Boss Skill focus priority to Skill Queue entries; Boss skills now sort ahead of other focus events as S Priority.
- Added low-presence Boss queue emphasis: when Boss is the first queue slot, the queue portrait uses 112% micro-scale and subtle brightness.
- Added Boss ready body micro-brightness while Boss skill is queued, without adding permanent spotlight, camera force, or warning FX.
- Target Line usage now follows v2 REVIEW direction: ranged normal attacks, ranged/magic skills, heals, and Boss specified-target skills may show lines; melee attacks and summon bites do not show Target Line.
- Melee actions retain a brief attacker micro-highlight, forward motion, hit reaction, and HP change instead of line clutter.
- Updated `GAME_CURRENT_VERSION.md` and `combat_system_current.md` with the queue preview and source-target readability rules.

### Protected

- Did not modify `combat_system_current.md`, combat tempo values, damage values, monster HP, skill cooldown targets, travel atmosphere, portrait layout, or low-fatigue combat direction during Phase 2 cleanup.
- Did not change active summon count, summon combat behavior, combat pacing, portrait layout, damage values, or travel atmosphere during the summon reserve UI pass.
- Did not change travel atmosphere, low-number RPG direction, no-front/back-row combat, overall battle pace, damage values, monster HP, skill multipliers, skill cooldown targets, or encounter duration targets.
- Did not change Skill Queue ordering, Skill Focus Slow, skill cooldowns, skill priority, damage values, or monster stats while retuning normal attack rhythm.
- Did not add combo/double-strike systems; the combo exception is documented only as a future Attack Package rule.
- Did not add cinematic pauses, forced camera, giant warning effects, raid-alert UI, or permanent Boss spotlight.

### Verified

- Fixed the BattleScene runtime Nil call in `_apply_button_style()` by removing the obsolete missing `QuickToggleButton` styling reference and adding null guards to shared style helpers.
- Verified Godot 3.6.1 headless `BattleScene.tscn` startup with `--phase2-4v6-acceptance`.
- Fixed the Godot 3 parser error at `battle_scene.gd:567` by explicitly casting the validated loaded resource with `as Texture`.
- Fixed the Godot 3 parser error at `battle_scene.gd:565` by validating loaded summon icon resources before returning them as `Texture`.
- Fixed the Godot 3 parser error at `battle_scene.gd:550` by replacing ambiguous `:=` inference with an explicit `bool`.
- Verified Godot 3.6.1 headless project startup after the summon reserve UI pass.
- Verified Godot 3.6.1 headless `res://scenes/BattleScene.tscn` startup after the summon reserve UI pass.
- Verified Godot 3.6.1 headless project startup after Skill Queue Visibility, Target Line v2, Normal Attack Rhythm v2, Global Normal Attack Beat v1, and Boss Focus Weight v1 changes.
- Verified Godot 3.6.1 headless `res://scenes/BattleScene.tscn` startup returned without reported parser or startup errors.

## 2026-05-30

### Added

- Added finalized `combat_rhythm_and_skill_queue_ui_v1.md` for Global Skill Queue, Skill Queue UI, skill-focus Slow State, agility/skill-CD separation, and removal of character-side skill cooldown UI.
- Added `combat_readability_expansion_v1_review.md` as a REVIEW-stage prototype plan for 4-player versus 6-enemy readability, Target Line, Skill Reading Window, and Skill FX layering validation.
- Added final `combat_focus_system_v1.md` and authorized Semi Turn-Based Combat focus timing as the formal combat focus direction.
- Added locked `combat_readability_prototype_v1.md` to define 4-player versus 6-enemy readability validation.
- Added locked `combat_readability_v1.md` for target, hit, damage number, status, and skill FX readability rules.
- Added locked `combat_tempo_v2.md` for micro-staggered real-time combat readability.
- Added `COMBAT_READABILITY_PACING_PASS_V2.md` to document the major-event density and skill-spacing tuning pass.
- Added `COMBAT_READABILITY_PHILOSOPHY_V1.md` as the locked direction for all-chapter combat readability.
- Added `COMBAT_READABILITY_TIMELINE_PASS_V1_2.md` to document the micro stagger timing test for overlapping skill moments.
- Added `COMBAT_READABILITY_TIMELINE_PASS_V1_1.md` to document the first action-stagger tuning pass after prototype observation.
- Added `COMBAT_READABILITY_TIMELINE_PASS_V1.md` to document the micro stagger action timeline implementation.

### Changed

- Implemented `Combat Rhythm + Skill Queue UI v1`: player skills and Boss skills now enter a Global Skill Queue by ready order.
- Added Skill Queue UI above the battle log with up to 6 queued unit portraits and a subtle next-caster highlight.
- Hid character-side skill cooldown labels and removed skill-ready status icon pressure from unit-side status icons.
- Added skill-focus Slow State behavior by advancing ordinary action timers at approximately 50% speed during important skill focus.
- Implemented class-specific normal attack rhythm for Guardian, Ranger, Mage, and Cleric, with speed-based fallback timing for other units.
- Tuned action-focus micro stagger for readability testing: normal actions now use 0.40 seconds, summons use a lighter 0.30 seconds, and major skill starts use 0.45 seconds without changing attack cooldowns or skill cooldowns.
- Added four high-transparency summon reserve UI slots as a visual reservation without changing current summon count rules.
- Authorized `Combat Rhythm + Skill Queue UI v1` as FINAL and updated `GAME_CURRENT_VERSION.md`.
- Implemented the REVIEW-stage Combat Readability Expansion prototype in `battle_scene.gd`: low-presence Target Line, Skill Reading Window ordering, delayed skill hit feedback, and reviewed Focus Window / Focus Gap timing for important events.
- Kept normal melee basic attacks free of Target Line so melee still reads through step-in and Hit Reaction.
- Updated `Combat Focus System v1 (FINAL)` to the reviewed timing version: Focus Window is now 1.8 to 3 seconds and Focus Gap is now 1.4 to 3 seconds.
- Formalized that `Combat Focus System v1` overwrites the focus-event timing rules of `combat_tempo_v2` and `combat_readability_v1`, while those files remain background rhythm and visual-fatigue references.
- Updated the formal adjustment order: if dense combat is still chaotic, increase Focus Gap first, then tune `ACTION_STAGGER_INTERVAL` toward 0.40 to 0.45.
- Overwrote the prior anti-focus-timing conflict language: formal combat is now Semi Turn-Based Combat on a Real-Time Timeline, where background combat keeps flowing and important events enter Focus Queue.
- Updated combat tempo and battle rules so important events take focus one at a time, while normal attacks remain background rhythm and do not enter Focus Queue.
- Added the prototype adjustment rule: if 4-player versus 6-enemy combat remains crowded, tune `ACTION_STAGGER_INTERVAL` toward 0.40 to 0.45 seconds before considering any other readability change.
- Aligned ordinary and area hit flashes with `Combat Readability v1` by shortening hit confirmation flashes to 0.08 seconds.
- Removed the outdated battle UI document note that described target knockback.
- Superseded the previous `Combat Tempo v2 (LOCK)` Boss focus/telegraph windows with `Combat Focus System v1 (FINAL)`: Focus Window 1.8 to 3 seconds and Focus Gap 1.4 to 3 seconds.
- Marked the previous 2.5 to 3.5 second major-event spacing and 0.60 to 1.20 second Boss focus windows as outdated by the reviewed FINAL focus system.
- Removed the battle speed button from `BattleScene` and fixed combat playback at 1x.
- Removed `x1 x2` speed text from the battle top bar.
- Kept `COMBAT_READABILITY_PACING_PASS_V2` normal attack timing at a 3.6-second baseline with +/-0.4-second variation, while superseding its long major-event spacing with `Combat Tempo v2 (LOCK)`.
- Retuned player active skill cooldown ticks to target approximately 16 to 24 seconds and Boss skill timing to approximately 24 to 36 seconds without changing damage, monster HP, skill multipliers, drops, chapters, or class design.
- Added a 0.08-second normal hit reaction delay to clarify attacker-to-target cause and effect.
- Added `SEE -> UNDERSTAND -> PROCESS`, major event priority, and background-event downgrading rules to the formal combat direction.
- Tuned ordinary and summon ready-action separation to a fixed 0.35-second action stagger interval without changing attack cooldowns or skill cooldowns.
- Implemented `COMBAT_READABILITY_TIMELINE_PASS_V1` with short action-focus windows so simultaneous ready actions do not visually fire on the same frame.
- Added separate action-focus spacing for ordinary attacks, summon attacks, and major skills while preserving real-time auto combat.
- Staggered single-target skill hit feedback and area-skill hit feedback so attack source and target are easier to identify.
- Updated combat tempo rules to explicitly require the micro stagger timeline for ready actions and damage feedback.

### Verified

- Verified Godot 3.6.1 can load `BattleScene` and run a 30-second combat window without reported script errors after implementing Global Skill Queue and Skill Queue UI.
- Verified Godot 3.6.1 can load `BattleScene` and run a 30-second combat window without reported script errors after implementing Combat Readability Expansion v1 REVIEW prototype.
- Verified Godot 3.6.1 can load `BattleScene` and run a 30-second combat window without reported script errors after adding `Combat Readability Prototype v1 (LOCK)`.
- Verified Godot 3.6.1 can load `BattleScene` and run a 30-second combat window without reported script errors after applying `Combat Readability v1 (LOCK)`.
- Verified Godot 3.6.1 can load `BattleScene` and run a 30-second combat window without reported script errors after applying `Combat Tempo v2 (LOCK)`.
- Verified Godot 3.6.1 can load `BattleScene` and run a 30-second combat window without reported script errors after removing the battle speed button.
- Verified Godot 3.6.1 can load `BattleScene` and run a 30-second combat window without reported script errors after `COMBAT_READABILITY_PACING_PASS_V2`.
- Verified Godot 3.6.1 can load `BattleScene` and run a 30-second combat window without reported script errors after the v1.1 action-stagger tuning pass.

## 2026-05-27

### Changed

- Adopted finalized `Readable Combat Tempo v3` targets in the formal game version and combat tempo rules, replacing the v2 timing ranges and encounter-duration targets.
- Slowed normal attacks to a 3.8-second baseline with +/-0.4-second variation, yielding approximately 3.4 to 4.2 seconds between ordinary actions.
- Rebalanced action-cycle cooldown counts so active skills occur approximately every 15 to 22 seconds and Boss skills approximately every 22 to 35 seconds.
- Expanded the one-at-a-time major skill presentation window to a randomized 0.8 to 1.8 seconds and added a 0.15 to 0.35 second breathing pause after major actions.
- Replaced fixed fifth-encounter Boss appearances with route-local weighted encounters: normal travel battles, elites, and a cumulative-chance Boss encounter.
- Kept Boss durability, restrained 2.4-second entrance, and Boss-only enemy summons within randomly selected Boss encounters.
- Expanded ordinary route encounters to support 3 to 6 ground enemies, while reducing ordinary floating-number noise.
- Shortened the victory-to-next-encounter gap to 0.75 seconds with a subtle normal-wave entrance.
- Reworded visible combat progress and loot messages from linear Stage clears to continuing Journey encounters.
- Disabled airborne enemies throughout Chapter 1 routes, reserving their arrival for later chapters.
- Added a sixth enemy battlefield slot with the same compact standing-unit treatment as the existing enemies.
- Replaced the Boss entrance warning text with a restrained cool ambient light shift behind the encounter entrance.
- Added readable action desynchronization: each unit receives a 0.2 to 1.2 second opening offset and independent mildly varied normal-attack timing.
- Added short cast preparation and shared presentation spacing for major skills so important actions do not trigger together.
- Added brief hit-reaction locks, quieter staggered DOT flashes, and reduced ordinary attack movement distance.
- Fixed Battle/Loot log reading lock so scrolling down freezes visible history while incoming events remain buffered until the player returns to the top.
- Reduced ordinary normal-encounter floating damage to a sparse 20% display chance while retaining feedback for critical hits, skills, and elite/Boss encounter pressure.
- Removed target knockback and area-hit displacement animations; hit targets now retain their standing positions and use restrained flash feedback only.
- Formalized that the battle and status systems do not support Knockback or forced-displacement effects.

### Verified

- Verified Godot 3.6.1 can load `BattleScene` and run a 30-second combat window without reported script errors after the finalized v3 pacing update.

## 2026-05-23

### Added

- Added `scenes/ExpeditionRewardSummaryPanel.tscn` as a portrait travel-report scene shown after retreat.
- Added `scripts/expedition_reward_summary_panel.gd` with safe selected-route display, duration presentation, mocked reward results, and confirm/close return to the tavern.
- Added `docs/expedition_reward_summary_panel_v1.md`.
- Added `scenes/ExpeditionHUD.tscn` as a compact, collapsible expedition status and action overlay inside `BattleScene`.
- Added `scripts/expedition_hud.gd` with selected-route display, elapsed-time tracking, capacity placeholder display, placeholder Workshop/Inventory shortcuts, and retreat-to-tavern flow.
- Added `docs/expedition_hud_v1.md`.
- Added `scenes/ExpeditionRoutePanel.tscn` as the first tavern map-table expedition route overlay.
- Added `scripts/expedition_route_panel.gd` with fixed Chapter 1 route selection, single-route highlight state, preference placeholder UI, and start expedition flow.
- Added `docs/expedition_route_panel_v1.md`.
- Added `assets/fonts/NotoSansTC-VF.ttf` for readable Traditional Chinese expedition route UI.
- Added finalized-version reading order, source-of-truth priority, MVP scope, and required implementation reporting rules to `AGENTS.md`.
- Added `NEXT_STEPS.md` as the current development roadmap, explicitly subordinate to finalized-version documents.

### Changed

- Routed expedition retreat through `ExpeditionRewardSummaryPanel` before returning to `TavernMainScene`.
- The expedition HUD now passes the active-scene elapsed duration to the reward summary for display only.
- Instanced `ExpeditionHUD` into `BattleScene` without changing the existing battle composition or quick-status overlay behavior.
- Connected the TavernMainScene map table interaction to open the expedition route overlay while keeping the tavern visible beneath it.
- Set `TavernMainScene` as the project startup scene so the playable MVP loop begins at the tavern main base.
- Starting an expedition now passes only the selected route ID, restores portrait layout, and enters `BattleScene`.
- Updated `AGENTS.md` local development information so `TavernMainScene` is recorded as the current main scene.
- Referenced `NEXT_STEPS.md` in `AGENTS.md` as roadmap-only material rather than finalized system authority.

### Fixed

- Fixed missing Chinese glyphs in `ExpeditionRoutePanel` by applying a project-local Traditional Chinese font theme.

### Verified

- Verified Godot 3.6.1 startup for `TavernMainScene`, `ExpeditionRoutePanel`, and the project main scene after WorldMap / Expedition Route Select Pass v1.
- Verified Godot 3.6.1 project startup after updating `AGENTS.md` finalized-version workflow rules.

## 2026-05-22

### Added

- Added `AGENTS.md` with project rules, guardrails, document references, and completion workflow for future agent work.
- Added `scenes/TavernMainScene.tscn` as the first horizontal tavern main-base scene.
- Added `scripts/tavern_main_scene.gd` for tavern micro motion, world rumor rotation, and the expedition entry button placeholder.
- Added `docs/tavern_main_scene_v1.md` to record the tavern scene purpose, layout, and guardrails.
- Added split TavernMainScene v2 controllers: `tavern_background.gd`, `tavern_interaction_points.gd`, `tavern_event_board.gd`, `tavern_travel_gate.gd`, and `tavern_npc_controller.gd`.
- Added `BattleQuickMenu v1` as a compact portrait battle overlay for bag, equipment, field workshop, enhancement, and Buff/Debuff status access.
- Added `scripts/battle_quick_menu.gd`.
- Added `docs/battle_quick_menu_v1.md`.
- Added TavernMainScene Lighting Pass v1 with `TavernLightController`, `TavernParticleLayer`, and `TavernAmbientEffects`.
- Added low-frequency tavern light, smoke, dust, ale vapor, gate mist, wind strip, foreground shadow, and corner vignette layers.

### Changed

- Replaced `AGENTS.md` content with the formal civilization caravan world-expedition RPG project direction and guardrails.
- Reworked `TavernMainScene` into a layered tavern main-base layout with far, middle, foreground, ambient, and UI layers.
- Changed the expedition entry from a detached UI button into an in-scene expedition gate interaction.
- Expanded tavern micro motion with lantern glow, dust drift, route banner movement, and traveler idle motion.
- Updated `docs/tavern_main_scene_v1.md` to describe the v2 tavern base layout.
- Rebuilt `TavernMainScene` as a main-base world interaction scene with night village background, bar counter, rumor board, map table, travel gate, workshop, black market corner, bard corner, and tavern travelers.
- Converted tavern functions into low-interference scene interaction points instead of large menu buttons.
- Refactored `TavernMainScene` to v3 de-UI presentation: interaction hotspots are transparent, persistent function labels are hidden, and tooltips appear only on hover or click.
- Added tavern life fragments including barrels, mugs, map documents, oil lamp, compass, forge glow, tool bench, wall weapons, black market lamp, hooded merchant, rug, chairs, travel pack, ale haze, and foreground shadow details.
- Connected BattleQuickMenu status page to current battle Buff/Debuff data while keeping tavern and horizontal scene access forbidden from battle.
- Strengthened TavernMainScene v3 atmosphere with warm map-table focus lighting, bar counter candle warmth, dim green black-market light, cool travel-gate moonlight, and low warm rumor-board readability light.
- Updated BattleQuickMenu with Visual Pass v1: idle display is now a compact status summary strip, expanded categories use pixel icon placeholders, and status categories focus on Buff, Debuff, World, Aura, and Summon notes.

### Verified

- Verified Godot 3.6.1 startup after adding `AGENTS.md`.
- Verified Godot 3.6.1 startup with `TavernMainScene`.
- Verified Godot 3.6.1 startup after the TavernMainScene v2 refactor.
- Verified Godot 3.6.1 startup after splitting TavernMainScene v2 controllers.
- Verified Godot 3.6.1 startup after the TavernMainScene v3 de-UI refactor.
- Verified Godot 3.6.1 startup after adding BattleQuickMenu v1.
- Verified Godot 3.6.1 startup after TavernMainScene Lighting Pass v1.
- Verified Godot 3.6.1 startup after BattleQuickMenu Visual Pass v1.

## 2026-05-16

### Added

- Added formal battlefield layout v1 background depth layer.
- Added `assets/backgrounds/bg_battle_depth_overlay_720x854.png` for the battle field background stack.
- Added `battle_ui_current_layout_v2.md` as the current formal battle UI layout snapshot.
- Added `scripts/status_effect.gd` as the shared Buff/Debuff status effect data object.
- Added Buff/Debuff System Rules v1 to the current battle UI layout documentation.
- Added `battle_rules_v1.md` as the formal battle system rule document.
- Added `status_system_rules_v1.md` as the formal status system rule document.
- Added `combat_tempo_rules_v1.md` as the formal combat tempo rule document.
- Added stable rule entry documents: `battle_rules.md`, `status_system_rules.md`, and `combat_tempo_rules.md`.
- Added status icon duration countdown display beside unit bodies.
- Added compact status icon overflow display.
- Added Summon System v1 with independent player and enemy summon units.
- Added supported summon definitions for Wolf, Bear, Treant, Skeleton, Wraith, and Death Knight.
- Added Flying Enemy System v1.
- Added `docs/` rule documentation folder.
- Added `docs/ai_archetype_rules.md` and `docs/class_design_rules.md` draft rule documents.
- Moved `battle_rules_v1.md` and `battle_ui_current_layout_v2.md` into `docs/`.
- Added full combat tempo and status system rule documents under `docs/`.
- Replaced `docs/ai_archetype_rules.md` placeholder with AI Archetype Rules v1.
- Replaced `docs/class_design_rules.md` placeholder with Class Design Rules v1.

### Changed

- Enlarged player and enemy battlefield visuals by approximately 15%.
- Shortened and centered player/enemy HP bars so the battlefield reads cleaner.
- Reduced the bottom Log area height to return more space to the battlefield.
- Applied shared button styling to the Battle/Loot log tabs.
- Documented fixed Buff/Debuff icon placement rules for the formal battle layout.
- Migrated Poison, Burn, and Guard to shared status effect storage with refresh/remove/tick/icon support.
- Added foundation behavior hooks for Freeze, Sleep, Root, Wound, Healing Blessing, Purify, Resistance, and Erosion.
- Updated battle UI layout documentation to reference the formal status system rules instead of duplicating full status rules.
- Updated battle UI layout documentation to reference the formal combat tempo rules instead of duplicating full timing rules.
- Implemented Buff/Debuff System v1 as a playable tactical combat layer.
- Expanded `StatusEffect` with status type, priority, effect category, and icon update data.
- Connected Ranger status pressure through Root and Wound.
- Connected Cleric support through Purify, Healing Blessing, and Resistance.
- Connected Mage control pressure through Frostbite and low-chance Freeze.
- Connected enemy status pressure through Poison, Burn, Root, Erosion, and Wound.
- Status duration ticking now applies to both player and enemy units.
- DOT ticking now supports Poison, Burn, and Frostbite on both sides while keeping visuals subtle.
- Summons now have their own HP, attacks, status effects, and fixed medium-low aggro.
- Enemy target selection now uses aggro weights, with Guardian higher and summons medium-low.
- Boss targeting now avoids permanently focusing summons.
- Player and enemy summon slots now display active summon name, HP bar, and status icons.
- Summon attacks now use simplified visual feedback.
- Flying enemies now appear after early-stage maps and float above their ground slot.
- Flying enemies now show a compact flying indicator icon.
- Melee normal attacks now skip flying enemies.
- Ranged and magic attacks can target flying enemies.
- Updated documentation references to use the new `docs/` paths.

### Fixed

- Fixed Godot unused-argument warning in DOT status damage flash handling.
- Fixed Godot narrowing-conversion warning when refreshing legacy status effect durations.
- Fixed additional Godot narrowing-conversion warnings in shared status effect stack and duration helpers.
- Fixed Godot parser error caused by ambiguous `:=` type inference in battle status UI/combat helpers.
- Fixed Godot parser error at status icon overflow count calculation.
- Fixed Godot parser error at battle log display line duplication.
- Fixed summon hit/death effects crashing when a summon slot has no `Content/Sprite` child.
- Fixed Godot parser error from strict `CanvasItem` return typing in summon visual target fallback.
- Fixed Godot parser error from inferred `modulate` color type in summon visual flash fallback.

### Verified

- Verified Godot 3.6.1 can start the project with `BattleScene.tscn`.
- Added latest formal battlefield layout preview screenshot at `screenshots/battle_ui_v2.png`.
- Added Summon System v1 preview screenshot at `screenshots/battle_ui_summon_v1.png`.
- Verified Godot 3.6.1 startup after Buff/Debuff System v1 implementation.
- Verified Godot 3.6.1 startup after parser error fix.
- Verified Godot 3.6.1 startup after Summon System v1 implementation.
- Verified Godot 3.6.1 startup after Flying Enemy System v1 implementation.

## 2026-05-15

### Added

- Added first-pass battle UI PNG assets:
  - Battle panel frame
  - Battle log frame
  - Player and enemy HP bar textures
  - Action button states
  - Support, speed, buff, debuff, death, and loot icons
- Added temporary player, enemy, and battle background test assets for layout review.
- Added runtime UI asset binding in `scripts/battle_scene.gd`.
- Added player/enemy sprite display in battle slots.
- Added no-frame combat presentation so units appear to stand in the scene.
- Added side status icon display:
  - Player icons appear beside the left side of the unit body.
  - Enemy icons appear beside the right side of the unit body.
  - Status icons are display-only and do not accept clicks.
- Added battle feedback effects:
  - Floating damage numbers
  - Floating heal numbers
  - Critical damage emphasis
  - Attacker lunge
  - Target knockback
  - Area-hit left-right shake
  - Skill flash
  - Death fade
- Added distinct player skill roles:
  - Guardian: `Shield Bash`, single-target damage with short Guard status.
  - Ranger: `Piercing Shot`, high single-target damage.
  - Cleric: `Mend`, heals the lowest HP living ally.
  - Mage: `Arcane Burst`, area damage against all living enemies.
- Added enemy status behavior:
  - Minion can apply Poison.
  - Beast can apply Burn.
  - Boss can apply Poison and/or Burn in addition to Heavy Swing.
- Added status effects:
  - Poison: small damage over time.
  - Burn: stronger short damage over time.
  - Guard: temporary incoming damage reduction.
- Added separate Battle and Loot log views.
- Added Battle/Loot log tab controls near the support and speed controls.
- Added separate loot log storage for equipment drops.
- Added victory reward settlement guard to prevent duplicate loot generation.
- Added battle tempo rules to `battle_ui_current_layout.md`:
  - Combat rounds target approximately 2.5 seconds.
  - Same-tick actions should be staggered.
  - Small skill presentations should last about 0.3 to 0.6 seconds.
  - High-tier skill presentations should stay under 1 second.
- Added effect rules to `battle_ui_current_layout.md`:
  - Normal attacks use small effects.
  - Only high-tier skills should use full-screen effects.
  - DOT effects should not use large visual effects.
  - Buffs should prioritize icon-based presentation.
- Added damage text rules to `battle_ui_current_layout.md`:
  - DOT damage may skip floating damage text.
  - Critical damage uses enlarged text.
  - Small damage should avoid excessive floating text.
- Added UI rules to `battle_ui_current_layout.md`:
  - Buff icons must not cover character heads.
  - Battle Log and Loot Log are separated.
  - The middle of the battlefield should remain visually readable.
  - When 6 enemies are shown, character visuals should scale down by 10%.
- Added skill design rules to `battle_ui_current_layout.md`:
  - Same-series skills evolve progressively.
  - Class advancements should preserve the original playstyle.
  - Each skill family specializes in 1 to 2 core status types.
  - Avoid overloading one skill with too many Buffs or Debuffs.
  - High-tier skills prioritize scale and battlefield impact.
- Added visual priority rules to `battle_ui_current_layout.md`:
  - Highest: Boss skills, Legendary skills, Freeze, Death.
  - Medium: Active skills, Shields.
  - Low: DOT, small Buffs, small damage.
- Added Codex completion workflow:
  - Update `CHANGELOG.md`.
  - Update `DEVLOG.md`.
  - Verify Godot 3.6.1 startup.
  - List current known issues.
  - Attach the latest battle screenshot when available.
- Added prohibited-change rules:
  - Do not add new classes without explicit user approval.
  - Do not modify class advancement routes without explicit user approval.

### Changed

- Implemented first-pass battle visual priority behavior:
  - Buff and Debuff side icons now use smaller 16x16 indicators.
  - DOT damage no longer spawns floating damage text.
  - Critical damage text is enlarged for clearer priority.
  - Boss Heavy Swing now uses a higher-priority warning flash layer.
- Moved Support and battle speed controls to the lower-left battle area.
- Moved reserved party-wide status slots to the lower-right battle area.
- Moved Battle/Loot log tabs out of the battle log panel so they no longer cover log text.
- Changed equipment drop handling so loot is generated only after the battle has entered the Victory end state.
- Changed equipment drops to write to the Loot log instead of the Battle log.
- Kept battle summaries such as stage clear and gold gain in the Battle log.
- Updated battle log documentation to describe separate Battle and Loot views.
- Updated combat layout documentation in `battle_ui_current_layout.md`.

### Fixed

- Fixed unit Buff/Debuff icons overlapping character heads by mounting them on the unit slot parent layer.
- Fixed battle log tab overlap with battle log text.
- Fixed battle log tab placement conflict with the reserved party-wide status bar.
- Fixed ordinary attack animation direction:
  - Player attacks move upward.
  - Enemy attacks move downward.
  - Targets knock back away on the same vertical lane.
- Reduced the visual impression of group shaking by staggering actions within the same battle tick.

### Verified

- Verified battle scene startup with Godot 3.6.1 after each major UI and combat logic change.
- Verified battle tick startup path after combat feedback, skill, status, and log changes.
