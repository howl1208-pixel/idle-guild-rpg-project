# Battle UI Current Layout v2

Status: CURRENT LAYOUT SNAPSHOT  
Rules Source: `../combat_system_current.md`  
Supersedes: root `battle_ui_current_layout.md`

Formal battlefield layout v1 snapshot.

Key layout changes:

- Character and enemy visuals are enlarged by roughly 15%.
- HP bars are shortened and centered.
- Battle area now includes a base background and an additional depth overlay layer.
- Battle log area is reduced to preserve more visible battlefield space.
- Buff/Debuff side icon positions are fixed relative to unit slots.
- Battle/Loot tabs use the shared button visual style.
- The middle of the battlefield is prioritized as readable combat space.

---

Godot version: 3.6.1  
Project resolution: 720 x 1280 portrait  
Scene: `res://scenes/BattleScene.tscn`  
Controller: `res://scripts/battle_scene.gd`
Battle rules: `docs/battle_rules_v1.md`
Combat tempo rules: `docs/combat_tempo_rules.md`

This document records the current battle UI layout and behavior after the latest Godot implementation pass.

---

## Battle Rules Source

The formal battle rules are maintained in `docs/battle_rules_v1.md`.

Current key rules affecting UI layout:

- Battle is real-time auto combat.
- Combat uses Real-Time Combat + Global Skill Queue.
- Global Normal Attack Beat enforces a 1.0-second minimum gap between normal attack nodes.
- There is no front-row/back-row system.
- All units exist on the same battlefield layer.
- Player side supports up to 4 player units and 1 summon.
- Enemy side supports up to 6 enemy units.
- Combat log is secondary information.
- Battlefield readability is the highest priority.
- Damage values should stay low-number and avoid inflated scaling.

---

## Battle Tempo Rules

- Formal combat rules are maintained in `../combat_system_current.md`.
- `docs/combat_tempo_rules.md` is retained only as a superseded historical rhythm reference.
- Normal attacks are background rhythm gated by Global Normal Attack Beat.
- Skills enter Global Skill Queue and become focus events one at a time.
- Battlefield readability has priority over animation volume.
- If uncertain, use the quieter visual option.

---

## Effect Rules

- Normal attacks use small effects.
- Only high-tier skills should use full-screen effects.
- DOT effects should not use large visual effects.
- Buffs should prioritize icon-based presentation.

---

## Damage Text Rules

- DOT damage may skip floating damage text.
- Critical damage uses enlarged text.
- Small damage should avoid excessive floating text.

---

## UI Rules

- Buff icons must not cover character heads.
- Battle Log and Loot Log are separated.
- The middle of the battlefield should remain visually readable.
- When 6 enemies are shown, character visuals should scale down by 10%.

---

## Status System Rules Source

Formal status rules are maintained in `docs/status_system_rules.md`.

Current key rules affecting battle UI:

- Status effects are a core combat mechanic.
- Status effects must remain readable on mobile screens.
- Buff/Debuff icons appear beside units and must not cover unit heads.
- DOT effects stay visually quiet and avoid excessive floating numbers.
- Highest visual priority status/effects are Freeze, Boss skills, Legendary skills, Death, and Major Buff activation.

Current implementation state:

- `scripts/status_effect.gd` provides the shared status effect data object.
- Poison, Burn, Frostbite, Freeze, Sleep, Root, Wound, Healing Blessing, Resistance, Erosion, Purify, and Guard now use shared status effect helpers.
- Player skills currently connect tactical status effects:
  - Guardian: Guard and Resistance.
  - Ranger: Root and Wound.
  - Cleric: Purify, Healing Blessing, and Resistance.
  - Mage: Frostbite and a low chance to Freeze.
- Enemy attacks currently connect status pressure:
  - Minion: Poison.
  - Beast: Burn and a low chance to Root.
  - Boss: Poison, Burn, Erosion, and Wound.
- Status icons display duration countdowns beside unit bodies.
- Status icon overflow collapses into a compact `+N` display.
- DOT damage stays visually quiet and does not spawn floating damage text.

---

## Battle Quick Menu v1

Formal quick menu notes are maintained in `docs/battle_quick_menu_v1.md`.

