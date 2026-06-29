# LIVING_HUB_SPATIAL_LAYOUT_V1

Status:
OFFICIAL SOURCE OF TRUTH

Purpose:
Define the permanent spatial composition of the Living Hub Tavern.

This document defines the relationship between the three Tavern zones, player visual flow, landmark placement, and spatial hierarchy.

This document does not define Godot implementation, artwork production, animation, or runtime behaviour.

Depends on:

- LIVING_HUB_PHILOSOPHY_V1.md
- LIVING_HUB_MEMORY_AND_STORY_V1.md
- LIVING_HUB_ORIENTATION_RULE_V1.md

This document does not replace or modify its dependencies.

---

## Orientation Rule

The Living Hub Tavern is a landscape gameplay scene.

The Tavern is a horizontal building and should be planned, validated, and implemented as a landscape space.

Only the Battlefield uses portrait gameplay orientation.

Do not apply Battlefield portrait viewport rules to Tavern layout.

---

## 1. Core Spatial Philosophy

The Tavern is one continuous building.

It is not three separate scenes.

Players move their attention across one living Tavern.

Every zone should feel physically connected.

The spatial layout should support the feeling that the player is inside one inhabited place rather than navigating separate function screens.

---

## 2. Three-Zone Layout

The Tavern is organized into three connected emotional spaces:

- Left Zone
- Center Zone
- Right Zone

Each zone has a clear theme, emotional question, landmark set, and spatial purpose.

### Left Zone

Theme:
Social Heart / Arrival.

Player Emotion:
"What happened today?"

Primary elements:

- Tavern Main Entrance
- Small Vestibule / doorway transition
- Tavern Bar against the rear wall
- Bartender behind the Tavern Bar
- Two Traveller Tables, 4 seats each
- Recruitable Travellers
- Bard
- Large Window
- World atmosphere

Purpose:

The Left Zone encourages arrival, social discovery, and curiosity.

Players naturally discover new travellers, rumours, and subtle world changes here.

The Left Zone should feel like the Tavern's connection to the outside world.

The Tavern Main Entrance is the primary entrance used by travellers, guests, merchants, and the player's first arrival.

The Tavern Bar belongs to the Bartender and should sit against the rear wall.

The foreground should remain available for traveller tables, recruitable travellers, the Bard, and the main circulation path.

The Bard should be close to the traveller seating area and main circulation path to encourage natural gathering.

### Center Zone

Theme:
The Guild.

Player Emotion:
"What should we do today?"

Primary elements:

- Six-member Round Table
- Inn
- Fireplace
- Expanded main walking area

Purpose:

This is the emotional heart of the Tavern.

Players return here after every expedition.

The Round Table represents the player's travelling guild.

The Inn represents home.

The Fireplace represents warmth.

This is the default login position after the first arrival.

The Center Zone has only three permanent landmarks:

1. Round Table
2. Inn
3. Fireplace

Removing the Tavern Bar from the Center preserves a larger walking area and keeps the Center focused on guild identity.

### Right Zone

Theme:
Growth.

Player Emotion:
"What did we accomplish?"

Primary elements:

- Blacksmith
- Workshop
- Market entrance
- Basement warehouse entrance
- Furnace

Purpose:

Everything here represents progress created by previous expeditions.

The Blacksmith and Furnace form one adjacent visual landmark.

The Blacksmith is the visual focus.

The Workshop is the production focus and should sit behind or below the Blacksmith.

The Market Entrance should sit at the far upper-right corner and represent the transition from Tavern interior to the outdoor world.

The Right Zone should feel productive, practical, and connected to guild growth.

The Right Zone should visually flow:

Blacksmith

↓

Workshop

↓

Market Entrance

---

## 3. Spatial Hierarchy

The player's eye should naturally follow:

Center

↓

Left

↓

Right

No UI should force this movement.

Players explore naturally.

The layout should guide attention through composition, landmark placement, lighting, and spatial weight rather than through forced interaction order.

---

## 4. Landmark Rule

Every zone must contain memorable landmarks.

Players should remember locations naturally rather than through UI icons.

### Left Zone Landmarks

- Traveller Tables
- Window
- Bard

### Center Zone Landmarks

- Round Table
- Inn
- Fireplace

### Right Zone Landmarks

- Blacksmith
- Workshop
- Market Door
- Warehouse Entrance

Landmarks should support memory, orientation, and emotional identity.

---

## 5. Spatial Density

Avoid filling every area.

Every zone must contain intentional empty space.

Negative space is part of the Tavern atmosphere.

The Tavern should feel comfortable rather than crowded.

Furniture, characters, props, and environmental detail should leave enough breathing room for the player to understand the space quickly.

---

## 6. Visual Weight

Center Zone should remain the strongest visual focus.

Suggested hierarchy:

Center > Left > Right

Individual landmark priority:

1. Round Table
2. Inn
3. Fireplace
4. Traveller Tables
5. Blacksmith
6. Workshop
7. Window
8. Market Entrance

Future art production may adjust proportions while preserving this hierarchy.

Visual weight may be expressed through:

- Size
- Lighting
- Contrast
- Animation attention
- Character density
- Landmark clarity
- Camera framing

---

## 7. Camera Rule

The Tavern uses three primary camera anchors:

- Left
- Center
- Right

Players slide naturally between them.

Camera movement should feel like turning attention inside one Tavern.

It should not feel like changing scenes.

Camera anchors should preserve spatial continuity and reinforce the three-zone structure.

Camera anchors operate horizontally in the Tavern's landscape scene.

Adjacent zones should slightly preview their primary landmarks inside the neighboring camera anchor.

Examples:

- Left Anchor may preview the edge of the Center landmarks.
- Center Anchor may preview part of the Left social landmark area and part of the Right Blacksmith landmark.
- Right Anchor may preview the edge of the Center landmarks.

Adjacent preview should encourage natural exploration while keeping the Center Zone as the dominant visual focus.

---

## 8. Player View

First Arrival:

Player enters through the Tavern door.

The camera moves into the Center Zone.

Subsequent logins:

Restore the player's previous camera position.

The player should feel they are returning to the same Tavern.

The player's view should support memory, familiarity, and continuity.

---

## 9. Spatial Principle

Every area must answer one emotional question.

Left:

"What happened today?"

Center:

"What should we do today?"

Right:

"What did we accomplish today?"

These emotional themes are more important than individual gameplay functions.

If a spatial decision strengthens the emotional question of its zone, it is likely aligned with this document.

If a spatial decision turns the Tavern into a menu screen, it should be reconsidered.

---

## 10. Future Review Items

Review later:

- Final visual weight percentages.
- Exact furniture blocking.
- Camera transition speed.
- Camera anchor width and adjacent landmark preview amount.
- Foreground / background layering.
- Lighting composition.
- Pixel art composition.
- Godot implementation.

---

Status:
OFFICIAL SOURCE OF TRUTH
