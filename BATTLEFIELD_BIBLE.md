# BATTLEFIELD_BIBLE.md

Status: Review Draft
Architecture: Art Documentation Architecture Review Draft

Purpose:

Defines how characters are visually read during battle.

This document gradually absorbs battlefield-related review rules.

It answers:

"How should players read this character during battle?"

---

## Scope

Contains:

- PLAYER_BATTLEFIELD_VIEW_DIRECTION_RULE_V2
- REAR_DOMINANT_READABILITY_RULE_V1
- SHIELD_READABILITY_RULE_V1
- Mount Readability Rule
- Mounted Character Scale Rule
- Character Scale Rules
- Character Spacing Rules
- Battlefield Silhouette Rules
- Cape Readability Rules
- Weapon Readability Rules
- Flying Unit Rule
- Boss Readability Rule
- UI Overlap Rules
- Safe Area Rules

Must NOT define:

- Profession identity
- Armor progression identity
- Weapon progression identity
- Color palette identity
- World identity
- Master character design references

Those belong in `CHARACTER_BIBLE.md`.

---

## Current Approved Review Candidate

35° Floor-Direction View

Rear-Dominant View

Battlefield Movement Read First

Player movement direction:

Lower-left -> Upper-right

Primary read:

- Back
- Back armor
- Back cape
- Shield backside
- Rear silhouette

Secondary read:

- Small side information
- Shield thickness
- Weapon silhouette
- Shoulder contour

Minor read:

- Minimal face
- Minimal chest
- Minimal shield front

---

## Migration Plan

`CHARACTER_VIEW_RULE_V2.md` currently acts as the temporary battlefield review document.

Validated battlefield readability contents should gradually migrate into this document.

After migration is complete, mark `CHARACTER_VIEW_RULE_V2.md` as Superseded Review Draft.

---

## Status Rule

This document is Review Draft only.

Do not promote to Active Rule without explicit user approval.

Do not treat as production lock.