Current implementation state:

- Battle quick menu opens as a compact portrait overlay.
- It allows Bag, Equipment, Field Workshop, Enhance, and Buff/Debuff Status entries.
- It does not open the tavern base, recruitment, tavern events, horizontal scenes, market, or full black market pages.
- It does not pause battle timers or background motion.
- Buff/Debuff Status reads current battle status effect data.

---

## Skill Design Rules

- Skills in the same series should evolve progressively.
- Different class advancements should not completely replace the original playstyle.
- Each skill family should specialize in 1 to 2 core status types.
- Avoid putting too many Buffs or Debuffs on a single skill.
- High-tier skills should prioritize improved scale and battlefield impact.

---

## Prohibited Changes

- Do not add new classes without explicit user approval.
- Do not modify class advancement routes without explicit user approval.

---

## Visual Priority

Highest priority:

- Boss skills
- Legendary skills
- Freeze
- Death

Medium priority:

- Active skills
- Shields

Low priority:

- DOT
- Small Buffs
- Small damage

---

## 1. Screen Structure

```text
BattleScene
- Background
- CanvasLayer
  - TopBar
  - BattleArea
    - BattleBackdrop
    - EnemyArea
      - EnemySlots
      - EnemySummonSlot
    - EffectLayer
    - PlayerArea
      - PlayerSlots
      - PlayerSummonSlot
    - SupportPanel
    - BuffPanel
    - SkillQueueBar
    - SummonReserveSlots
  - BottomActionBar
    - BattleLogPanel
    - ActionButtons
  - LootPanel
  - ResultLabel
- AttackTimer
- StageAdvanceTimer
- PartyRestTimer
```

---

## 2. TopBar

Purpose: global combat information.

Current elements:

- `TitleLabel`
  - Shows game title: `Idle Guild RPG`
- `StageLabel`
  - Shows current stage, enemy count, and best stage.
  - Example: `Stage 3 | Enemies 5 | Best 4`
- `ResourceLabel`
  - Shows gold and idle income.
  - Example: `Gold 120 | Idle +8/s`
- `BattleStateLabel`
  - Shows combat state.
  - Normal: `AUTO`
  - Party resting: `REST | 89s`

Note: battle speed is no longer shown here. Combat playback is fixed at 1x for readable observation.

---

## 3. BattleArea

Purpose: main combat field.

Area includes:

- Enemy field
- Player field
- Summon placeholders
- Effect layer
- Support character slot
- Skill Queue preview bar
- Buff/status slots

The battle area ends above the battle log so the player summon slot visually lines up with the top edge of the battle log area.

---

## 4. EnemyArea

Purpose: enemy formation display and combat targets.

Current enemy slots:

```text
EnemyUnit1
EnemyUnit2
EnemyUnit3
EnemyUnit4
EnemyUnit5
EnemyUnit6
```

Enemy behavior:

- Normal route encounters spawn a weighted enemy count, up to 6 enemies.
- Boss encounters use weighted appearance rather than deterministic stage intervals.
- Unused enemy slots are hidden.
- Each active enemy has independent HP, attack, defense, hit, and evasion.
- Each living enemy attacks during the enemy turn.
- Auto-targeting attacks the first living enemy slot.
- Minion enemies can apply Poison.
- Beast enemies can apply Burn.
- Boss enemies can apply Poison and/or Burn in addition to Heavy Swing.

Victory rewards:

- Gold and equipment drops are settled only after the battle has entered the Victory end state.
- A per-battle settlement flag prevents duplicate reward or loot generation from repeated result checks.

Enemy UI:

```text
EnemyUnit
- Sprite placeholder
- NameLabel
- HPBar
- HPLabel hidden
- StatusIconContainer
```

HP is displayed only as a bar. Numeric HP is hidden.

Flying Enemy System v1:

- Flying enemies begin appearing after early-stage maps.
- Flying enemies visually float above their ground slot.
- Flying enemies show a compact flying indicator icon beside their body.
- Melee normal attacks cannot target flying enemies.
- Ranged and magic attacks can target flying enemies.
- Battlefield readability is prioritized over large flying effects.

---

## 5. EnemySummonSlot

