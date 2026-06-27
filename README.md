# Idle Guild RPG MVP

Status: CURRENT README  
Combat Rules Source: `combat_system_current.md`

Godot 3.6.1 mobile portrait MVP generated from `idle_rpg_codex_handoff.md`.

## Open

1. Open Godot 3.6.1.
2. Choose **Import**.
3. Select this folder:
   `C:\Users\User\Documents\Codex\2026-05-05\files-mentioned-by-the-user-idle`
4. Open `project.godot`.
5. Press **Play**.

## Current MVP

- 720 x 1280 portrait project setup.
- `TavernMainScene` is the project main scene; `BattleScene` is the combat prototype scene.
- Battle UI uses a mobile vertical layout with TopBar, BattleArea, and BottomActionBar.
- Enemy and player areas use unit slots based on the battle UI handoff.
- Route encounters can spawn up to 6 active enemies with individual HP and attacks.
- Four player units fight automatic weighted encounters.
- Each unit has HP, attack, defense, crit, lifesteal, hit, and evasion stats.
- Each player unit has one automatic skill; character-side cooldown UI is removed in favor of the Skill Queue.
- Boss victory creates one equipment drop.
- HP bars update during battle.
- Battle ends with `Victory!` or `Defeat...`.
- Victory unlocks the next stage.
- Victory automatically advances to the next stage after a short delay.
- Enemies scale up by route encounter. Boss encounters use weighted appearance during travel.
- Gold is earned during battle, on stage clear, and while offline.

## Skills

- Guardian: `Shield Bash`, stronger damage every 3 turns.
- Ranger: `Piercing Shot`, high damage every 4 turns.
- Cleric: `Mend`, heals the lowest HP ally every 4 turns.
- Mage: `Arcane Burst`, burst damage every 5 turns.
- Boss: `Heavy Swing`, queued as a high-priority focus event when ready.

## Equipment Drops

- Equipment slots: Weapon, Helmet, Armor, Boots, Ring, Amulet.
- Rarities: Common, Uncommon, Rare, Epic, Legendary.
- Each rarity changes stat count and stat strength.
- Drops appear after `Victory!`.

## Stage Progression

- The current and highest unlocked stage appear at the top.
- After victory, the game automatically starts the next stage after 2 seconds.
- Press `Next Stage` to advance immediately.
- Player HP refills at the start of each stage.
- Equipment drop strength uses the current stage as enemy level.

## Battle UI Layout

- TopBar: journey, encounter label, enemy count, gold, idle rate, and combat state.
- Combat playback: fixed at 1x for readable observation; no battle speed control is shown.
- Skill Queue: up to 6 unit portraits above the battle log.
- BattleArea: 6 enemy slots, 4 player slots, enemy summon slot, player summon slot, effect layer, support panel.
- BuffPanel: left-side slots reserved for passive buffs, team aura, summon bonuses, and temporary statuses.
- BottomActionBar: battle log and four placeholder buttons.
- Stage clear, loot drops, and auto-advance notices are shown inside the battle log.
- Battle log keeps up to 80 events and clears when the game window loses focus.
- On defeat, the party rests for 90 seconds, revives, and spawns a fresh enemy group on the same stage.
- If an individual party member dies but the party survives, that member revives after the party wins 2 stages.
- Enemy slots are active only when the current stage spawns that enemy.
- Auto-targeting attacks the first living enemy slot.
- Living enemies each attack during the enemy turn.

## Idle Rewards

- Gold per second scales with the highest unlocked stage.
- Battle ticks grant gold while the game is open.
- Clearing a stage grants bonus gold, with a bigger bonus every 5 stages.
- Offline rewards are calculated from the last saved time, capped at 6 hours.

## Core Files

- `scenes/BattleScene.tscn`
- `scripts/battle_scene.gd`
- `scripts/character_stats.gd`
