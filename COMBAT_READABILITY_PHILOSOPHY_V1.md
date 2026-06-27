# COMBAT_READABILITY_PHILOSOPHY_V1.md

Version: v1
Status: LOCKED DIRECTION
Priority: HIGH
Target: Combat Prototype / Timeline / Animation / FX / Audio / UI
Applies To: All Chapters

---

# Purpose

Combat prototype validation found:

> The core issue is NOT overall combat speed.

The actual issue is:

> Multiple units acting simultaneously reduces combat readability.

Player experience becomes:

```text
I don't know who attacked whom.
Too many things happen at once.
Combat feels noisy instead of readable.
```

This philosophy exists to solve:

```text
Combat readability
Long-session viewing comfort
Auto-battle clarity
Low fatigue gameplay
```

without turning combat into traditional full-stop turn-based gameplay.

---

# Core Philosophy

Combat must follow:

# SEE → UNDERSTAND → PROCESS

(看到 → 理解 → 消化)

This becomes a global combat rule.

Priority:

```text
Readability > Spectacle
Clarity > Chaos
Comfort > Noise
```

The goal is:

> Make combat readable and comfortable to watch for long sessions.

---

# 1. SEE (看到)

The player must first:

> Notice an event is happening.

Questions:

```text
What is happening?
Who is acting?
Where should I look?
```

---

## Requirements

Combat must ensure:

```text
• Clear silhouettes
• Clear attack preparation
• Clear animation start
• Only limited major events at once
• Reduced simultaneous action overlap
```

---

## Allowed

```text
Single major event focus
Micro stagger timing
Clear skill startup
Readable attack motion
```

---

## Forbidden

```text
Multiple major events exploding at once
Heavy FX overlap
Simultaneous attack spam
Unreadable visual stacking
Instant untelegraphed important actions
```

---

## Example

Good:

```text
Boss slowly raises weapon
Ground warning appears
Player immediately notices danger
```

Bad:

```text
Boss skill + ally skill + enemy skill + particles
all explode simultaneously
```

Player reaction:

```text
???
```

---

# 2. UNDERSTAND (理解)

The player must understand:

> Who did what to whom.

Combat must establish:

# Cause → Effect

Flow:

```text
Attacker
→ Attack motion
→ Target hit reaction
→ Damage number
```

Player understanding:

```text
"Oh, the warrior hit the wolf."
"The healer saved the team."
"The boss used a dangerous attack."
```

---

## Required Sequence

Every important action should follow:

```text
1. Actor starts action
2. Motion direction becomes readable
3. Target reacts
4. Damage/heal appears
5. Recovery
```

---

## Good Example

```text
Warrior shield bash
→ wolf staggers backward
→ damage appears
```

Player understands:

```text
Warrior hit wolf
```

---

## Bad Example

```text
Everyone moves
Everyone shakes
Numbers explode everywhere
```

Player understands:

```text
Nothing
```

---

# 3. PROCESS (消化)

The player must have time to:

> Mentally absorb what happened.

This is one of the most important rules.

Combat should NOT feel like:

```text
1 second = 5 important events
```

Combat should feel like:

```text
Event
→ short breathing room
→ next event
```

---

# Combat Beat Rule

Adopt:

# Combat Beats

Meaning:

> Only ONE major readable event should dominate attention at a time.

Major events require breathing room.

---

## Example (Good)

```text
0.0 Warrior shield bash

0.6 Enemy reaction

1.5 Boss warning

2.5 Mage fireball

3.5 Small heal
```

Player experience:

```text
See
Understand
Process
```

---

## Example (Bad)

```text
0.0 Warrior attack
0.1 Boss warning
0.2 Mage spell
0.3 Archer attack
0.4 Heal
0.5 Explosion
```

Player experience:

```text
Visual overload
Unreadable combat
Fatigue
```

---

# Major Event Priority Rule

At any moment:

> Only one major visual focus.

Priority:

```text
Boss Skill
> Elite Skill
> Player Core Skill
> Enemy Skill
> Normal Attack
```

When a higher priority action plays:

```text
Lower priority actions should visually downgrade
or slightly delay.
```

---

# Background Event Rule

Not all actions deserve spotlight.

Background actions:

```text
DOT
Buff ticks
Aura
Minor heal
Small debuff
Minor attacks
```

Should become:

```text
Low animation
Low FX
Low audio
Minimal screen attention
```

Goal:

```text
Do not compete with major events.
```

---

# Information Density Rule

Combat readability is NOT solved by slowing combat.

Combat readability is solved by:

> Controlling information density.

Wrong:

```text
Fast + many important events
```

Also wrong:

```text
Slow + many important events
```

Correct:

```text
Readable density
```

---

# Combat Readability Targets

Codex implementation target:

Combat should allow players to:

```text
See
Understand
Process
```

within comfortable viewing time.

Acceptance criteria:

```text
• Players can roughly tell who attacked whom
• Boss/Elite actions naturally attract attention
• Combat no longer feels noisy
• Long watching sessions feel comfortable
• Combat still feels real-time
• Combat does NOT become traditional full-stop turn-based
```

---

# Design Philosophy

Official direction:

> Combat should not become slower.

Official goal:

> Combat becomes clearer.

Core philosophy:

```text
Less simultaneous chaos
More readable beats
Clear cause and effect
Breathing room between major events
Comfortable long-session viewing
```

---

# Relationship To Existing Systems

This philosophy affects:

```text
Combat Timeline
Animation timing
Skill startup
Hit reaction
Damage number timing
Audio priority
FX density
Combat readability
Boss presentation
```

This philosophy does NOT change:

```text
Combat total pace
Game balance
Damage values
Monster stats
Drop systems
Class design
```

---

# Final Rule

When uncertain:

Ask:

```text
Can the player:

SEE?
UNDERSTAND?
PROCESS?
```

If the answer is:

```text
No
```

Then the combat presentation should be simplified.