Purpose: future enemy summon/additional unit slot.

Current behavior:

- Placeholder only.
- Does not participate in combat yet.
- Located inside `EnemyArea`.

---

## 6. PlayerArea

Purpose: player party formation.

Current player slots:

```text
PlayerUnit1
PlayerUnit2
PlayerUnit3
PlayerUnit4
```

Player UI:

```text
PlayerUnit
- Sprite placeholder
- NameLabel
- HPBar
- HPLabel hidden
- StatusIconContainer
```

HP is displayed only as a bar. Numeric HP is hidden.
Character-side skill name, cooldown number, cooldown bar, and skill hint UI are removed. Existing `SkillLabel` scene nodes are kept hidden for compatibility only.

Current party:

- Guardian
- Ranger
- Cleric
- Mage

Current skill roles:

- Guardian: `Shield Bash`, single-target damage and a short guard status icon.
- Ranger: `Piercing Shot`, high single-target damage.
- Cleric: `Mend`, heals the lowest HP living party member.
- Mage: `Arcane Burst`, area damage against all living enemies. Targets remain anchored and receive restrained hit flashes.

Current status effects:

- Poison: small damage over time for 3 ticks.
- Burn: stronger damage over time for 2 ticks.
- Guard: short Guardian status that reduces incoming damage.
- Status icons are mounted on the unit slot parent layer instead of inside the unit layout. Player icons sit beside the left side of the unit body, enemy icons sit beside the right side, vertically aligned around the torso area to avoid covering heads.

---

## 7. Player Death And Revival

Individual member death:

- If one party member dies but the party survives, that member stays dead.
- The dead member revives after the party wins 2 stages.
- Revival progress is logged and represented through dead/reviving unit state. Character-side skill labels remain hidden.

Full party defeat:

- If all party members die, the party enters rest mode.
- Rest duration: 90 seconds.
- During rest:
  - No attacks occur.
  - TopBar shows `REST | Ns`.
  - Center result text shows `Reviving in Ns`.
- After rest:
  - All party members revive.
  - The same stage starts again.
  - A fresh enemy group is generated.

Combat feedback:

- Damage displays as a short floating red number above the target.
- Critical damage uses a brighter, slightly larger floating number.
- Healing displays as a floating green number.
- Attackers briefly lunge forward on the vertical battle lane: player units move upward, enemy units move downward.
- Targets briefly flash for hit confirmation and remain anchored in their battlefield positions.
- Multiple actions in the same battle tick are slightly staggered so individual attacker/target pairs remain readable.
- Hit targets remain fixed in place; ordinary and area hits use restrained flashes rather than displacement motion.
- Ordinary hit flash duration follows the locked readability direction of approximately 0.05 to 0.08 seconds.
- Skill users briefly flash blue when a skill is triggered.
- Defeated unit sprites fade down and remain dim until revived or replaced by a new stage.
- DOT damage is kept low priority and does not spawn floating damage text.
- Boss Heavy Swing uses a higher-priority warning flash layer.
- Buff and Debuff side icons are compact 16x16 indicators.

---

## 8. PlayerSummonSlot

Purpose: future player summon slot.

Current behavior:

- Summon System v1 combat slot.
- Supports one active player-side summon at a time.
- Current test summon: Wolf.
- Summons are independent battlefield units with their own HP, attacks, status effects, and aggro weight.
- Summons disappear on death only and do not expire by timer.
- Summon attacks use simplified visual feedback.
- Its lower edge is aligned with the top of the battle log area.

Supported summon types:

- Wolf
- Bear
- Treant
- Skeleton
- Wraith
- Death Knight

---

## 9. SupportPanel

Purpose: support character slot.

Current layout:

- Small square on the lower-left side of `BattleArea`.
- Label: `SUP`

Current behavior:

- Placeholder only.
- Future use:
  - Support character portrait
  - Support passive
  - Support skill entry

---

## 10. Fixed Playback

Status: CURRENT

Combat playback remains fixed at 1x to preserve observation readability. No battle speed control is shown in the battle UI.

---

## 11. BuffPanel

Purpose: reserved status/buff display area.

Current layout:

- Lower-right side of `BattleArea`.
- Four small slots.

