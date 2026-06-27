# Devlog

## 2026-06-04

### Prototype Pass: Travel Loop v1

Implemented:

- Added a lightweight post-battle travel state machine in `battle_scene.gd`.
- Added Recovery & Gather, weighted 1-to-3 segment travel, travel-only healing, low-frequency micro events, shared Loot logging, subtle Travel Drift, and restrained dust foreshadow.
- Preserved living party HP across encounters so travel healing matters.
- Preserved party formation and fixed camera while hiding defeated enemies between encounters.

Known issues:

- Travel timing, healing amount, micro-event frequency, and encounter weighting require live-feel validation.
- Route materials are Loot-log prototype entries only; no material inventory mutation exists yet.
- Travel Drift uses the existing depth overlay as a restrained prototype cue.

Verification:

- Godot 3.6.1 headless `BattleScene.tscn` startup passed.
## 2026-06-03

### Development Pass: Story Log + Death Recap v1

Implemented:

- Added `Story` as the third battle-log view beside Battle and Loot.
- Added a quiet unread marker that appears when Story receives a new event and clears when Story is opened.
- Story records Boss arrival, Boss major skills, player-character deaths, and Boss defeat.
- Added Death Recap v1 with the latest three actual damage/healing records and sources.
- Excluded Buff, Debuff, Miss, block, and dodge events from Death Recap history.

Protected:

- Did not move SUP, change combat rules, damage values, Skill Queue, Loot rules, or Boss behavior.

Verification:

- Godot 3.6.1 headless `BattleScene.tscn` startup passed.
- Godot 3.6.1 headless `BattleScene.tscn --phase2-boss-readability-acceptance` startup passed.

### Prototype Polish: Queue Readability v1

Implemented:

- Added `queue_readability_v1.md` as the FINAL queue readability polish note.
- Extended the Skill Queue width by roughly 30% while keeping the queue centered in the battle area.
- Increased Skill Queue slot and portrait size for portrait readability.
- Raised the queue opacity slightly while keeping the presentation low-interference.
- Added timeline hierarchy: first slot 125%, second 100%, third 95%, later slots 90%.
- Added subtle first-slot brightness to clarify the next important action.
- Added micro slide + fade queue entry motion: player entries rise from below, enemy/Boss entries enter from above.
- Added soft queue exit fade/shrink and short reflow slide when entries advance.

Protected:

- Did not change combat tempo, skill cooldowns, target-line rules, damage values, monster HP, Boss behavior, summon rules, or the Combat Focus System.
- Did not add bounce, pulse, warning flash, cinematic queue effects, or new combat systems.

Verification:

- Godot 3.6.1 headless `BattleScene.tscn --phase2-4v6-acceptance` startup passed after Queue Readability v1.

Known issues:

- Portrait viewport observation is still needed to confirm the enlarged timeline reads clearly during live skill queue transitions.

## 2026-06-02

### Debug Fix: Missing QuickToggleButton Style Target

Fixed:

- Removed the obsolete `_apply_ui_assets()` styling reference to `BattleQuickMenu/QuickToggleButton`, which no longer exists in `BattleScene.tscn`.
- Added null guards to `_apply_button_style()` and `_apply_progress_style()` so removed or optional UI nodes cannot trigger a Nil method call during `_ready()`.

Verification:

- Godot 3.6.1 headless project startup passed.
- Godot 3.6.1 headless `BattleScene.tscn` startup passed.
- Godot 3.6.1 headless `BattleScene.tscn --phase2-4v6-acceptance` startup passed.

### Cleanup Pass: Combat Prototype Phase 2 Acceptance

Implemented:

- Cleaned README combat prototype descriptions so they no longer describe the removed speed button, fixed 5-enemy slots, fixed every-5 Boss cycle, or character-side skill cooldown UI.
- Updated `docs/battle_ui_current_layout_v2.md` to reflect current Phase 2 state: Skill Queue UI, fixed 1x playback, up to 6 enemies, weighted Boss encounters, and hidden character-side skill labels.
- Marked legacy layout and tempo documents as superseded historical references:
  - `battle_ui_current_layout.md`
  - `docs/combat_tempo_rules.md`
  - `combat_tempo_v2.md`
- Added `docs/combat_phase2_cleanup_notes.md`.
- Added CLI-only deterministic acceptance path: `--phase2-4v6-acceptance`.
- The acceptance path forces a normal 4 player vs 6 enemy setup, disables summons for that run, uses a fixed seed, and logs the acceptance setup.
- Marked Combo Exception Rule as DESIGN LOCKED / NOT IMPLEMENTED in cleanup notes.

Protected:

- Did not modify `combat_system_current.md`.
- Did not add combo, follow-up, double-strike, or other new combat systems.
- Did not tune combat tempo values, damage values, monster HP, skill cooldown targets, travel atmosphere, portrait layout, or low-fatigue combat direction.

Known issues:

- The deterministic 4v6 path is a local CLI acceptance path, not a formal gameplay route.
- Dedicated automated full-battle completion assertions are not implemented yet.

Verification:

