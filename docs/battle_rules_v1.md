# Battle Rules v1

## Core Battle Concept

- Battle uses real-time auto combat.
- Base normal attack rhythm follows class and agility rhythm; skill cooldown is not affected by agility.
- The game does not use front-row/back-row systems.
- All units exist on the same battlefield layer.
- Combat focuses on class identity, skill timing, Buff/Debuff interaction, and battlefield pressure.
- Hit reactions must not displace units from their standing positions.
- Knockback is not a supported status or battle-control effect.

---

## Battlefield Rules

### Player Side

- Maximum: 4 player units + 1 summon.

### Enemy Side

- Maximum: 6 enemy units.

### Summons

- Summons are semi-independent units.
- Summons disappear after death.
- Summons do not expire by timer.

---

## Airborne Rules

- Flying enemies can only be hit by ranged attacks and magic attacks.
- Melee normal attacks cannot hit flying enemies.
- Flying enemies do not appear in Chapter 1 routes and begin appearing progressively after Chapter 2.
- Flying enemies should visually float above the battlefield.
- Flying enemies use a compact flying indicator icon.
- Mobile readability takes priority over large airborne effects.

---

## Aggro Rules

### Tank Classes

- Guardian classes generate higher aggro.

### Summons

- Summons use fixed medium-low aggro.
- Summons do not inherit caster aggro.
- Bosses should not permanently target summons.

---

## Combat Speed Rules

- Active skills should usually occur approximately every 16 to 24 seconds.
- Boss skills should usually occur approximately every 24 to 36 seconds.
- Skills enter Global Skill Queue by ready time and are read one at a time.
- During skill focus, ordinary action timers advance at approximately 50% speed; this is Slow State, not Freeze.
- Only one major skill presentation should take visual focus at a time.
- Combat uses semi turn-based focus timing on a real-time timeline: background combat continues while important events take focus one at a time.
- Focus events follow `Combat Focus System v1 (FINAL)`: Focus Window 1.8 to 3 seconds, Focus Gap 1.4 to 3 seconds.
- Boss actions must remain readable, but combat must not become cinematic, traditional full-stop turn-based, or whole-battlefield frozen.
- Normal attacks are background rhythm and do not enter Focus Queue.
- Encounter transitions should preserve a seamless 0.5 to 1 second travel rhythm.
- Avoid excessive animation spam.
- Avoid chain crowd-control lock.
- Battle readability is highest priority.

---

## UI Rules

- Battlefield should remain visually clean.
- Combat log is secondary information.
- Buff/Debuff icons should not cover characters.
- Background should keep subtle motion feeling.

---

## Damage Philosophy

- Low-number RPG design.
- Avoid inflated damage values.

### Early Game Example

- Normal attack: 20 to 60.
- Skill damage: 50 to 120.
- Boss skills: 80 to 180.

### Late Game Goal

- Damage numbers should usually remain under 1000 to 5000.

---

## Character Design Philosophy

- No paper-doll equipment system.
- Character appearance changes mainly through job advancement.
- Weapons represent class culture and identity.

---

## Combat Feeling Goals

Battle should feel:

- Readable.
- Atmospheric.
- Strategic.
- Alive.

Battle should not feel:

- Chaotic.
- Flashy spam.
- MMO-style clutter.
