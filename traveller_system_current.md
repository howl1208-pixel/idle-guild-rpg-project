# traveller_system_current.md

Status: CURRENT / SINGLE SOURCE SUMMARY
Purpose: Current single-source recovery document for traveller system direction after context loss.
Sources: GAME_CURRENT_VERSION.md, CURRENT_PROJECT_STATE.md, CHANGELOG.md, DEVLOG.md, WORK_LOG.md.

This document consolidates already-recorded current direction only. It does not add new traveller mechanics, new recruitment rules, new NPC identities, new lore, or new economy behavior.

Terminology note: source files use both `traveler` and `traveller` in conversation. This file uses `traveller` in the title, but preserves source meaning.

---

## 1. Core Position

Travellers belong to the Hub Tavern / tavern-first home direction.

Formal tavern functions include:

- Traveller recruitment.
- Expedition entry.
- Tavern events.
- Late-night rest.
- Map / expedition setup direction.

Current project direction:

- Tavern-first home scene: Hub Tavern.
- Low-frequency life feeling.
- Living world without fatigue.
- Low-interference UI.
- Travel atmosphere must be preserved.

---

## 2. Tavern Role

The tavern is the main home scene / Hub Tavern, not a town screen.

Travellers are part of tavern breathing:

- They are visible in the tavern scene.
- They contribute to low-frequency life feeling.
- They should not become noisy or high-interference.
- They should not introduce MMO-style free movement or visual spam.

Recorded tavern life examples include:

- Occasional drinking.
- Distant chatting.
- Minor exchange events.
- Small tavern incidents.
- Traveller idle movement.
- Bard placeholder performances.

---

## 3. Traveller System Direction

Formal current direction from GAME_CURRENT_VERSION:

- Traveller recruitment is a formal tavern function.
- Travellers refresh by time period:
  - Day
  - Dusk
  - Night
- Traveller professions are not bound to refresh periods.
- A recruited traveller leaves the traveller area.
- A passerby NPC fills the resulting visual vacancy.
- Hub Tavern contains Upper / Lower traveller areas.
- Early / prerequisite professions should have higher appearance weight so players can reliably find class-advancement prerequisites.
- Hidden-profession appearances should not make prerequisite professions hard to encounter.
- Traveller appearance should not be forcibly chapter-locked in a way that can block player progress.

The current files do not define final recruitment cost, recruit stat rules, exact profession tables, rarity, or long-term roster management. Do not invent them.

---

## 4. Appearance Weight And Progress Safety

Current direction:

- Initial / prerequisite professions appear with higher weight than rare or hidden professions.
- Hidden professions may appear, but their appearance must not crowd out required prerequisite professions.
- Traveller appearance is not force-bound to chapters when that would make progression dependent on reaching a specific chapter first.
- The goal is to avoid players being unable to find the pre-advancement role they need.

Boundaries:

- This document does not implement recruitment logic.
- This document does not add characters.
- This document does not change the class tree.
- This document does not define exact spawn percentages.
- This document does not define hidden profession unlock rules.

---

## 5. Visual / Presentation Direction

Recorded implementation direction:

- Traveller display placeholders exist without free movement controls.
- TavernMainScene added subtle traveller idle movement.
- Tavern v2 / v3 notes include upper and lower traveller areas.
- Hub Tavern v2.2 prototype keeps traveller areas as tavern hotspots / placement validation only.

Presentation rules:

- Travellers should be calm tavern life, not an action system.
- Use low-interference scene-based presentation.
- Avoid large menu-button lobby presentation.
- Avoid town-screen replacement.
- Avoid free roaming / MMORPG behavior.

---

## 6. Current Runtime / Prototype State

Recorded scenes and state:

- `res://scenes/HubTavernPrototype.tscn` is the current project startup scene after Safe Merge Stage 1.
- `res://scenes/TavernMainScene.tscn` is retained unchanged as existing / rollback tavern implementation.
- Hub Tavern v2.2 prototype has traveller upper / lower hotspot areas for placement validation.
- Older TavernMainScene work included traveller placeholders and traveller idle motion.

Important boundary:

- Hub Tavern v2.2 / World Map safe merge did not add expedition logic, combat behavior, or worldbuilding changes.
- Traveller hotspot presentation is not final recruitment logic.

---

## 7. Bard And Information Relationship

The bard is adjacent to, but distinct from, the traveller system.

Formal bard communication includes:

- Rumors.
- Boss rumors.
- Black market clues.
- Market hints.
- World-event hints.
- Implicit tutorials.
- Small amounts of lyrics.

Bard content updates approximately every 2 to 3 hours.

Do not merge bard rules into traveller recruitment unless explicitly requested.

---

## 8. Tavern Events Relationship

Formal tavern events include:

- Drunken event.
- Argument event.
- Bard event.
- Injured event.
- Theft event.
- World information event.

These events support tavern breathing and world feel. Current sources do not define final traveller-specific event mechanics. Do not invent event resolution, rewards, penalties, or recruitment effects.

---

## 9. Current Non-Implemented / Placeholder Areas

The following are not finalized in the specified current sources:

- Traveller recruitment UI flow.
- Recruitment cost.
- Recruitment success / failure rules.
- Traveller profession table.
- Traveller rarity.
- Exact traveller appearance weights.
- Hidden profession appearance rules.
- Traveller stat generation.
- Traveller personality generation.
- Traveller departure timing beyond the formal `recruited traveller leaves the traveller area` rule.
- Passerby NPC identity rules.
- Traveller-linked economy.
- Traveller-linked combat abilities.
- Traveller-linked expedition events.

Do not fill these gaps without explicit instruction.

---

## 10. Protection Rules

Do not modify or infer:

- Existing lore.
- Existing monster names or drops.
- Traveller personalities if later official lore exists.
- World roles or established positioning.
- Combat systems.
- Expedition logic.
- Market / black market systems.
- Tavern final art.

When uncertain, preserve the locked project priorities:

```text
readability
comfort
travel atmosphere
low-interference tavern life
```

---

## 11. Recovery Notes

After context loss, future work should treat this document as a summary of current traveller direction, but still defer to the specified source files and any later explicit user instruction.

This document is not permission to implement traveller recruitment. It only preserves the current formal direction and boundaries.