- Godot 3.6.1 headless project startup passed after Phase 2 cleanup.
- Godot 3.6.1 headless `BattleScene.tscn` startup passed after Phase 2 cleanup.
- Godot 3.6.1 headless `BattleScene.tscn --phase2-4v6-acceptance` startup passed.

### Prototype Pass: Summon Reserve Readability v1

Implemented:

- Converted the four summon reserve slots from static placeholders into quiet stateful frames.
- Empty reserve slots now use high-transparency styling so they read as reserved capacity without competing with the battlefield.
- Living player summons now fill the leftmost reserve slot with a compact icon.
- The active summon battlefield slot now shows a compact summon icon above its HP bar.
- Reserve visuals refresh during normal battle UI updates and after summon death.
- Reused existing icon assets as temporary summon identifiers until dedicated summon art exists.

Protected:

- Did not change summon count rules, summon attacks, summon targeting, combat pacing, skill queue behavior, Boss focus, portrait layout, damage values, or travel atmosphere.

Known issues:

- Summon reserve icons reuse existing buff/debuff/state icons until dedicated summon icons are produced.
- The reserve bar still needs portrait viewport review to confirm it stays visually secondary beside the moved buff panel and lower controls.

Verification:

- Fixed the Godot 3 parser error at `battle_scene.gd:567`; validated loaded icon resources now return through explicit `as Texture` casting.
- Fixed the Godot 3 parser error at `battle_scene.gd:565`; loaded summon icon assets are now checked as `Texture` before returning.
- Fixed the Godot 3 parser error at `battle_scene.gd:550`; the ambiguous `:=` comparison is now an explicit `bool`.
- Godot 3.6.1 headless project startup passed after the summon reserve UI pass.
- Godot 3.6.1 headless `res://scenes/BattleScene.tscn` startup returned without reported parser or startup errors.

### Prototype Pass: Skill Queue Visibility + Source-Target Readability v1

Implemented:

- Added `COMBAT_SKILL_QUEUE_VISIBILITY_PASS_V1.md`.
- Added `combat_target_line_rule_v2.md` as a REVIEW-stage Target Line usage rule.
- Added `combat_normal_attack_rhythm_v2.md` as a REVIEW-stage normal attack rhythm rule.
- Added `combat_global_normal_attack_beat_v1.md` as a REVIEW-stage Global Normal Attack Beat rule.
- Added `boss_focus_weight_v1.md` as a FINAL Boss focus readability rule.
- Added `ready_at` timing to Global Skill Queue entries.
- Changed Skill Queue visibility so skills appear about one base rhythm tick before Ready, approximately 3.6 seconds in the current prototype.
- Kept skill casting gated by actual cooldown Ready state, so queue preview does not cast skills early.
- Sorted the visible queue by true ready time, then ready order.
- Moved Boss cooldown reset to the actual queued cast attempt so Boss skills can preview without changing their timing.
- Added a shared low-interference source-target cue split into attacker micro-highlight and optional Target Line.
- Applied Target Line only to ranged normal attacks, ranged/magic skills, AoE first-target cue, heals, and Boss specified-target skills.
- Removed Target Line from melee attacks and summon bites; these now read through motion, attacker micro-highlight, hit reaction, and HP change.
- Changed normal attack interval calculation to `Base Rhythm × SPD Modifier`, then clamped the result to a hard 1.0-second minimum.
- Retuned prototype normal attack base rhythms to reduce background visual noise while keeping expedition party combat flowing.
- Added a shared `global_normal_attack_beat_remaining` gate so ordinary player, enemy, and summon normal attacks cannot create independent sub-second attack nodes.
- Normal attack candidates now use weighted selection by speed instead of fixed side-order scanning, so agility increases the chance to receive the next global attack node without breaking the 1.0-second global beat.
- Global normal attack beat advances through the same slowed schedule delta as ordinary actions, aligning the beat with Skill Focus Slow.
- Added Skill Queue `focus_priority`; Boss skills use S Priority and sort ahead of other focus events.
- Added subtle Boss first-slot queue emphasis at 112% scale with mild brightness.
- Added Boss body micro-brightness while Boss skill is queued, limited to dangerous ready/queued moments.

Known issues:

- Target Line opacity and duration need portrait viewport review; the current values are intentionally conservative.
- AoE still uses one line toward the first reachable enemy to avoid clutter.
- Skill Queue preview currently maps the formal "about 4 seconds" rule to one base rhythm tick, approximately 3.6 seconds.
- Normal attack v2 rhythm needs portrait viewport feel review because headless validation cannot judge whether the battle now feels too quiet or still too busy.
- Global Normal Attack Beat v1 needs portrait viewport feel review; the prototype may need weight tuning if fast units feel underrepresented or heavy units feel too absent.
- Combo / double-strike exceptions are documented but not implemented because the current prototype has no combo attack package system.
- Boss first-slot scale and ready brightness need portrait viewport review to confirm they read as dangerous but not noisy.

Verification:

