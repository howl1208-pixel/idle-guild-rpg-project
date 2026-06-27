# Status System Rules v1

## Core Philosophy

- Status effects are a core combat mechanic.
- Combat should focus on Buff/Debuff interaction, battlefield control, readable combat flow, and tactical timing.
- Avoid excessive visual clutter.
- Status effects must remain readable on mobile screens.

---

## Core System Rules

Every status effect must support:

- `apply()`
- `refresh()`
- `remove()`
- `tick()`
- `icon_update()`

Each status should contain:

- `id`
- `type`
- `duration`
- `source`
- `stackable`
- `icon`
- `priority`
- `effect_category`

---

## Buff Rules

### Attack Up

- Increase damage dealt.

### Defense Up

- Reduce incoming damage.

### Agility Up

- Faster action cycle or cooldown speed.

### Accuracy Up

- Increase hit chance.

### Critical Rate Up

- Increase critical hit chance.

### Critical Damage Up

- Increase critical damage multiplier.

### Magic Defense Up

- Reduce incoming magic damage.

### Shield

- Absorbs damage before HP.

### Resistance

- Reduce Debuff success chance.

### Thorns

- Reflect damage to nearby attackers.

### Lifesteal

- Recover HP based on damage dealt.

### Regeneration

- Heal over time.

### Healing Blessing

- Increase healing received.

### Purify

- Remove Debuffs.

---

## Debuff Rules

### Excluded Statuses

- Knockback is not part of the status system.
- No Buff, Debuff, or control effect may forcibly displace a unit from its battlefield position.

### Attack Down

- Reduce damage dealt.

### Defense Down

- Increase incoming damage.

### Slow

- Slower action cycle or cooldown speed.

### Accuracy Down

- Reduce hit chance.

### Poison

- Low damage DOT.
- Long duration.

### Bleed

- Extra damage when taking hits.

### Burn

- High damage DOT.
- Shorter duration.

### Frostbite

- Low damage cold DOT.

### Magic Defense Down

- Increase incoming magic damage.

### Freeze

- Cannot attack or cast skills.
- Highest control priority.

### Root

- Cannot perform normal attacks.

### Sleep

- Cannot act.
- Removed after taking damage.

### Wound

- Healing received reduced by 50%.

### Erosion

- Reduce Resistance value.

---

## DOT Rules

DOT effects should:

- Remain visually quiet.
- Avoid excessive floating numbers.
- Prioritize readability.

Burn:

- May use small flame flash.

Poison:

- Minimal visual effect.

Frostbite:

- Small cold visual effect.

---

## Crowd Control Rules

- Crowd control should not permanently lock units.
- Freeze duration should remain short.
- Sleep breaks on damage.
- Boss units may have partial resistance to control effects.

---

## Resistance Rules

### Resistance

- Lowers Debuff application chance.

### Erosion

- Reduces Resistance effectiveness.
- Resistance and Erosion should interact dynamically.

---

## Buff Display Rules

### UI Rules

- Buff icons appear beside units.
- Buff icons must not cover unit heads.
- Buff/Debuff display must remain mobile readable.

### Overflow Rules

- If status count exceeds display limit, collapse icons and use compact mode.

---

## Visual Priority Rules

Highest visual priority:

1. Freeze.
2. Boss skills.
3. Legendary skills.
4. Death.
5. Major Buff activation.

DOT effects should remain lower priority.

---

## Technical Rules

Status effects should support:

- Duration refresh.
- Non-stackable mode.
- Stackable mode.
- Overwrite priority.
- Immunity checks.

---

## Combat Readability Rules

Avoid:

- Excessive screen shake.
- Large constant particle spam.
- MMO-style clutter.

Combat should feel:

- Readable.
- Atmospheric.
- Tactical.
- Alive.

Combat should not feel:

- Chaotic.
- Noisy.
- Overloaded.
