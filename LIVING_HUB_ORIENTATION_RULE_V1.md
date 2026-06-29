# LIVING_HUB_ORIENTATION_RULE_V1

Status:
OFFICIAL SOURCE OF TRUTH

Purpose:
Define the official gameplay orientation rule for the Living Hub Tavern and prevent Battlefield portrait rules from being applied to Tavern design.

Depends on:

- LIVING_HUB_PHILOSOPHY_V1.md
- LIVING_HUB_SPATIAL_LAYOUT_V1.md

This document does not replace its dependencies.
It defines orientation priority for all Tavern layout, camera, validation, and future implementation decisions.

---

## 1. Core Orientation Rule

The Living Hub Tavern is a landscape gameplay scene.

The Battlefield is a portrait gameplay scene.

Do not apply Battlefield portrait viewport rules to the Tavern.

---

## 2. Tavern Gameplay Orientation

Tavern gameplay uses a horizontal scene composition.

The Tavern is a wide, continuous building.

Players move attention horizontally across:

- Left Zone
- Center Zone
- Right Zone

The Tavern should feel like one connected landscape interior, not a portrait menu screen.

---

## 3. Battlefield Separation

Battlefield validation and combat use portrait rules.

Battlefield portrait rules include:

- Portrait combat viewport
- Battlefield composition
- Combat readability
- Player and enemy battlefield placement

These rules do not define Tavern layout.

Tavern layout must not inherit Battlefield portrait assumptions unless explicitly approved by a future Tavern-specific document.

---

## 4. Camera Anchor Rule

The Tavern uses landscape camera anchors.

Primary anchors:

- Left Anchor
- Center Anchor
- Right Anchor

Camera movement should slide horizontally through one continuous Tavern.

Adjacent zones should slightly preview their primary landmarks inside the neighboring camera anchor.

This preview should encourage natural exploration while keeping the Center Zone as the dominant visual focus.

---

## 5. Validation Rule

All future Tavern spatial blocking, camera validation, layout testing, and Godot implementation planning must use landscape orientation.

Do not validate Tavern layout using a portrait canvas.

Portrait Tavern sketches are deprecated unless explicitly used only as historical reference.

---

## 6. Current Approved Direction

Current Tavern direction:

- Landscape gameplay
- Horizontal building
- Three connected camera anchors
- Adjacent landmark preview
- Center Zone remains dominant
- Left Zone contains social arrival flow
- Right Zone contains progress flow

---

## Future Review Items

- Define final Tavern landscape resolution.
- Define exact camera anchor width and overlap.
- Define how much adjacent landmark preview is visible in each camera anchor.
- Define whether the first arrival camera starts at the Main Entrance or transitions into the Center Zone.

---

Status:
OFFICIAL SOURCE OF TRUTH