- Godot 3.6.1 headless project startup passed after Skill Queue Visibility, Target Line v2, Normal Attack Rhythm v2, Global Normal Attack Beat v1, and Boss Focus Weight v1 changes.
- Godot 3.6.1 headless `res://scenes/BattleScene.tscn` startup returned without reported parser or startup errors.

## 2026-05-30

### Documentation Pass: Combat Rhythm + Skill Queue UI v1 FINAL

Implemented:

- Added finalized `combat_rhythm_and_skill_queue_ui_v1.md`.
- Updated `GAME_CURRENT_VERSION.md` with Global Skill Queue, Skill Queue UI, skill-focus Slow State, agility/skill-CD separation, and character-side cooldown removal.
- Summon reserved slots are treated as UI reservation only in this pass; summon system count remains governed by existing summon rules until separately finalized.

### Prototype Pass: Global Skill Queue + Skill Queue UI v1

Implemented:

- Added `global_skill_queue` and ready-order tracking in `battle_scene.gd`.
- Player skills and Boss skills now enter the queue when cooldown becomes ready.
- Queued dead units are skipped before casting, preventing dead units from casting queued skills.
- Added skill-focus Slow State by advancing ordinary action timers at 50% speed while focus lock is active.
- Added class-specific normal attack rhythm for Guardian, Ranger, Mage, and Cleric; other units use speed-based fallback timing.
- Added runtime `SkillQueueBar` above the battle log with up to 6 unit portraits.
- Added subtle first-slot highlight for the next caster.
- Hid character-side skill cooldown labels and removed the previous skill-ready status icon.
- Added 4 transparent summon reserve UI slots as visual reservation only.
- Tuned micro stagger test timing to separate overlapping visible actions: normal actions 0.40 seconds, summons 0.30 seconds, major skill starts 0.45 seconds. Attack cooldowns, skill cooldowns, portrait layout, travel atmosphere, and low number readability are unchanged.

Known issues:

- Skill Queue UI placement needs visual review against Support/Buff panels in the actual portrait viewport.
- Summon reserve slots are UI-only and do not expand the active summon system.
- Class-specific normal-attack intervals are implemented for the current four-player prototype, but still need feel tuning on-device.

Verification:

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn`.
- Godot 3.6.1 ran a 30-second headless combat window without reported script errors.

### Documentation Draft: Combat Readability Expansion v1 REVIEW

Implemented:

- Added `combat_readability_expansion_v1_review.md` as a review-only prototype document.
- Captured the proposed 4-player versus 6-enemy readability validation, empty standoff space use, low-presence Target Line, Skill Reading Window, and Skill FX layering.
- Did not update `GAME_CURRENT_VERSION.md` because the document status is REVIEW, not FINAL.

### Prototype Pass: Combat Readability Expansion v1 REVIEW

Implemented:

- Added low-presence Target Line rendering in `battle_scene.gd` for ranged, magic, heal, and Boss focus events.
- Kept normal melee basic attacks without Target Line.
- Added Skill Reading Window sequencing: caster flash first, then Target Line, then delayed hit / heal feedback.
- Updated important-event lock timing to use Focus Window + Focus Gap while allowing background actions to continue through ordinary action staggering.
- Added Boss skill line support using a slightly thicker, still low-presence line paired with the existing Threat Marker.

Known issues:

- AoE currently shows one Target Line toward the first reachable enemy to avoid line clutter; this may need a center-area hint later.
- Exact line opacity, width, and duration need visual review on a portrait device.
- Screenshot was not updated because verification was run headless.

Verification:

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn`.
- Godot 3.6.1 ran a 30-second headless combat window without reported script errors.

### Documentation Pass: Combat Focus System v1 FINAL

Implemented:

- Added final `combat_focus_system_v1.md`.
- Updated `combat_focus_system_v1.md` to the reviewed FINAL timing version with Focus Window 1.8 to 3 seconds and Focus Gap 1.4 to 3 seconds.
- Formalized that Combat Focus System v1 overwrites focus-event timing from `combat_tempo_v2` and `combat_readability_v1`.
- Updated dense-combat tuning priority so Focus Gap is increased before `ACTION_STAGGER_INTERVAL`.
- Updated `GAME_CURRENT_VERSION.md` to authorize Semi Turn-Based Combat as the formal focus direction.
- Updated combat tempo and battle rules: background combat keeps flowing while important events enter Focus Queue and take focus one at a time.
- Replaced conflicting anti-focus-timing wording with anti-traditional-full-stop-turn-based restrictions.
- Preserved Real-Time Timeline Combat, damage values, monster stats, skill balance, encounter design, and class design.

### Documentation Pass: Combat Readability Prototype v1 LOCK

Implemented:

- Added locked `combat_readability_prototype_v1.md`.
- Defined the dense readability validation scenario as 4 player units versus 6 enemies.
- Recorded the adjustment priority: tune `ACTION_STAGGER_INTERVAL` toward 0.40 to 0.45 seconds before making other readability changes.
- Preserved encounter structure, combat design, monster design, skill balance, and current pacing philosophy.

