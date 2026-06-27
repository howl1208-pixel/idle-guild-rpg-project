# CURRENT_PROJECT_STATE

Status: CURRENT PROJECT STATE
Purpose: Recovery handoff for Codex after context loss
Priority Rules Source: "combat_system_current.md"

---

## 1. Project Direction (LOCKED)

This project is:

«a low-fatigue, readability-first, portrait idle RPG with travel atmosphere»

Core direction:

- Portrait mobile RPG
- Tavern-first home scene (Hub Tavern)
- Idle / travel feeling
- Semi Turn-Based Combat on a Real-Time Timeline
- Readability First
- Long-term comfortable watching
- Low-number combat

Forbidden direction:

- MMO-style visual spam
- synchronized combat explosions
- giant damage inflation
- full-screen chaotic FX
- traditional full turn-based combat
- front-row/back-row formation
- cinematic hard pauses

Combat should feel:

«alive, understandable, readable, comfortable»

---

## 2. Combat Rules Priority (VERY IMPORTANT)

Single source of truth:

combat_system_current.md

Priority order:

combat_system_current.md
↓
GAME_CURRENT_VERSION.md
↓
DEVLOG / CHANGELOG / WORK_LOG
↓
SUPERSEDED / ARCHIVE documents

SUPERSEDED documents are:

«historical reference only»

Never restore older conflicting combat rules.

Do NOT treat:

combat_tempo_v2
combat_tempo_rules.md
old battle layout docs

as formal current truth.

---

## 3. Formal Combat Direction (LOCKED)

Formal direction:

«Semi Turn-Based Combat
running on a Real-Time Timeline»

Meaning:

Background combat keeps flowing:

- normal attacks
- enemy bites/slashes
- DOT ticks
- small events

Important events become readable one at a time:

- Boss Skill
- Elite Skill
- Player Skill
- Important Heal

Combat philosophy:

Background Combat Continues
→ Focus Event
→ Background Combat Continues

NOT:

everyone explodes together

NOT:

traditional stop-and-wait turn combat

---

## 4. Combat Focus System v1 FINAL (LOCKED)

Combat uses two layers.

Background Layer

Purpose:

«maintain world flow»

Contains:

- normal attacks
- small enemy actions
- DOT
- minor Buff/Debuff ticks

Rules:

- low FX
- low visual priority
- low fatigue
- quieter presentation

Normal attacks are:

«background rhythm»

NOT:

«combat stars»

---

Focus Layer

Purpose:

«readable important combat events»

Priority:

Boss Skill
> Elite Skill
> Player Skill
> Important Heal
> Background Event

Formal rule:

«one important event should be understood at a time»

Goal:

Player should:

see
→ understand
→ process

instead of:

visual overload

---

## 5. Combat Tempo (LOCKED)

Combat playback:

fixed x1

Removed:

- speed button
- x2
- x4

Normal attack rhythm:

Base Rhythm × SPD Modifier

Hard minimum:

1.0 second

Purpose:

Prevent:

machine-gun attacks

Normal attacks are background rhythm.

NOT:

«primary combat focus»

---

## 6. Skill Queue (IMPLEMENTED)

Current state:

«implemented prototype»

Behavior:

- enters queue roughly one base rhythm before ready
- approximately 3.6 seconds early visibility
- does NOT cast early
- still sorted by true ready time
- removed if actor dies before cast

Queue order:

true ready_at
→ real ready order

Boss:

S Priority

UI:

- maximum 6 slots
- center battlefield position
- approximately 50% opacity
- enlarged for readability

Purpose:

«readability and anticipation»

NOT:

«manual control UI»

---

## 7. Readability Philosophy (LOCKED)

Formal philosophy:

«Readability First»

NOT:

«Slow First»

Goal:

Combat should become:

A attacks
→ player understands
→ B attacks

instead of:

everything happens simultaneously

Combat is NOT intended to become slow turn-based combat.

---

## 8. Target Line Rule v2 (IMPLEMENTED)

Target lines remain for:

- ranged normal attacks
- ranged / magic skills
- healing
- boss targeted skills

Removed from:

- melee normal attacks
- melee skills
- summon bite attacks

Melee readability uses:

small forward movement
+ attacker emphasis
+ hit reaction
+ HP change

Purpose:

«avoid battlefield line clutter»

---

## 9. Boss Readability (PROTOTYPE)

Current direction:

