# material_usage_master_database.md

Status: CURRENT / MATERIAL USAGE MASTER DATABASE
Source Priority: subordinate to `monster_material_master_database.md` and `SCENE_GATHERING_MATERIAL_DATABASE.md` by material type

This file maps existing monster drop materials and approved scene gathering materials to high-level usage categories only.

Formal rules:

- `monster_material_master_database.md` is the only source for monster material names.
- `SCENE_GATHERING_MATERIAL_DATABASE.md` is the source for approved scene gathering material names.
- Do not create new materials in this file.
- Do not modify material names.
- Do not create numerical values.
- Do not create drop rates.
- Do not create recipes.
- If a needed monster material is missing, report: `未存在於 monster_material_master_database.md`.
- If a needed scene material is missing, report: `未存在於 SCENE_GATHERING_MATERIAL_DATABASE.md`.
- Do not self-complete Boss materials.
- Do not infer chapter materials beyond the source database.
- Scene material usage entries do not create recipes, numerical values, drop rates, accessory databases, potion databases, or scroll databases.

Source files checked:

- `monster_material_master_database.md`: read successfully.
- `SCENE_GATHERING_MATERIAL_DATABASE.md`: read successfully for Chapter 01 scene material names.
- `裝備設計.txt`: NOT REQUIRED FOR CURRENT PHASE. This phase only maps material -> source -> usage category, so material source databases are sufficient. Request equipment-design references again when entering `semi_finished_material_database.md`, `recipe_database.md`, or `equipment_database.md` work.

Usage categories:

- Blacksmith
- Workshop
- Accessory
- Semi-Finished Material
- Potion
- Scene Material: Basic Processed Goods
- Scene Material: Potion
- Scene Material: Accessory
- Future Reserved
- Vendor

---

## Chapter 01｜Kingdom Borderlands

| Material | Source Monster | Usage Category |
|---|---|---|
| 狼牙 | 邊境野狼 | Blacksmith: Weapon / Workshop: Accessory, Semi-Finished Material |
| 粗皮革 | 邊境野狼 | Blacksmith / Workshop / Semi-Finished Material |
| 狂狼利牙 | 邊境野狼；狂暴狼人；黑狼王 | Blacksmith: Weapon / Workshop: Accessory |
| 哥布林羽毛 | 哥布林斥侯 | Workshop / Accessory / Vendor |
| 韌藤 | 哥布林斥侯 | Workshop / Semi-Finished Material |
| 粗製石片 | 哥布林斥侯 | Workshop / Semi-Finished Material / Vendor |
| 破損護甲片 | 流亡士兵；重裝流寇 | Blacksmith / Workshop / Semi-Finished Material |
| 生鏽鐵皮 | 流亡士兵 | Blacksmith / Semi-Finished Material |
| 粗布 | 流亡士兵；邊境盜匪 | Workshop / Semi-Finished Material |
| 鐵礦 | 流亡士兵 | Blacksmith / Semi-Finished Material |
| 舊軍牌 | 流亡士兵；邊境掠奪者首領 | Accessory / Vendor |
| 汙染黏液 | 汙染史萊姆 | Potion / Workshop / Semi-Finished Material |
| 魔素碎晶 | 汙染史萊姆 | Potion / Accessory / Workshop |
| 變質膠質 | 汙染史萊姆 | Potion / Workshop / Semi-Finished Material |
| 風乾獸皮 | 荒野野犬 | Blacksmith / Workshop / Semi-Finished Material |
| 野犬尖牙 | 荒野野犬 | Blacksmith: Weapon / Workshop: Accessory, Semi-Finished Material |
| 狂躁犬牙 | 荒野野犬 | Blacksmith: Weapon / Workshop: Accessory |
| 生鏽鐵片 | 邊境盜匪 | Blacksmith / Semi-Finished Material |
| 破舊槍柄 | 邊境盜匪 | Blacksmith / Workshop / Semi-Finished Material |
| 邊境錢袋 | 邊境盜匪；邊境掠奪者首領 | Vendor |
| 重裝鐵片 | 重裝流寇 | Blacksmith / Semi-Finished Material |
| 生鏽重盾碎片 | 重裝流寇 | Blacksmith / Workshop / Semi-Finished Material |
| 流寇軍牌 | 重裝流寇 | Accessory / Vendor |
| 異化獸血 | 狂暴狼人 | Potion / Workshop |
| 狼化皮革 | 狂暴狼人 | Blacksmith / Workshop / Semi-Finished Material |
| 實驗殘片 | 狂暴狼人 | Workshop / Accessory / Vendor |
| 王國軍牌 | 王國逃兵隊長 | Accessory / Vendor |
| 鋼製短矛碎片 | 王國逃兵隊長 | Blacksmith / Semi-Finished Material |
| 警備護甲布 | 王國逃兵隊長 | Blacksmith / Workshop / Semi-Finished Material |
| 機密殘頁 | 王國逃兵隊長 | Workshop / Accessory / Vendor |
| 狼王獸皮 | 黑狼王 | Blacksmith: Armor / Workshop: Accessory, Semi-Finished Material |
| 狼王利爪 | 黑狼王 | Blacksmith: Weapon / Workshop: Accessory |
| 邊境獸核 | 黑狼王 | Accessory / Potion / Workshop |
| 掠奪者護腕 | 邊境掠奪者首領 | Blacksmith: Armor / Workshop: Accessory / Other: Vendor |
| 破損戰刃碎片 | 邊境掠奪者首領 | Blacksmith / Semi-Finished Material |
| 流寇徽記 | 邊境掠奪者首領 | Accessory / Vendor |

