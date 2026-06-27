# Combat Prototype Phase 2 Cleanup Notes

Status: CURRENT ACCEPTANCE NOTE
Rules Source: `../combat_system_current.md`
Scope: Cleanup and deterministic acceptance only

---

## Purpose

This document records Phase 2 cleanup state without changing formal combat rules.

Phase 2 validates:

- Global Skill Queue
- Global Normal Attack Beat
- Skill Focus Slow
- Skill Queue placeholder UI
- Battle log / startup stability
- Deterministic 4 player vs 6 enemy acceptance setup

It does not add new combat features or tune combat tempo values.

---

## Deterministic 4v6 Acceptance Path

Use the BattleScene CLI flag:

```text
--phase2-4v6-acceptance
```

Behavior when enabled:

- Fixed random seed for repeatability.
- Encounter type is forced to normal travel.
- Enemy count is forced to 6.
- Player summon and enemy summon slots are disabled for the acceptance run.
- The battle log records the fixed 4 player vs 6 enemy setup.

This flag is for local validation only and is not part of formal gameplay.

---

## Combo Exception Rule

Status: DESIGN LOCKED / NOT IMPLEMENTED

Formal rule:

- Combo / follow-up / double-strike effects may only be implemented later as additional hits inside one Attack Package.
- They must not reset or bypass Global Normal Attack Beat.

Current implementation state:

- No combo, follow-up, or double-strike system exists in the combat prototype.
- Because the feature is not implemented, Phase 2 acceptance should not fail solely because combo package execution is absent.
- If implemented in a later phase, it must be tested as one normal attack package with no extra global beat reset.

---

## Protected Scope

Do not change during this cleanup pass:

- `combat_system_current.md`
- Combat pacing values
- Damage values
- Monster HP
- Skill cooldown targets
- Travel atmosphere
- Portrait layout
- Low-fatigue combat direction