Slots:

```text
P = Passive Buff
A = Team Aura
S = Summon Bonus
T = Temporary Status
```

Current behavior:

- Placeholder only.
- Does not affect combat yet.

---

## 12. BottomActionBar

Purpose: battle log and main action navigation.

Contains:

```text
BattleLogPanel
ActionButtons
```

Action buttons:

- `Skill`
- `Gear`
- `Team`
- `Menu`

Current behavior:

- Buttons are placeholders.
- No menu logic is connected yet.

---

## 13. BattleLogPanel

Purpose: combat event history.

Current behavior:

- Scrollable shared log display with `Battle` and `Loot` tabs.
- Battle events and loot drops are stored separately.
- The tab controls are compact buttons placed in the lower-left battle area near the support controls.
- The scrollable log text uses the full log panel area and is not covered by the tabs.
- Latest event appears at the top.
- Older events appear below.
- Maximum stored battle events: 80.
- Maximum stored loot events: 80.
- The log clears when the game window loses focus.
- If the player scrolls down to inspect older events, the view locks.
- While locked, new events are stored internally but do not refresh the visible text.
- When the player returns to the top, the log refreshes to show the newest events.

Events currently recorded:

- Player attacks
- Enemy attacks
- Misses
- Skills
- Gold gain
- Stage clear
- Party defeat
- Rest/revive state
- Individual member death and revival progress
- Skill queue and combat event entries

Loot log currently records:

- Encounter number for each drop
- Equipment rarity
- Equipment slot
- Equipment stat summary

---

## 14. LootPanel

Purpose: previous floating loot display.

Current behavior:

- Hidden.
- Stage clear and loot information are now written into `BattleLogPanel`.

Example log output:

```text
Encounter 3 Complete
Loot Drop: Rare Weapon (+8 ATK, +0.05 Crit Rate)
The journey continues...
Stage clear gold +44
```

---

## 15. ResultLabel

Purpose: central battle result/status text.

Current usage:

- `Victory!`
- `Defeat...`
- `Reviving in Ns`

---

## 16. Timers

### AttackTimer

Purpose:

- Drives combat ticks.

Current behavior:

- Drives combat scheduler pulses.
- Playback is fixed at 1x.
- Important scheduler timing is governed by Global Skill Queue, Global Normal Attack Beat, and Skill Focus Slow.

### StageAdvanceTimer

Purpose:

- Automatically advances to the next stage after victory.

Current delay:

```text
0.75 seconds
```

### PartyRestTimer

Purpose:

- Handles full party defeat recovery.

Current delay:

```text
90 seconds
```

---

## 17. Current Combat Rules Connected To UI

Stages:

- Normal route encounters can spawn up to 6 enemies.
- Boss and elite encounters use weighted appearance.

Victory:

- All active enemies must be defeated.
- A new route encounter begins automatically after 0.75 seconds.
- Loot and gold are logged.

Defeat:

- If all party members die, party rests for 90 seconds.
- After rest, all members revive.
- Same stage restarts with a fresh enemy group.

Individual death:

- A dead member stays dead while the team continues.
- The member revives after 2 stage victories.

HP display:

- HP uses bars only.
- Numeric HP labels are hidden.

Summons:

- Player side supports one active summon in `PlayerSummonSlot`.
- Enemy side supports one active summon in `EnemySummonSlot`.
- Summons use fixed medium-low aggro and do not inherit owner aggro.
- Boss targeting avoids permanently focusing summons.
- Summons vanish when dead and are not revived by timers.
- Summon attacks are intentionally quieter than character and Boss actions.

---

## 18. Future UI Work

Recommended next UI tasks:

1. Replace ColorRect placeholders with real unit sprites.
2. Add selected target indicator.
3. Add click/tap enemy targeting.
4. Connect Skill/Gear/Team/Menu buttons.
5. Add actual passive buff, aura, summon bonus, and temporary status icons.
6. Replace `SUP` text with support portrait.
7. Add visual feedback for dead/reviving party members.
8. Add stage progress or wave indicator.
9. Add equipment drop history or compact loot ticker.
10. Replace temporary summon reserve icons with dedicated summon icons.
