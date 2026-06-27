# GUARD_BATTLEFIELD_CONFRONTATION_VALIDATION_V1.md

Status: Review Draft

Purpose:

Validate the official Guard Battlefield Master inside an actual battlefield composition.

The objective is not to evaluate artwork quality.

The objective is to verify gameplay readability during real combat.

This document does not modify:

- CHARACTER_BIBLE.md
- BATTLEFIELD_BIBLE.md
- BATTLEFIELD_ADAPTATION_WORKFLOW.md
- SCALE_VALIDATION_WORKFLOW.md
- GUARD_BATTLEFIELD_VALIDATION_V1.md
- SOURCE_OF_TRUTH_INDEX.md
- Gameplay systems
- Godot scenes
- Runtime code
- Sprite pipeline

---

## Reference

Character:

`Guard_Battlefield_Master_V1_candidate_01`

Battlefield Rules:

`BATTLEFIELD_BIBLE.md`

Scale Validation:

`SCALE_VALIDATION_WORKFLOW.md`

---

## Validation Scenario

Player:

Guard

Enemies:

- Border Wolf
- Goblin Scout

Optional later:

- Slime
- Bandit
- Skeleton

---

## Validation Categories

### 1. Player Recognition

Can the player immediately identify Guard?

Result:

PASS / FAIL

### 2. Enemy Separation

Can Guard be immediately distinguished from enemies?

Result:

PASS / FAIL

### 3. Silhouette Recognition

Is the shield silhouette still dominant?

Result:

PASS / FAIL

### 4. Combat Focus

Does Guard naturally attract the correct visual focus without excessive decoration?

Result:

PASS / FAIL

### 5. Rear-Dominant Readability

Does the 35° rear-dominant view remain readable?

Result:

PASS / FAIL

### 6. Equipment Recognition

Can players clearly recognize:

- Helmet
- Straight Sword
- Kite Shield

Result:

PASS / FAIL

### 7. Scale Readability

Does Guard remain readable at actual gameplay size?

Result:

PASS / FAIL

### 8. Adjacent Promotion Space

Does the current design leave enough visual space for:

- Shield Guard
- Vanguard
- Knight
- Royal Knight

Result:

PASS / FAIL

---

## Review Result

PASS

or

Revision Required

---

## Production Rule

If the confrontation validation fails, Battlefield Master must be revised before Battlefield Approval.

No Pixel Sprite production may begin.

---

## Workflow

```text
Gameplay Character
-> Battlefield Master
-> Battlefield Confrontation Validation
-> Scale Validation
-> Battlefield Approval
-> Pixel Sprite
```

---

## Status Rule

Do not promote to Active Rule.
