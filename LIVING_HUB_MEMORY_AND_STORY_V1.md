# LIVING_HUB_MEMORY_AND_STORY_V1

Status:
OFFICIAL SOURCE OF TRUTH

Purpose:
Define what the Tavern remembers, what does not need persistence, and how Tavern resident stories should exist without becoming forced quests or daily tasks.

Depends on:

- LIVING_HUB_PHILOSOPHY_V1.md
- LIVING_HUB_ORIENTATION_RULE_V1.md

This document does not replace LIVING_HUB_PHILOSOPHY_V1.md.
It extends the Living Hub philosophy by defining memory, persistence, and resident story rules.

---

## 1. Core Rule

Only gameplay-relevant entities require persistent memory.

Ambient life does not require exact state memory.

The Tavern should feel alive, not frozen in time.

The player should experience the Tavern as a continuous place, but this does not mean every minor ambient animation or background action must be preserved exactly.

---

## 2. Functional Memory

Functional entities must preserve their gameplay state.

Examples:

- Recruitable travellers
- Traveller refresh timer
- Expedition teams
- Workshop completion state
- Blacksmith production state
- Warehouse inventory
- Player camera focus position

Functional state must be reliable because it affects player decisions, rewards, progress, or access to systems.

---

## 3. Traveller Memory

Recruitable travellers are functional entities.

Traveller refresh rule:

- Refresh cycle: every 6 hours
- Refresh amount: 2 travellers per cycle

Travellers should remain available during their active refresh window.

Travellers may perform small seat-based animations:

- Drinking
- Chatting
- Looking at a map
- Looking out the window
- Resting
- Waiting quietly

Traveller animation may vary, but the traveller identity and availability must remain stable until refreshed, recruited, or replaced by system rules.

The player should be able to trust that a recruitable traveller does not disappear because of ambient behaviour.

---

## 4. Ambient Life Does Not Need Exact Memory

Ambient NPC behaviour does not require exact continuity.

Example:

If the player leaves the Tavern for battle and returns after a few seconds, the bartender may be doing a different activity.

Allowed ambient transitions:

- Bartender cleaning a glass
- Bartender arranging bottles
- Bartender speaking with a traveller
- Workshop apprentice carrying boxes
- Blacksmith sitting in the traveller area
- Bard adjusting instrument
- Random resident walking through the room

This is acceptable because the Tavern is continuously living.

Ambient changes should feel natural, not random in a way that breaks the feeling of place.

---

## 5. Memory Principle

Functional state must be reliable.

Ambient life must feel natural.

Do not over-persist minor ambient animation states.

The Tavern should not feel like it was paused only because the player changed screens.

Persistence should be used where player trust requires it.
Variation should be used where living atmosphere benefits from it.

---

## 6. Player Camera Memory

The Tavern remembers the player's last camera focus.

If the player leaves the Tavern from the Right Zone, returning to the Tavern should restore the Right Zone focus when appropriate.

This reinforces the feeling that the player is returning to the same place, not reopening a menu.

Camera memory is a functional comfort feature because it preserves the player's recent context.

Camera memory operates inside the Tavern's landscape camera-anchor system.

Do not interpret Tavern camera memory using Battlefield portrait camera rules.

---

## 7. Tavern Stories

The Tavern should contain resident stories.

These are not main quests.

These are not mandatory daily tasks.

These are small repeated or evolving details that make the player feel familiar with the Tavern residents.

Examples:

- Bartender recognising regular travellers
- Blacksmith occasionally drinking in the traveller area
- Workshop apprentice carrying the wrong crate
- Bard changing songs after major world events
- A traveller always choosing a window seat
- Residents reacting subtly after a boss defeat

Resident stories should build familiarity over time without becoming required progression content.

---

## 8. Story Philosophy

Tavern stories should be discovered, not forced.

They should reward observation.

They should never block gameplay.

They should never become mandatory checklists.

The player may ignore them completely and still progress normally.

Story details should make the Tavern feel more personal, not more demanding.

---

## 9. Resident Rule

The Tavern is not filled with NPCs.

The Tavern is filled with residents.

Residents may have jobs, but they are not only function buttons.

When not directly interacted with, they should behave like people living inside the Tavern.

Resident behaviour should support the Living Hub philosophy:

- They exist in the place.
- They have routines.
- They can rest.
- They can talk.
- They can move.
- They can react subtly to the world.

---

## 10. Interaction Rule

Functionality must remain accessible even when residents move.

Example:

If the blacksmith is drinking in the traveller area, the player can still access blacksmith functions.

The interaction may either:

- Open the blacksmith interface directly.
- Briefly imply the blacksmith returns to work.

Resident behaviour must never make the player search for a function.

Living behaviour supports atmosphere.
It must not create friction.

---

## 11. Future Review Items

To be reviewed later:

- Whether Tavern residents should have named recurring identities.
- How many recurring resident stories should exist in Closed Beta.
- Whether story reactions should unlock after boss defeats.
- Whether bard songs should reflect world progress.
- How much persistence is needed for non-functional residents.

---

Status:
OFFICIAL SOURCE OF TRUTH
