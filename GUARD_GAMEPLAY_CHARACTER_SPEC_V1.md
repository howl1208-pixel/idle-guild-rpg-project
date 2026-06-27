# GUARD_GAMEPLAY_CHARACTER_SPEC_V1.md

Status: Review Draft

Purpose:

Define the shared gameplay character used by all in-game representations.

The Gameplay Character is the common foundation for:

- Battlefield Character
- Hub Character
- Future Sprite Production

Only animation and pose differ between gameplay contexts.

This document bridges:

```text
Character Master Reference
-> Gameplay Character
-> Battlefield / Hub
```

This document does not modify:

- CHARACTER_BIBLE.md
- BATTLEFIELD_BIBLE.md
- SOURCE_OF_TRUTH_INDEX.md
- Gameplay systems
- Runtime code

---

## Reference

Official Master Reference:

`Guard_Master_V1`

---

## Character Scale

Head Proportion:

3.5-4 heads.

This proportion is shared by:

- Battlefield
- Hub

Do not create separate body proportions.

---

## Equipment Scale

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

No gameplay version should redesign equipment.

---

## Color Language

Maintain the same palette defined by Character Bible.

Only lighting may differ.

---

## Material Language

Maintain the same material identity.

Do not simplify into another visual language.

---

## Animation Separation

Battlefield:

Combat-oriented animation.

Hub:

Relaxed daily-life animation.

The model itself remains identical.

---

## Production Rule

Gameplay Character is the only source used for:

- Battlefield
- Hub
- Sprite Production

Future improvements begin from Gameplay Character rather than recreating separate versions.

---

## Status Rule

Do not promote to Active Rule.