### Verification Notes

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn` and ran a 30-second combat window without reported script errors after adding `Combat Readability Prototype v1 (LOCK)`.

### Documentation / Tuning Pass: Combat Readability v1 LOCK

Implemented:

- Added locked `combat_readability_v1.md`.
- Updated formal rules with readability-first target, hit, damage number, status, and skill FX guidance.
- Shortened ordinary and area hit confirmation flashes to 0.08 seconds.
- Removed outdated battle UI documentation that described target knockback.
- Preserved monster balance, combat pacing philosophy, combat rules, damage values, and class design.

### Verification Notes

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn` and ran a 30-second combat window without reported script errors after applying `Combat Readability v1 (LOCK)`.

### Documentation / Tuning Pass: Combat Tempo v2 LOCK

Implemented:

- Added locked `combat_tempo_v2.md`.
- Updated formal combat tempo direction to micro-staggered real-time combat.
- Superseded the previous 0.30 to 0.60 second readable action spacing and 0.50 to 1.20 second Boss focus windows for important events with `Combat Focus System v1 (FINAL)`.
- Marked reviewed FINAL focus timing as Focus Window 1.8 to 3 seconds and Focus Gap 1.4 to 3 seconds.
- Preserved damage values, monster stats, skill balance, encounter design, and class design.

### Verification Notes

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn` and ran a 30-second combat window without reported script errors after applying `Combat Tempo v2 (LOCK)`.

### Development Pass: Remove Battle Speed Button

Implemented:

- Removed the battle speed button node and signal connection from `BattleScene`.
- Removed speed-toggle state from `battle_scene.gd`.
- Fixed battle timer playback to 1x.
- Removed `x1 x2` from the battle top-bar status text.

### Verification Notes

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn` and ran a 30-second combat window without reported script errors after removing the battle speed button.

### Development Pass: Combat Readability Pacing Pass v2

Implemented:

- Added `COMBAT_READABILITY_PACING_PASS_V2.md`.
- Changed normal attack timing from a 3.8-second baseline to a 3.6-second baseline with +/-0.4-second variation.
- Superseded the previous 2.2-second minimum and 2.5 to 3.5-second major-event window with `Combat Focus System v1 (FINAL)`.
- Retuned player active skill cooldown ticks to target approximately 16 to 24 seconds.
- Retuned Boss skill timing to target approximately 24 to 36 seconds.
- Added a 0.08-second normal hit reaction delay for clearer cause and effect.
- Preserved damage values, monster HP, skill multipliers, drops, monster data, chapter rules, and class design.

### Verification Notes

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn` and ran a 30-second combat window without reported script errors after `COMBAT_READABILITY_PACING_PASS_V2`.

### Documentation Pass: Combat Readability Philosophy v1

Implemented:

- Added the locked combat readability philosophy document from the provided text.
- Updated `GAME_CURRENT_VERSION.md` so combat readability is treated as an information-density problem, not simply a speed problem.
- Updated combat tempo rules with `SEE -> UNDERSTAND -> PROCESS`, major event priority, and background-event downgrading rules.
- Preserved existing v3 timing, action-stagger tuning, cooldowns, damage values, and encounter-duration targets.

### Development Pass: Combat Readability Timeline Pass v1.1

Implemented:

- Tuned the ordinary ready-action stagger interval to 0.35 seconds after prototype observation.
- Applied the same 0.35-second spacing to summon ready actions.
- Preserved the existing normal attack cooldown, skill cooldowns, Boss timing, and encounter-duration targets.
- Kept major skills on their longer action-focus window so important actions remain readable.

### Verification Notes

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn` and ran a 30-second combat window without reported script errors after the v1.1 action-stagger tuning pass.

### Development Pass: Combat Readability Timeline Pass v1

Implemented:

- Added a micro stagger action timeline on top of the existing v3 combat tempo.
- Added action-focus windows for ordinary attacks, summons, and major skills to reduce same-frame visual overlap.
- Delayed single-target skill hit feedback slightly after the attacker motion.
- Increased area-skill target hit staggering so damage feedback does not appear all at once.
- Preserved real-time auto combat, existing v3 timing, no-knockback behavior, and low floating-number density.

### Current Known Issues

- Visual readability still needs an in-window screenshot or recording check because headless validation cannot confirm perceived overlap.
- The exact action-focus values may need tuning after testing 4-player versus 6-enemy encounters.