---

## Chapter 01 Scene Materials｜Kingdom Borderlands

Status: FINAL
Scope: Chapter 01 Scene Material Usage Positioning

Formal direction:

- Monster materials support the main equipment loop.
- Scene materials support the expedition support loop.
- This section defines material positioning only.
- This section does not create recipes, numerical values, accessory databases, potion databases, or scroll databases.

### Workshop Processing Materials

| Material | Usage Category | Usage Direction |
|---|---|---|
| 廢棄鐵片 | Scene Material: Basic Processed Goods | 鐵錠 |
| 荒廢木材 | Scene Material: Basic Processed Goods | 王國硬木材 |
| 王國舊布料 | Scene Material: Basic Processed Goods | 王國織布 |
| 汙染結晶碎片 | Scene Material: Basic Processed Goods | 邊境魔晶 |

### Potion Materials

| Material | Usage Category | Usage Direction |
|---|---|---|
| 荒野草藥 | Scene Material: Potion | 治療藥劑 |
| 毒沼草 | Scene Material: Potion | 抗毒藥劑 |

### Accessory Materials

| Material | Usage Category | Usage Direction |
|---|---|---|
| 乾燥獸骨 | Scene Material: Accessory | 骨製飾品 |
| 邊境石材 | Scene Material: Accessory | 石製飾品 |

### Future Reserved

| Material | Usage Category | Usage Direction |
|---|---|---|
| 腐化木枝 | Future Reserved | 卷軸系統／特殊消耗品 |

Chapter 01 Beta Scope:

- 基礎加工品：保留。
- 藥劑：保留。
- 飾品：保留。
- 卷軸系統：封測版暫不開放。

Important:

- 腐化木枝不作為 Chapter 01 Beta 正式用途。
- 腐化木枝只保留為卷軸系統／特殊消耗品的 Future Reserved 方向。

---

## Chapter 02

_Reserved. No material usage entries added in this pass._

---

## Chapter 03

_Reserved. No material usage entries added in this pass._

---

## Chapter 04

_Reserved. No material usage entries added in this pass._

---

## Chapter 05

_Reserved. No material usage entries added in this pass._


