# GUARD_GAMEPLAY_CHARACTER_MASTER_V1.md

Status: Official Gameplay Master Candidate / Review Draft

Purpose:

Guard Gameplay Character is the single gameplay source for every in-game representation.

It is not a concept illustration.

It is not a sprite sheet.

It is the gameplay master model.

This document defines the production target for the in-game Guard character.

This document does not modify:

- CHARACTER_BIBLE.md
- BATTLEFIELD_BIBLE.md
- GUARD_GAMEPLAY_CHARACTER_SPEC_V1.md
- Gameplay systems
- Runtime code
- Sprite pipeline

---

## Reference

Official Character Master Reference:

`Guard_Master_V1`

Gameplay Character Specification:

`GUARD_GAMEPLAY_CHARACTER_SPEC_V1.md`

---

## Shared Identity

Must preserve:

- Face identity
- Hairstyle
- Helmet
- Straight sword
- Kite shield
- Blue kingdom cloth
- Armor language
- Material language
- Character proportions

The player must immediately recognize:

"This is Guard_Master_V1."

---

## Gameplay Proportion

Head proportion:

3.5-4 heads.

Designed for gameplay readability.

Shared by:

- Battlefield
- Hub

---

## Shared Equipment

Weapon:

Shared.

Shield:

Shared.

Armor:

Shared.

Helmet:

Shared.

Cape:

Shared.

No redesign.

No gameplay-exclusive equipment.

---

## Shared Color Language

Maintain Character Bible colors.

Do not create different palettes for Hub or Battlefield.

Lighting may differ.

Palette may not.

---

## Shared Material Language

Steel remains steel.

Leather remains leather.

Cloth remains cloth.

Material identity must remain identical across every gameplay representation.

---

## Animation Compatibility

Gameplay Character must support:

### Battlefield

- Idle
- Walk
- Attack
- Hit
- Skill
- Death

### Hub

- Idle
- Walk
- Sit
- Drink
- Talk
- Observe
- Relax

No separate gameplay character is created.

Only animation changes.

---

## Production Rule

Every future gameplay asset derives from this document.

- Battlefield Character
- Hub Character
- Sprite Sheet
- Animation

Future visual improvements begin here.

---

## Status Rule

Do not promote to Active Rule.
