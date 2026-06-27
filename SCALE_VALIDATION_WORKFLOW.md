# SCALE_VALIDATION_WORKFLOW.md

Status: Review Draft

Purpose:

Define the official validation process for reviewing gameplay characters at actual in-game display size.

Artwork must never be approved using full-resolution images alone.

Every Battlefield Master must pass Scale Validation before becoming an Official Battlefield Reference.

This document does not modify:

- CHARACTER_BIBLE.md
- BATTLEFIELD_BIBLE.md
- BATTLEFIELD_ADAPTATION_WORKFLOW.md
- SOURCE_OF_TRUTH_INDEX.md
- Gameplay systems
- Godot scenes
- Runtime code
- Sprite pipeline

---

## Reference

Applies to:

- Player Characters
- Monsters
- NPCs
- Bosses
- Future Summons

---

## Validation Sizes

Every Battlefield Master must be reviewed at:

- 160 px
- 140 px
- 120 px
- 96 px

Use the actual expected in-game display size.

Do not upscale for review.

---

## Validation Categories

### 1. Profession Recognition

Can players immediately identify the profession?

Result:

PASS / FAIL

### 2. Primary Silhouette

Is the primary silhouette still recognizable?

Examples:

- Shield
- Bow
- Staff
- Dual Daggers
- Lute

Result:

PASS / FAIL

### 3. Equipment Recognition

Can the primary weapon and equipment still be identified?

Result:

PASS / FAIL

### 4. Color Recognition

Can the profession's primary color language still be recognized?

Result:

PASS / FAIL

### 5. Character Readability

Does the character remain visually readable during gameplay?

Result:

PASS / FAIL

### 6. Combat Recognition

When placed beside enemies and allies, can players immediately distinguish the character?

Result:

PASS / FAIL

### 7. Evolution Recognition

When compared with adjacent promotions:

Promotion 1 <-> Promotion 2

Promotion 2 <-> Promotion 3

Players must immediately perceive visual progression.

Result:

PASS / FAIL

---

## Golden Rule

If recognition is lost after scaling, increase silhouette clarity.

Do not solve readability by adding more decorative details.

At gameplay scale, silhouette always has higher priority than detail.

---

## Validation Rule

If any category fails, the Battlefield Master must be revised before Battlefield Approval.

Pixel Sprite production may not begin until Scale Validation passes.

---

## Workflow

```text
Character Master
-> Gameplay Character
-> Battlefield Master
-> Scale Validation
-> Battlefield Approval
-> Pixel Sprite
```

---

## Status Rule

Do not promote to Active Rule.
