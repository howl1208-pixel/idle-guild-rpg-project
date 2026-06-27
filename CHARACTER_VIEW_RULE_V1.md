# CHARACTER_VIEW_RULE_V1

Version: v1
Status: Review Draft

Purpose:

定義角色在戰場中的正式視角、Facing、Boss 規則、飛行單位規則與 Corridor Battlefield 呈現規則。

本文件屬於 Character Visual System。

本文件不修改：

- Combat System
- Targeting System
- Skill Queue
- Damage Formula
- Class Tree

---

## Chapter 01｜Battlefield View Rule

正式戰場視角：

3/4 View

禁止：

- 正側面 Side View
- 等角視角 Isometric
- 俯視戰場
- 前後排戰場

目的：

提高手機直式 RPG 可讀性。

---

## Chapter 02｜Player Facing Rule

玩家角色 Facing：

↗

Player Visible Angle：

Right Rear 45°

玩家主要可見：

- 右肩
- 右手武器
- 部分背部
- 部分正面

目的：

保留：

- 武器輪廓
- 披風輪廓
- 盾牌輪廓
- 文明辨識

---

## Chapter 03｜Enemy Facing Rule

敵方角色 Facing：

↙

Enemy Visible Angle：

Left Rear 45°

敵方主要可見：

- 左肩
- 左手武器
- 部分背部
- 部分正面

目的：

形成正式對峙感。

---

## Chapter 04｜Boss Facing Rule

Boss 不採用普通怪 Facing。

Boss 使用：

3/4 Front View

Boss Priority：

1. Threat Readability
2. Visual Identity
3. Skill Readability

玩家應優先看見：

- 頭部
- 胸口
- 核心武器
- Boss 特徵

禁止：

- 完全側面 Boss
- 完全背面 Boss

---

## Chapter 05｜Flying Enemy Rule

Flying Enemy：

Combat Focus Zone Above

不使用：

Enemy Formation Area

用途：

- 飛龍
- 裂風獅鷲
- 鳳凰
- 浮空魔物

Ground Enemy：

Enemy Formation Area

Flying Enemy 必須與 Ground Enemy 保持視覺分層。

---

## Chapter 06｜Knight Civilization Rule

Horse 為文明輪廓。

Horse 不等於強制騎乘。

Closed Beta Direction：

Character
+
Horse Companion Silhouette

戰馬可位於：

- 角色後方
- 角色側後方

目的：

保留騎士文明辨識。

避免：

- 遮擋角色輪廓
- 遮擋盾牌輪廓
- 遮擋武器輪廓

---

## Chapter 07｜Corridor Battlefield Rule

正式戰場結構：

Player Area

↓

Combat Focus Zone

↓

Enemy Area

正式對峙軸：

Left Bottom

↓

Right Top

Player Facing：

↗

Enemy Facing：

↙

Boss：

3/4 Front View

Combat Focus Zone：

保持水平。

禁止傾斜。

---

## Audit Notes

本文件為 Character View Rule Review Draft。

後續若納入正式 Source Of Truth，需再同步：

- SOURCE_OF_TRUTH_INDEX.md
- Character Visual System 文件索引
- 角色 Sprite / Silhouette 製作規格

本次不修改 Godot 場景、不修改 BattleScene、不修改戰鬥系統。