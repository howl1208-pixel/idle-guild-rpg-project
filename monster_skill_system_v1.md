# monster_skill_system_v1.md

Version: v1
Status: REVIEW
Scope: Monster Skill Architecture

---

## Purpose

建立怪物技能系統架構。

本文件只定義：

- 怪物是否具備技能
- 各怪物階級技能數量上限
- 怪物技能如何接入 Combat Focus System
- 怪物召喚能力規則
- 技能設計限制

本文件不定義：

- 各章怪物實際技能名稱
- 技能倍率
- 技能 CD 數值
- Boss 技能資料庫

---

## Core Philosophy

正式哲學：

```text
怪物技能不是越多越好，而是要讓玩家看得懂威脅。
```

怪物技能應建立：

- 怪物辨識度
- 戰鬥節奏變化
- Elite / Boss 記憶點
- 世界觀差異

但不得造成：

- 10 秒後技能洪水
- Queue 爆滿
- 技能特效互打
- 玩家無法理解戰況

---

## Monster Skill Tier Rule

### 普通怪

正式方向：

```text
0 主動技能
```

普通怪主要依靠：

- 普通攻擊
- 外觀辨識
- 行為 Personality
- 掉落素材
- 場景生態感

普通怪不承擔技能教學壓力。

---

### 特殊怪

正式方向：

```text
0 主動技能
```

特殊怪可透過：

- 遠程普攻
- 大型體型
- 飛行
- 高血量
- 高命中
- 特殊目標傾向

建立差異。

暫不加入主動技能，避免技能密度過早升高。

---

### 精英怪

正式方向：

```text
1 主動技能
```

精英怪技能用途：

- 建立精英辨識度
- 提供單一戰術壓力
- 讓玩家理解該怪物危險點

每隻精英怪原則只設計：

```text
1 個核心技能
```

不可堆疊多技能。

---

### Boss

正式方向：

```text
1～2 主動技能
```

Boss 技能用途：

- 建立記憶點
- 建立章節 Boss 特色
- 建立階段感或核心壓力

Boss 不得技能過量。

Boss 技能上限：

```text
最多 2 個主動技能
```

---

## Combat System Integration

怪物技能必須遵守：

- Global Skill Queue
- Skill Focus Slow
- Skill Trigger System v1
- Target Line Rule v2
- Threat Readability
- Status Layering

怪物技能不得繞過 Combat Focus System。

---

## Skill Ready Rule

怪物技能同樣遵守：

```text
Skill Ready ≠ Skill Cast
```

流程：

```text
Skill CD Ready
↓
Check Trigger Condition
↓
Enter Global Skill Queue
↓
Cast
```

---

## Monster Summon Rule

### 普通怪

```text
不具備召喚能力
```

### 特殊怪

```text
原則不具備召喚能力
```

### 精英怪

```text
少數精英怪可具備召喚能力
```

### Boss

```text
可具備召喚能力，但不是每隻 Boss 都必須召喚
```

召喚能力必須符合怪物世界觀。

例如：

- 死靈系 Boss 可召喚亡者
- 狼王類 Boss 不一定召喚
- 巨像型 Boss 不召喚
- 信仰型 Boss 不一定召喚

---

## Summon Slot Rule

怪物召喚物：

```text
使用 Enemy Summon Area
```

不佔用正式敵人 6 格。

召喚物不得破壞 Combat Focus Zone 閱讀性。

---

## Enemy Count Rule

普通遭遇：

```text
3～6 敵
```

精英遭遇：

```text
原則不超過 5 敵
```

Boss 遭遇：

```text
原則不超過 5 敵
```

原因：

- 保留召喚物空間
- 保留 Combat Focus Zone
- 避免單位數與技能數同時過密

---

## Skill Category

怪物技能可分為：

- Single Target Damage
- AoE Damage
- Debuff
- Buff
- Execute
- Summon
- Control
- Heavy Warning Attack

---

## Skill Design Restriction

怪物技能不得：

- 高頻連續施放
- 大量堆疊 Debuff
- 長時間控場
- 多技能同時爆發
- 造成不可閱讀的技能潮
- 讓普通怪像精英怪
- 讓精英怪像 Boss

---

## Chapter Direction

### Chapter 01

低複雜度。

- 普通怪：0技能
- 特殊怪：0技能
- 精英怪：1技能
- Boss：1～2技能

第一章避免：

- 大量召喚
- 多段控制
- 高頻 AoE
- 複雜連鎖

---

### Chapter 02+

可逐步加入：

- 飛行威脅
- 遠程壓制
- 召喚型 Boss
- Debuff 壓力
- 大型預警技能

但仍必須維持可閱讀性。

---

## Final Rule

怪物技能不是為了增加特效數量。

而是為了讓玩家理解：

```text
這隻怪物為什麼危險。
```