### Verification Notes

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn` and ran a 30-second combat window without reported script errors after the combat readability timeline pass.

## 2026-05-27

### Development Pass: Readable Combat Tempo v3

Implemented:

- Adopted `Readable Combat Tempo v3` as the finalized replacement for the v2 combat tempo and encounter-duration ranges.
- Set normal attacks to a 3.8-second baseline with +/-0.4-second variation, producing approximately 3.4 to 4.2-second individual attack intervals.
- Recalibrated cooldown cycle counts and prioritized ready skill scheduling so party skills remain approximately 15 to 22 seconds and Boss skills remain approximately 22 to 35 seconds.
- Removed the fixed every-fifth-encounter Boss cycle.
- Added weighted route encounters: ordinary travel battles, elite encounters, and Boss encounters whose chance increases while travelling and resets after a Boss appears.
- Added low-interruption encounter entrances: a short natural normal-wave fade and a restrained 2.4-second Boss arrival pause.
- Changed seamless progression to a 0.75-second transition between cleared encounters.
- Kept ordinary hit feedback visually quiet while preserving floating feedback for skills, Boss actions, healing, and critical hits.
- Disabled airborne enemy generation on all currently playable Chapter 1 routes.
- Expanded enemy standing slots to six and allowed ordinary route encounters to occupy 3 to 6 ground positions.
- Removed Boss entrance warning text and replaced it with a short cool ambient light shift.
- Changed active combat from whole-side action execution to independent unit readiness scheduling.
- Added randomized entry offsets, lightly varied attack intervals, short skill cast delays, and a single-major-skill presentation window randomized between 0.8 and 1.8 seconds.
- Replaced the earlier 0.15 to 0.35 second global breathing pause with the reviewed FINAL Focus Gap direction: 1.4 to 3 seconds.
- Added brief post-hit action locks and staggered low-key DOT flashes while keeping DOT free of floating number spam.
- Reduced normal attack motion so skill actions retain clearer visual emphasis.
- Repaired the Battle/Loot log inspection mode with an explicit reading lock: visible text no longer refreshes while the player is scrolled down, and buffered events appear when returning to the top.
- Set ordinary normal-encounter attacks to show floating numbers only about 20% of the time while preserving visual feedback for critical hits, skill damage, elites, and Bosses.
- Removed the legacy target knockback and area-hit shake animations, because they read as unsupported forced displacement.
- Locked the formal rules so Knockback cannot be introduced as a status or battle-control effect.

### Current Known Issues

- Elite encounters are now identifiable in the random flow, but receive no invented stat profile until finalized encounter data is supplied.
- Presentation mode controls (Full, Simplified, Minimal) are formally recorded but do not yet have a settings UI.
- Duration targets require balancing passes using playable route encounter data beyond the current MVP enemy pool.
- Six-enemy portrait spacing and the random Boss ambient entrance need a fresh in-window visual confirmation screenshot.
- Chapter 2 route data is not implemented yet, so airborne generation remains reserved rather than reachable in play.
- Action-offset values will need an in-window pacing pass during longer normal and Boss encounters.
- Battle log scroll-lock behavior should be visually confirmed by scrolling into older events while active combat continues.
- Hit flash readability should be visually confirmed now that targets no longer move when struck.
- Normal, Elite, and Boss encounter durations should be timed against the v3 targets of 45 to 80, 70 to 110, and 120 to 240 seconds.

### Verification Notes

- Godot 3.6.1 loaded `res://scenes/BattleScene.tscn` and ran a 30-second combat window without reported script errors after the finalized v3 pacing update.

## 2026-05-23

### Development Pass: Expedition Reward Summary Pass v1

Implemented:

- Added a portrait expedition travel-report scene between retreat and the tavern return.
- Updated the expedition HUD retreat action to open the report instead of returning immediately.
- Carried the selected route ID forward and displayed its readable Chapter 1 route name, with `未知路線` fallback.
- Passed the active battle-visit duration into the report for display.
- Added mocked gold, EXP, materials, defeated enemies, elite encounter, Boss encounter, and capacity-result presentation.
- Added one clear confirmation action plus close/Escape return behavior.
- Returned to `TavernMainScene` in landscape mode only after confirming or closing the report.

### Current Known Issues

- Reward, encounter, and capacity report values are mocked presentation only.
- Duration currently measures the active battle scene visit only.
- No real economy or reward settlement is applied from the report.

### Development Pass: Expedition HUD Pass v1

Implemented:

- Added a compact collapsible expedition strip to `BattleScene`.
- Displayed the selected route ID as a readable route name during battle.
- Added active-scene expedition elapsed time display.
- Added the initial capacity placeholder display, `Bag 0 / 120`.
- Added small Workshop and Inventory placeholder actions in the expanded panel.
- Added player-controlled retreat entry, now routed through the expedition reward summary before returning to `TavernMainScene`.
- Kept the battle layout and auto-combat behavior intact while the HUD is open.

### Current Known Issues

- Capacity consumption is not connected to loot data.
- Expedition elapsed time does not persist across scene changes.
- Workshop and Inventory buttons remain placeholder feedback only.
- Selected routes do not yet influence battle encounters or rewards.

### Development Pass: WorldMap / Expedition Route Select Pass v1

Implemented:

- Added a low-interference `ExpeditionRoutePanel` modal overlay opened from the tavern map table.
- Added the fixed Chapter 1 Kingdom Border route set: Grassland Trade Road, Border Camp, and Swamp.
- Added single route selection with restrained warm highlight state.
- Added expedition preference placeholder controls with High Value Exploration as the default mode.
- Added start expedition validation and transition into portrait `BattleScene`.
- Passed only the selected route ID into the battle transition; expedition preference remains placeholder UI state.
- Changed the project start scene to `TavernMainScene`, establishing the first playable tavern-to-expedition loop.
- Added and applied `NotoSansTC-VF.ttf` so Traditional Chinese route text renders in the expedition overlay.
- Updated `AGENTS.md` so future implementation reads `GAME_CURRENT_VERSION.md` first, then the latest weekly summary, and follows finalized systems only.
- Recorded the required post-implementation report format and current tavern main-scene entry point in `AGENTS.md`.
- Added `NEXT_STEPS.md` as the current roadmap and classified it as planning material subordinate to finalized-version files.

