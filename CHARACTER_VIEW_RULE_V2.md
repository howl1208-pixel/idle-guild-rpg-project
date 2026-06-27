# CHARACTER_VIEW_RULE_V2

Version: v2
Status: Review Draft
Supersedes: CHARACTER_VIEW_RULE_V1.md for player battlefield view interpretation

Purpose:

Define the current approved review candidate for character battlefield view, player/enemy facing, rear-dominant readability, shield readability, boss presentation, flying unit placement, knight civilization silhouette, and corridor battlefield presentation.

This document belongs to the Character Visual System.

This document does not modify:

- Combat System
- Targeting System
- Skill Queue
- Damage Formula
- Class Tree
- Godot scenes
- Runtime scripts

---

## Chapter 01 - Battlefield View Rule

Current approved review candidate:

35° Floor-Direction View

Rear-Dominant View

Battlefield Movement Read First

Definition:

- 0° = character faces screen-up / into battlefield depth
- 45° = character faces the upper-right battlefield diagonal
- 90° = character faces screen-right / pure side view

Therefore:

- 35° is a battlefield floor movement direction.
- 35° is not face exposure.
- 35° is not chest exposure.
- 35° is not a showcase angle.
- 45° must not be interpreted as pure side view.
- 90° is pure side view.

Formal battlefield direction:

Player units advance from lower-left toward upper-right.

Enemy units oppose from upper-right toward lower-left.

Forbidden:

- Pure side view as the standard player view
- Isometric interpretation by default
- Front-facing character showcase pose
- Chest-forward display pose
- Face-forward portrait pose
- Using visible face amount to define the angle

---

## Chapter 02 - Player Facing Rule

Player Facing:

↗

Player battlefield direction:

Lower-left -> upper-right

Player view standard:

35° Floor-Direction View

Rear-Dominant View

Primary read:

- Back
- Back armor
- Back cape
- Back silhouette
- Rear-facing equipment surfaces

Secondary read:

- Small amount of side information
- Weapon silhouette
- Shoulder contour
- Shield thickness / side edge

Minor read:

- Minimal face information
- Minimal chest information
- Minimal shield front surface

The player unit should feel like it is moving forward into battle, not displaying itself to the player.

---

## Chapter 03 - Shield Readability Rule

Shield visibility follows the same rule as face visibility.

Primary read:

- Shield backside

Secondary read:

- Shield thickness
- Shield side edge
- Shield attachment / arm relationship

Minor read:

- Small amount of shield front surface

Forbidden:

- Full shield emblem display
- Full shield front showcase
- Front-facing heraldry presentation

Reason:

Player units are read from the rear. Shields must support battlefield movement readability, not character showcase readability.

---

## Chapter 04 - Enemy Facing Rule

Enemy Facing:

↙

Enemy battlefield direction:

Upper-right -> lower-left

Enemy view may mirror the player battlefield relationship, but enemy readability may be adjusted by monster role, threat readability, body type, and boss rules.

Standard enemies should preserve battlefield opposition clarity without forcing player-facing portrait display.

---

## Chapter 05 - Boss Facing Rule

Boss units do not need to follow normal enemy facing strictly.

Boss presentation may use stronger front readability when required by threat identity.

Boss Priority:

1. Threat Readability
2. Visual Identity
3. Skill Readability
4. Battlefield Direction Consistency

The player should be able to read:

- Head or core identity feature
- Chest or central threat feature when needed
- Main weapon or attack source
- Boss-specific silhouette

Forbidden:

- Completely side-only boss when threat identity is lost
- Completely back-facing boss when threat identity is lost
- Showcase pose that breaks battlefield movement logic without reason

---

## Chapter 06 - Flying Enemy Rule

Flying Enemy:

Combat Focus Zone Above

Flying enemies do not use the same baseline as ground enemies.

Used for:

- Flying dragon
- Griffon-type enemy
- Phoenix-type enemy
- Floating monster

Ground Enemy:

Enemy Formation Area

Flying enemies must preserve visual separation from ground enemies.

---

## Chapter 07 - Knight Civilization Rule

Horse is a civilization silhouette element.

Horse does not mean forced mounted gameplay.

Closed Beta Direction:

Character + Horse Companion Silhouette

Horse may be placed:

- Behind the character
- Side-rear of the character

In 35° rear-dominant battlefield view, horse readability must prioritize:

- Rear-depth silhouette
- Body mass relationship to rider or companion position
- Movement direction toward upper-right
- Non-occlusion of weapon, shield, cape, and class silhouette

Forbidden:

- Full side-view horse as the default player standard
- Front showcase horse pose
- Horse placement that blocks shield readability
- Horse placement that blocks cape silhouette
- Horse placement that reverses battlefield direction

---

## Chapter 08 - Corridor Battlefield Rule

Formal battlefield structure:

Player Area

↓

Combat Focus Zone

↓

Enemy Area

Formal opposition axis:

Lower-left -> Upper-right

Player Facing:

↗

Enemy Facing:

↙

Boss:

Threat readability may override normal enemy rear/side balance.

Combat Focus Zone:

Keep horizontal.

Forbidden:

- Tilting the Combat Focus Zone
- Treating the battlefield as a square isometric board
- Replacing the corridor read with front/back row layout

---

## Chapter 09 - Relationship To V1

`CHARACTER_VIEW_RULE_V1.md` remains retained as a superseded review draft.

Do not delete V1.

Do not promote V1 to Active Rule.

V1's useful retained concepts:

- Character Visual System ownership
- Player ↗ / Enemy ↙ opposition axis
- Boss exception concept
- Flying enemy vertical separation
- Knight horse-as-civilization-silhouette concept
- Corridor battlefield concept

V1 concepts superseded by V2:

- Player Visible Angle: Right Rear 45°
- Interpreting the view through visible face/chest amount
- Any reading that causes 45° to become pure side view
- Any reading that prioritizes showcase readability over battlefield movement readability

---

## Chapter 10 - Source Alignment

V2 aligns with:

- PLAYER_BATTLEFIELD_VIEW_DIRECTION_RULE_V2
- REAR_DOMINANT_READABILITY_RULE_V1
- SHIELD_READABILITY_RULE_V1

Current approved review candidate:

35° Floor-Direction View

Rear-Dominant View

Battlefield Movement Read First

---

## Audit Notes

This file is a Review Draft until added to `SOURCE_OF_TRUTH_INDEX.md`.

If promoted later, update:

- `SOURCE_OF_TRUTH_INDEX.md`
- Character Visual System index, if one is created
- Sprite / silhouette production specifications
- Battlefield validation handoff documents

This file does not modify Godot scenes, runtime scripts, combat rules, or gameplay systems.
