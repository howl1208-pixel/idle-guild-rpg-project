# Battle UI Current Layout

Status: SUPERSEDED  
Superseded By: `docs/battle_ui_current_layout_v2.md` and `combat_system_current.md`  
Retained For: historical UI implementation notes only.

Godot version: 3.6.1  
Project resolution: 720 x 1280 portrait  
Scene: `res://scenes/BattleScene.tscn`  
Controller: `res://scripts/battle_scene.gd`
Battle rules: `docs/battle_rules_v1.md`
Combat tempo rules: `docs/combat_tempo_rules.md`

This document records the current battle UI layout and behavior after the latest Godot implementation pass.

---

## Battle Rules Source

- Formal battle rules are maintained in `docs/battle_rules_v1.md`.
- Battle is real-time auto combat with a base 2.5-second action rhythm.
- There is no front-row/back-row system.
- Player side supports up to 4 player units and 1 summon.
- Enemy side supports up to 6 enemy units.
- Combat log is secondary information.
- Battlefield readability is the highest priority.

---

## Formal Battlefield Layout v1

- Character and enemy visuals are enlarged by roughly 15%.
- HP bars are shortened and centered.
- Battle area uses a base background plus an added depth overlay layer.
- Battle log area is reduced to preserve battlefield readability.
- Buff/Debuff icon positions are fixed relative to unit slots.
- UI controls use shared panel and button texture styles where available.

---

## Battle Tempo Rules

- Formal combat tempo rules are maintained in `docs/combat_tempo_rules.md`.
- Base combat rhythm is approximately 2.5 seconds per action cycle.
- Actions inside the same tick should be staggered.
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

- Formal status rules are maintained in `docs/status_system_rules.md`.
- Status effects are a core combat mechanic.
- Status UI must remain readable on mobile screens.
- Buff/Debuff icons appear beside units and must not cover unit heads.
- DOT effects stay visually quiet.
- Highest visual priority status/effects are Freeze, Boss skills, Legendary skills, Death, and Major Buff activation.
- Current implementation uses `scripts/status_effect.gd` as the shared status effect data object.
- Status icons display duration countdowns beside unit bodies.
- Status icon overflow uses a compact `+N` display.

---

## Summon System v1

- Summons are independent battlefield units.
- Player side supports one active summon in `PlayerSummonSlot`.
- Enemy side supports one active summon in `EnemySummonSlot`.
- Supported summon types: Wolf, Bear, Treant, Skeleton, Wraith, Death Knight.
- Summons have their own HP, attacks, status effects, and medium-low fixed aggro.
- Summons do not inherit owner aggro.
- Boss targeting avoids permanently focusing summons.
- Summons disappear on death only and do not expire by timer.
- Summon attacks use simplified visual effects to preserve battlefield readability.

---

## Flying Enemy System v1

- Flying enemies can only be hit by ranged attacks and magic attacks.
- Melee normal attacks cannot target flying enemies.
- Flying enemies visually float above their battlefield slot.
- Flying enemies use a compact flying indicator icon.
- Flying enemies begin appearing after early-stage maps.
- Mobile readability takes priority over large airborne effects.

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
    - SpeedPanel
    - BuffPanel
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

Note: battle speed is no longer shown here. It has been moved beside the support character slot.

---

## 3. BattleArea

Purpose: main combat field.

Area includes:

- Enemy field
- Player field
- Summon placeholders
- Effect layer
- Support character slot
- Battle speed button
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
```

Enemy behavior:

- A stage may spawn 3, 4, or 5 enemies.
- Every 5th stage always spawns 5 enemies.
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
- SkillLabel
- StatusIconContainer
```

HP is displayed only as a bar. Numeric HP is hidden.

Current party:

- Guardian
- Ranger
- Cleric
- Mage

Current skill roles:

- Guardian: `Shield Bash`, single-target damage and a short guard status icon.
- Ranger: `Piercing Shot`, high single-target damage.
- Cleric: `Mend`, heals the lowest HP living party member.
- Mage: `Arcane Burst`, area damage against all living enemies. Targets use the reserved left-right area hit shake.

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
- `SkillLabel` shows revival progress.
  - Example: `Revive in 2 wins`

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
- Targets briefly flash and knock back away on the same vertical lane.
- Multiple actions in the same battle tick are slightly staggered so individual attacker/target pairs remain readable.
- A left-right area hit shake helper is reserved for future group attacks.
- Skill users briefly flash blue when a skill is triggered.
- Defeated unit sprites fade down and remain dim until revived or replaced by a new stage.
- DOT damage is kept low priority and does not spawn floating damage text.
- Boss Heavy Swing uses a higher-priority warning flash layer.
- Buff and Debuff side icons are compact 16x16 indicators.

---

## 8. PlayerSummonSlot

Purpose: future player summon slot.

Current behavior:

- Placeholder only.
- Does not participate in combat yet.
- Its lower edge is aligned with the top of the battle log area.

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

## 10. SpeedPanel

Purpose: battle speed control.

Current layout:

- Single button placed next to the support character slot on the lower-left side.
- Button text shows current speed.

Speed cycle:

```text
x1 -> x2 -> x4 -> x1
```

Current behavior:

- Pressing the button cycles speed.
- Speed changes `AttackTimer.wait_time`.
- Battle log records speed changes.

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
- The tab controls are compact buttons placed in the lower-left battle area, beside the support and speed controls.
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
- Battle speed changes

Loot log currently records:

- Stage number for each drop
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
Stage 3 Clear
Loot Drop: Rare Weapon (+8 ATK, +0.05 Crit Rate)
Next stage in 2s
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

Affected by:

- Battle speed button.

Speed behavior:

```text
x1 = 1.0s per tick
x2 = 0.5s per tick
x4 = 0.25s per tick
```

### StageAdvanceTimer

Purpose:

- Automatically advances to the next stage after victory.

Current delay:

```text
2 seconds
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

- Normal stages spawn 3, 4, or 5 enemies.
- Every 5th stage spawns 5 enemies.
- Elite Boss stages are currently disabled.

Victory:

- All active enemies must be defeated.
- Stage automatically advances after 2 seconds.
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
8. Add battle speed active-state styling.
9. Add stage progress or wave indicator.
10. Add equipment drop history or compact loot ticker.