### Current Known Issues

- Route selection does not yet modify enemy encounters, reward pools, or visual battle background.
- Expedition preference remains display/selection state only until the expedition rules system is built.
- Route panel uses styled placeholder UI pending final pixel-art panel assets.

### Verification Notes

- Godot 3.6.1 startup verification passed for `res://scenes/TavernMainScene.tscn`.
- Godot 3.6.1 startup verification passed for `res://scenes/ExpeditionRoutePanel.tscn`.
- Godot 3.6.1 startup verification passed using the updated project main scene.
- Godot 3.6.1 startup verification passed after updating `AGENTS.md` finalized-version workflow rules.

### Latest Screenshot

- `screenshots/expedition_route_panel_v1.png`

## 2026-05-22

### Development Pass: Agent Project Instructions

Implemented:

- Added `AGENTS.md` for future agent guidance.
- Recorded Godot version, main scene, main controller, core docs, guardrails, and completion workflow.
- Included warnings about Godot 3.6.1 GDScript type inference.
- Replaced `AGENTS.md` with the formal civilization caravan world-expedition RPG direction, including tavern base, expedition loop, combat restrictions, event direction, economy limits, and visual/UI guardrails.

### Development Pass: Tavern Main Scene v1

Implemented:

- Added `TavernMainScene` as a horizontal tavern main-base scene.
- Added subtle tavern micro motion for candle glow, drifting dust, and traveler idle movement.
- Added traveler display placeholders without free movement controls.
- Added a lower-left world rumor panel with rotating rumor text.
- Added an expedition entry button placeholder that updates tavern status text.
- Added `docs/tavern_main_scene_v1.md` as the current tavern scene note.

### Development Pass: Tavern Main Scene v2

Implemented:

- Rebuilt `TavernMainScene` as a layered tavern base with far, middle, foreground, ambient, and UI layers.
- Added visual world-travel cues through window views, route banners, a world route board, supplies, and an expedition gate.
- Changed the expedition entry into an in-scene gate interaction instead of a detached button.
- Added subtle route banner movement while keeping the scene calm and low-interference.
- Preserved no-free-movement rules; the tavern remains a viewing and preparation base.
- Updated the tavern layout note to v2.
- Split the tavern implementation into `TavernBackground`, `TavernInteractionPoints`, `TavernEventBoard`, `TavernTravelGate`, and `TavernNPCController`.
- Rebuilt tavern functions as scene hotspots for bar management, rumor board, map table, travel gate, workshop, and black market.
- Added night-version placeholders for village background, moonlight, weak street lights, tavern street view, candle glow, light dust, and foreground shadow.
- Added small traveler and bard placeholder performances without free movement.
- Kept all major interactions low-interference and scene-based.

### Development Pass: Tavern Main Scene v3 De-UI

Implemented:

- Removed persistent function labels from tavern interaction points.
- Hid interaction hotspot visuals so the player clicks scene objects instead of visible UI boxes.
- Added hover/click tooltip behavior through `TavernInteractionPoints`.
- Hid top title/status labels so the tavern reads as a space instead of a homepage UI.
- Added more tavern life fragments: barrels, mugs, rug, chairs, travel pack, wall weapons, forge glow, tool bench, black market lamp, hooded merchant, map documents, compass, oil lamp, ale haze, and foreground shadow.
- Kept the world rumor board as a small parchment-style rotating event surface.
- Preserved observation mode and no-free-movement rules.

### Development Pass: BattleQuickMenu v1

Implemented:

- Added `BattleQuickMenu` to the portrait battle scene as a compact overlay.
- Added quick entries for Bag, Equipment, Field Workshop, Enhance, and Buff/Debuff Status.
- Kept the overlay in portrait orientation and did not connect any tavern, recruitment, tavern event, market, black market, or horizontal scene entry.
- Added one-tap close behavior through a compact close button.
- Kept battle timers and background motion untouched while the overlay is open.
- Connected the Buff/Debuff status page to current player, summon, enemy, and enemy summon status data.
- Added `docs/battle_quick_menu_v1.md`.

### Development Pass: TavernMainScene Lighting Pass v1

Implemented:

- Added `TavernLightController` for low-frequency light breathing.
- Added `TavernParticleLayer` for slow dust, smoke, and ale vapor.
- Added `TavernAmbientEffects` for travel-gate mist, subtle wind strip, foreground shadow, and corner vignette darkening.
- Made the map table the warm primary focus.
- Added secondary warm light around the bar counter and rumor board.
- Kept the black market corner darker with weak green light.
- Added cool moonlight and mist around the travel gate to imply the outside world.
- Preserved de-UI rules; lighting guides attention without adding functional UI.

