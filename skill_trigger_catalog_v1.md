# skill_trigger_catalog_v1.md

Version: v1
Status: REVIEW
Scope: Combat System

---

## Purpose

建立 Skill Trigger Catalog。

本文件定義：

- 技能允許使用的 Trigger
- 技能禁止使用的 Trigger
- Trigger 使用哲學
- Trigger 與 Combat Focus System 關聯

本文件適用於：

- 玩家技能
- 怪物技能
- 精英怪技能
- Boss 技能
- 召喚技能

---

## Core Philosophy

正式哲學：

```text
Skill Ready
不等於
Skill Cast
```

流程：

```text
Skill Ready
↓
Trigger Check
↓
Global Skill Queue
↓
Cast
```

---

## Allowed Trigger

### SELF_HP_BELOW_X

自身生命低於指定比例。

範例：

- 70%
- 50%
- 30%

用途：

- 狂暴
- 防禦
- 生存

---

### ENEMY_HP_BELOW_X

敵方生命低於指定比例。

範例：

- 70%
- 50%
- 30%

用途：

- 處決
- 追擊
- 補刀

---

### ALLY_HP_BELOW_X

友軍生命低於指定比例。

用途：

- 治療
- 保護
- 團隊支援

---

### OPENING_FIRST_CAST

開場首次符合條件。

用途：

- Boss 登場技
- 威嚇技
- 開場 Buff

限制：

每場戰鬥只觸發一次。

---

### BUFF_MISSING

自身 Buff 不存在。

用途：

- 維持戰鬥姿態
- 維持護盾
- 維持強化

---

### DEBUFF_MISSING

目標 Debuff 不存在。

用途：

- 上毒
- 上燃燒
- 上詛咒

避免重複浪費施法。

---

### SUMMON_NOT_PRESENT

召喚物不存在。

用途：

- 召喚型角色
- 召喚型 Boss

---

### READY_ALWAYS

技能 Ready 後可直接進入 Queue。

用途：

- 純傷害技能
- 基礎 Boss 技能

限制：

不得過度使用。

---

## Forbidden Trigger

目前版本禁止：

### ON_HIT

受到攻擊時。

---

### ON_DODGE

閃避時。

---

### ON_BLOCK

格擋時。

---

### ON_CRIT

暴擊時。

---

### ON_DEATH

死亡時。

---

### EVERY_SECOND_CHECK

固定時間循環觸發。

---

### RANDOM_PROC

隨機機率觸發。

---

## Design Rule

新增 Trigger 必須符合：

- 提升可讀性
- 提升戰術理解
- 降低技能密度

不得僅為增加複雜度而新增 Trigger。

---

## Combat Focus Alignment

Trigger 的目的：

不是增加技能數量。

而是控制：

- 技能出現時機
- 技能密度
- 技能閱讀空間

---

## Final Rule

技能 CD：

代表技能準備完成。

Trigger：

決定技能是否值得施放。

正式哲學：

讓技能因戰況而施放，

而不是因時間到了就施放。