«dangerous but readable»

Implemented prototype:

- Boss queue priority
- Boss queue first-slot emphasis
- subtle boss brightness
- boss readiness emphasis

Allowed:

«subtle focus emergence»

Forbidden:

- giant warning FX
- raid-warning UI
- camera spam
- cinematic interruption
- permanent spotlight

Boss should feel:

«threatening and understandable»

NOT:

«loud»

---

## 10. UI Current State

Removed:

- speed button
- character-side cooldown UI
- old placeholder skill icons
- temporary BuffPanel placeholder

Implemented:

- centered SkillQueueBar
- Battle/Loot tab cleanup
- player formation lowered for readability
- cleaner combat center

SummonReserveSlots are now:

«future player battlefield support buttons»

NOT:

«summon reserve UI»

---

## 11. Tavern / Town Breathing (LOCKED)

Main home scene:

«Tavern (Hub Tavern)»

NOT:

«town screen»

Blacksmith:

«visible inside tavern scene»

Town Breathing philosophy:

low-frequency life feeling

Examples:

- blacksmith hammering
- occasional drinking
- mug sounds
- distant chatting
- small tavern incidents
- minor exchange events

Goal:

«living world without fatigue»

---

## 12. Audio Philosophy (LOCKED)

Direction:

«layered low-fatigue audio»

Priority system:

A-level:

- blacksmith hammer

B-level:

- mug sound
- distant chatting
- laughter

C-level:

- charcoal crackle
- wind
- ambient fire

Avoid:

«noisy tavern spam»

Music:

«optional / ambient-first»

---

## 13. Current Development Phase

Current phase:

«Combat Prototype Phase 2 Acceptance»

Already completed:

- Global Skill Queue
- Skill Focus Slow
- Global Normal Attack Beat
- Skill Queue visibility
- Target Line Rule v2
- Boss readability prototype
- deterministic 4v6 acceptance path

Current focus is:

«combat readability validation»

NOT:

«large feature expansion»

---

## 14. Deterministic Acceptance Mode

CLI flag:

--phase2-4v6-acceptance

For local validation only.

Behavior:

- fixed random seed
- forced normal encounter
- fixed 4 player vs 6 enemy setup
- summon disabled
- deterministic validation battle

Purpose:

«readability testing»

NOT:

«formal gameplay»

---

## 15. Current Highest Priorities

Priority 1:

«4 player vs 6 enemy readability validation»

Validate:

- can player understand who attacks whom
- can player understand boss actions
- are skills readable
- is combat too noisy or too quiet

Priority 2:

«boss encounter readability»

Includes:

- boss summon encounter layout
- summon spacing
- boss visibility preservation
- boss focus tuning

Priority 3:

«align Focus Queue timing with FINAL rules»

---

## 16. Forbidden Changes

Do NOT:

- invent new combat systems
- revert to chaotic real-time combat
- convert combat into full turn-based combat
- reintroduce speed buttons
- restore character-side cooldown UI
- redesign combat pacing without approval
- overwrite locked combat philosophy
- modify world direction without approval

When uncertain:

«preserve readability, comfort, and travel atmosphere.»

## 2026-06-05 Safe Merge Stage 1

Runtime alignment completed for first-stage verification:

- `project.godot` main scene now points to `res://scenes/HubTavernPrototype.tscn`.
- Hub Tavern v2.2 prototype and World Map Prototype v1 files have been copied into this real Godot project.
- Existing `res://scenes/TavernMainScene.tscn` is retained unchanged.
- Combat system, BattleScene, expedition logic, and worldbuilding content are unchanged.

## Monster Material Source Of Truth

`monster_material_master_database.md` is the SOURCE OF TRUTH for monster drop material names.

Priority order:

```text
monster_material_master_database.md
>
material_usage_master_database.md
>
equipment_database.md
>
recipe_database.md
>
numerical_balance_database.md
```

Formal rules:

- Monster drop material names can only come from `monster_material_master_database.md`.
- `material_usage_master_database.md` must not create new materials.
- Recipe databases must not create new materials.
- Equipment databases must not create new materials.
- If a needed material is missing, report: `未存在於 monster_material_master_database.md`.
- Do not self-complete Boss materials.
- Do not infer chapter materials.
- Do not replace this file with old chat memory, old material tables, old recipe drafts, or unorganized chat records.

Future database work must automatically follow this priority order and these restrictions.