### Development Pass: BattleQuickMenu Visual Pass v1

Implemented:

- Replaced the lone `Q` button presentation with a compact status summary strip.
- Added summary counts for Buff, Debuff, World, Aura, and Summon.
- Replaced abstract `B / E / W / + / S` category letters with pixel color-block icon placeholders.
- Adjusted BattleQuickMenu content toward tactical status notes instead of a debug-like utility list.
- Kept the overlay portrait-only and compact.
- Did not add tavern, recruitment, tavern event, horizontal scene, market, or full black market access.

### Current Known Issues

- Dedicated art is still needed for several placeholder systems, including summons, flying indicators, and some status icons.
- Tavern scene currently uses placeholder UI shapes; final pixel tavern art, traveler sprites, expedition gate art, and route-selection flow are still needed.
- Tavern v3 de-UI presentation still uses placeholder pixel blocks; final object sprites and Chinese tooltip/font pass are still needed.
- BattleQuickMenu v1 uses compact placeholder letter buttons; final quick-menu icon art and simplified item/equipment/workshop data flows are still needed.
- Lighting Pass v1 uses ColorRect placeholder light shapes; final pixel-art lighting masks and object sprites are still needed.
- BattleQuickMenu Visual Pass v1 still needs final icon sprites for Buff, Debuff, World, Aura, and Summon.

### Verification Notes

- Godot 3.6.1 startup verification passed after adding `AGENTS.md`.
- Godot 3.6.1 startup verification passed for `res://scenes/TavernMainScene.tscn`.
- Godot 3.6.1 startup verification passed after the TavernMainScene v2 refactor.
- Godot 3.6.1 startup verification passed after splitting TavernMainScene v2 controllers.
- Godot 3.6.1 startup verification passed after the TavernMainScene v3 de-UI refactor.
- Godot 3.6.1 startup verification passed after adding BattleQuickMenu v1.
- Godot 3.6.1 startup verification passed after TavernMainScene Lighting Pass v1.
- Godot 3.6.1 startup verification passed after BattleQuickMenu Visual Pass v1.

### Latest Battle Screenshot

- `screenshots/battle_ui_flying_v1.png`
- `screenshots/battle_quick_menu_v1.png`
- `screenshots/battle_quick_menu_visual_pass_v1.png`

### Latest Tavern Screenshot

- `screenshots/tavern_lighting_pass_v1.png`

## 2026-05-16

### Development Pass: Formal Battlefield Layout v1

Implemented:

- Player and enemy battlefield visuals enlarged by approximately 15%.
- HP bars shortened and centered under each unit.
- Battle field gained a background depth overlay layer.
- Bottom Log area reduced so more screen height belongs to the battle field.
- Battle/Loot tabs now use the shared button style.
- `battle_ui_current_layout_v2.md` created as the current layout reference.
- Fixed the DOT status damage flash warning by marking the retained damage argument as intentionally unused.
- Fixed a Godot narrowing-conversion warning in legacy status duration refresh handling.
- Fixed additional narrowing-conversion warnings in shared status effect stack and duration helpers.
- Fixed a Godot parser error caused by ambiguous `:=` type inference in status UI/combat helper variables.
- Fixed a Godot parser error at the status icon overflow count calculation.
- Fixed a Godot parser error at battle log display line duplication.
- Fixed summon hit/death effects by falling back to the summon panel when no `Content/Sprite` child exists.
- Fixed a Godot parser error from strict `CanvasItem` return typing in summon visual target fallback.
- Fixed a Godot parser error from inferred `modulate` color type in summon visual flash fallback.
- Added Buff/Debuff System Rules v1 to the battle layout documentation.
- Added `scripts/status_effect.gd` for shared status effect data.
- Migrated Poison, Burn, and Guard to shared status effect storage.
- Added foundation helpers for Freeze, Sleep, Root, Wound, Healing Blessing, Purify, Resistance, and Erosion.
- Added `battle_rules_v1.md` for the formal battle system rules.
- Added `status_system_rules_v1.md` for the formal status system rules.
- Added `combat_tempo_rules_v1.md` for the formal combat tempo rules.
- Added stable rule entry documents for `battle_rules.md`, `status_system_rules.md`, and `combat_tempo_rules.md`.
- Implemented Buff/Debuff System v1 as the first playable tactical combat layer.
- Added duration countdown display to unit-side status icons.
- Added compact status icon overflow display.
- Implemented Summon System v1 with independent player and enemy battlefield units.
- Added supported summon definitions: Wolf, Bear, Treant, Skeleton, Wraith, and Death Knight.
- Implemented Flying Enemy System v1.
- Organized core rule documents under `docs/`.
- Added draft `docs/ai_archetype_rules.md` and `docs/class_design_rules.md`.
- Replaced `docs/ai_archetype_rules.md` placeholder with AI Archetype Rules v1.
- Replaced `docs/class_design_rules.md` placeholder with Class Design Rules v1.

Development summary:

