# AI Archetype Rules v1

## Core Concept

Combat AI should be based on combat archetypes, not fixed class names.

Each class/job can later assign an `ai_type`.

Examples:

- guardian
- assassin
- ranger
- mage
- priest
- support
- debuffer
- summoner
- boss

AI behavior should use weighted logic instead of 100% deterministic targeting.

Default recommendation:

- 70% preferred behavior
- 30% fallback behavior

Goal:

- AI should feel intelligent but not perfectly predictable.

---

## Global AI Rules

- Avoid excessive target switching.
- Avoid perfectly deterministic AI.
- If preferred targets do not exist, use normal valid targets.
- AI decisions should remain readable.
- Boss AI should feel intentional but not unfair.
- Respect airborne targeting rules.
- Respect summon aggro rules.

---

## Guardian Archetype

Role:

- Tank / protector / frontline stabilizer.

Behavior:

- Prefer enemies attacking allies.
- Prefer enemies pressuring low HP allies.
- Maintain stable target focus.

Target Weight:

- 70% preferred targets.
- 30% normal targets.

Behavior Notes:

- Guardian should feel stable.
- Guardian should not constantly switch targets.

---

## Assassin Archetype

Role:

- Execution / poison / weakened target hunter.

Behavior:

- Prefer low HP enemies.
- Prefer poisoned enemies.
- Prefer enemies affected by wound or erosion.

Target Weight:

- 70% preferred targets.
- 30% normal targets.

Behavior Notes:

- Assassin may switch targets more often.
- Assassin should feel opportunistic.

---

## Ranger Archetype

Role:

- Ranged attacker / anti-air / precision attacker.

Behavior:

- Prefer flying enemies.
- Prefer weakened enemies.
- Prefer targets melee units cannot reach.

Target Weight:

- 70% preferred targets.
- 30% normal targets.

Behavior Notes:

- Ranger should help control airborne pressure.

---

## Mage Archetype

Role:

- Area damage / battlefield control / magic pressure.

Behavior:

- Prefer grouped enemies.
- Prefer targets vulnerable to status effects.
- Prefer targets without existing matching debuffs.

Examples:

- Fire prefers enemies without Burn.
- Ice prefers enemies without Freeze.
- Lightning prefers enemies without Magic Defense Down.
- Arcane prefers enemies without Erosion.

Target Weight:

- 70% preferred targets.
- 30% normal targets.

Behavior Notes:

- Mage should maximize battlefield value.

---

## Priest Archetype

Role:

- Healing / cleansing / defensive support.

Behavior:

- Heal lowest HP ally.
- Prefer allies under dangerous pressure.
- Prefer cleansing dangerous debuffs.

Target Weight:

- 70% preferred targets.
- 30% fallback targets.

Behavior Notes:

- Priest should avoid unnecessary overhealing.

---

## Support Archetype

Role:

- Buff support / team rhythm control.

Behavior:

- Prefer applying missing buffs.
- Prefer supporting multiple allies.
- Prioritize team stability.

Target Weight:

- 70% preferred actions.
- 30% fallback actions.

Behavior Notes:

- Support should not behave like pure healer.

---

## Debuffer Archetype

Role:

- Enemy weakening / tactical disruption.

Behavior:

- Prefer enemies without intended debuffs.
- Prefer high threat enemies.
- Prefer enemies affected by erosion.

Target Weight:

- 70% preferred targets.
- 30% normal targets.

Behavior Notes:

- Avoid wasting repeated debuffs.

---

## Summoner Archetype

Role:

- Battlefield extension / summon pressure.

Behavior:

- Maintain summon presence.
- Resummon only if summon is dead.
- Support battlefield pressure with summon units.

Target Weight:

- 70% summon logic.
- 30% fallback actions.

Summon Rules:

- Max 1 summon per summoner.
- Summons disappear on death only.
- Summons use fixed medium-low aggro.
- Summons do not inherit owner aggro.

---

## Boss Archetype

Role:

- Encounter identity / pressure source.

Behavior:

- Use readable skill timing.
- Use weighted skill logic.
- Avoid unfair spam behavior.

Behavior Notes:

- Boss should feel dangerous but understandable.
- Boss should not permanently focus summons.

---

## Development Guardrails

Codex must not:

- Create new classes automatically.
- Modify advancement routes.
- Ignore `battle_rules_v1.md`.
- Ignore `status_system_rules.md`.
- Ignore `combat_tempo_rules.md`.
- Create perfectly deterministic AI unless explicitly requested.