- The battle screen now has a more formal first-pass battlefield composition.
- Units have stronger presence while HP information stays compact.
- The Log area remains usable but no longer dominates the lower screen.
- Buff/Debuff icon placement remains fixed beside unit slots and should avoid covering character heads.
- Buff/Debuff behavior now has a common structure before future skill-specific effects are added.
- Battle rules are now separated from UI layout notes so future combat work has a clear source document.
- Status system rules are now separated from UI layout notes so future skill, enemy, and equipment work can reference one source.
- Combat tempo rules are now separated from UI layout notes so future animation, skill effect, summon, and Boss work can reference one source.
- Player and enemy units now share one status ticking path.
- Poison, Burn, and Frostbite DOTs now work on both sides with subtle flash feedback and no floating DOT numbers.
- Freeze, Sleep, and Root now affect action availability.
- Resistance and Erosion now interact during Debuff application checks.
- Healing Blessing and Wound now modify healing received.
- Cleric Mend now purifies Debuffs from its target before applying support statuses.
- Summons now participate in combat with their own HP, attacks, status effects, and medium-low fixed aggro.
- Summons disappear on death only and do not use timer expiration.
- Enemy target selection now includes weighted aggro so Guardian attracts more attention while summons stay medium-low.
- Boss targeting avoids permanently focusing summons.
- Flying enemies now appear after early-stage maps, float above their battlefield slots, and show a compact flying indicator icon.
- Melee normal attacks now skip flying enemies; ranged and magic attacks can hit them.
- Documentation now has a central `/docs` folder for battle rules, status rules, combat tempo, UI layout, AI archetypes, and class design.
- AI archetypes now define weighted behavior guidance for guardian, assassin, ranger, mage, priest, support, debuffer, summoner, and boss roles.
- Class design rules now define progressive advancement, status identity, hidden class locks, and class development guardrails.

### Current Known Issues

- Direct Godot CLI screenshot automation still needs confirmation in this Codex environment.
- Buff/Debuff side icon offsets may need final pixel tuning after reviewing the newest screenshot.
- Battle/Loot tab position should be checked once more in the running Godot window.
- Background depth layer is a first-pass placeholder and may be replaced by final art later.
- Status icon art currently reuses existing buff/debuff icons until dedicated icons are produced.
- Boss control resistance is represented through status chance tuning only; a fuller immunity table is still future work.
- Summon visuals are still panel-based placeholders; dedicated summon sprites are future art work.
- Player-side summon selection is currently fixed to Wolf for v1 testing.
- Flying indicator currently reuses the speed-up icon until dedicated airborne icon art is produced.

### Verification Notes

- Godot 3.6.1 startup verification passed with `BattleScene.tscn`.
- A current layout preview screenshot was generated from the project PNG assets and layout coordinates.
- Godot 3.6.1 startup verification passed after Buff/Debuff System v1 implementation.
- Godot 3.6.1 startup verification passed after fixing the parser error that prevented the test screen from displaying.
- Godot 3.6.1 startup verification passed after Summon System v1 implementation.
- Godot 3.6.1 startup verification passed after summon visual target fallback fix.
- Godot 3.6.1 startup verification passed after loosening summon visual target return typing.
- Godot 3.6.1 startup verification passed after explicit `modulate` color typing.
- Godot 3.6.1 startup verification passed after Flying Enemy System v1 implementation.
- Godot 3.6.1 startup verification passed after AI Archetype Rules v1 documentation update.
- Godot 3.6.1 startup verification passed after Class Design Rules v1 documentation update.

### Latest Battle Screenshot

- `screenshots/battle_ui_flying_v1.png`

## 2026-05-15

### Development Pass: Battle Visual Priority System

Implemented:

- Buff and Debuff side icons reduced to 16x16.
- DOT damage no longer creates floating damage text.
- Critical damage text scale increased for higher readability.
- Boss Heavy Swing now triggers a higher-priority warning flash layer.

### Development Guardrails

- Do not add new classes unless the user explicitly approves it.
- Do not modify class advancement routes unless the user explicitly approves it.

Development summary:

- Low-priority effects now stay quieter.
- Boss skills now have a clearer visual layer than ordinary enemy attacks.
- Damage text priority now better matches the written visual priority rules.

### Codex Completion Workflow

After each development pass:

1. Update `CHANGELOG.md`.
2. Update `DEVLOG.md`.
3. Verify Godot 3.6.1 can start the project.
4. List current known issues.
5. Attach the latest battle screenshot when available.

### Current Known Issues

- Latest battle screenshot capture is not automated yet in this Codex environment.
- Battle/Loot tab placement still needs final visual confirmation inside the Godot editor/game window.
- Buff/Debuff icon offsets may still require pixel-level tuning after checking a fresh screenshot.
- Boss Heavy Swing warning flash needs visual confirmation in the running Godot window.

### Verification Notes

- Godot 3.6.1 startup verification passed after this documentation update.
- Godot 3.6.1 BattleScene startup and 8-second battle tick verification passed after the battle visual priority implementation.
- Godot 3.6.1 startup verification passed after adding prohibited-change guardrails.

### Latest Battle Screenshot

- Pending: attach after the next visual check from the Godot window.
