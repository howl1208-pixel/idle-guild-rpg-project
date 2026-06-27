# CHAPTER04_MONSTER_DATABASE.md

Version: v1
Status: Review Draft
Chapter: Chapter 04 - Desert Ruined City
Phase: Closed Beta Consolidation Phase
Scope: Monster Database Consolidation Only

---

## Document Rules

- Do not create new monsters.
- Do not create new civilizations.
- Do not create new classes.
- Do not create new chapters.
- Do not create Chapter 06+ content.
- Do not create new skills.
- Character System = Locked.
- Weapon System = Locked.
- Monster Bible System = Locked.
- This document consolidates existing Chapter 04 monster sources only.
- Missing data is marked as `SOURCE MISSING`.
- Drop Quantity is not recorded in this Monster Database.
- Drop rate is not recorded in this Monster Database.
- Drop weight is not recorded in this Monster Database.
- Drop numerical values are not recorded in this Monster Database.
- Drop materials must come from `monster_material_master_database.md`.

---

## Source Priority

1. `AGENTS.md`
2. `GAME_CURRENT_VERSION.md`
3. `CURRENT_PROJECT_STATE.md`
4. `combat_system_current.md`
5. `CLASS_TREE_CURRENT.md`
6. `monster_database.md`
7. `archive/chapter04_monster_lore.docx`
8. `archive/chapter04_monster_silhouette_260606_145841.docx`
9. `C:/Users/User/Documents/Codex/2026-06-01/new-chat/MONSTER_SILHOUETTE_BIBLE.md`
10. `C:/Users/User/Documents/Codex/2026-06-01/new-chat/MONSTER_CIVILIZATION_BIBLE.md`
11. `C:/Users/User/Documents/Codex/2026-06-01/new-chat/MONSTER_ANIMATION_BIBLE.md`
12. `C:/Users/User/Documents/Codex/2026-06-01/new-chat/MONSTER_COLOR_BIBLE.md`
13. `monster_material_master_database.md`
14. `material_usage_master_database.md`

---

## Source Index

| Data Type | Source | Integration Rule |
|---|---|---|
| Monster Names | `monster_database.md`; `MONSTER_SILHOUETTE_BIBLE.md`; `archive/chapter04_monster_silhouette_260606_145841.docx` | Use listed Chapter 04 monster names only |
| Lore | `archive/chapter04_monster_lore.docx` | Consolidate only; preserve source conflicts as review notes |
| Silhouette | `MONSTER_SILHOUETTE_BIBLE.md`; `archive/chapter04_monster_silhouette_260606_145841.docx` | Use approved silhouette Bible reference and Chapter 04 source row |
| Color | `MONSTER_COLOR_BIBLE.md`; `MONSTER_SILHOUETTE_BIBLE.md` | Use approved color Bible rule plus source color direction |
| Animation | `MONSTER_ANIMATION_BIBLE.md`; `archive/chapter04_monster_lore.docx`; `archive/chapter04_monster_silhouette_260606_145841.docx` | Use approved animation Bible rule plus source animation text |
| Civilization | `MONSTER_CIVILIZATION_BIBLE.md` | Use Chapter 04 civilization mapping where directly listed |
| Drops | `monster_material_master_database.md` | Material names only; no quantity, drop rate, weight, or numerical value |
| Threat Level | `MONSTER_SILHOUETTE_BIBLE.md`; `archive/chapter04_monster_silhouette_260606_145841.docx` | Normal / Elite / Boss only |
| Region Distribution | Source text only | Do not add regions |

---

## Chapter Overview

- Chapter: Chapter 04
- Region: 沙漠遺城 / Desert Ruined City
- Closed Beta Scope: Chapter 01~05 only
- Encounter System: weighted random encounters
- Boss Encounter System: weighted accumulated encounter
- Fixed Boss Stage: No
- Chapter 06+ Handling: Out of scope
- Chapter Core: 文明遺跡; 古代守護者; 重量感; 巨像壓迫; 失落王朝; 預警判讀

---

## Chapter 04 Region Distribution Matrix

This matrix uses only region / location wording present in approved sources.

| Source Region Text | Monsters Referenced | Notes |
|---|---|---|
| 沙漠遺城 | 沙行角獸; 沙塵掠食者; 遺跡殘兵; 石像巡守者; 地宮爬獸; 王墓石衛; 沙海屠夫・拉格爾; 古城守衛長・托爾曼; 王墓巨像・卡姆拉; 沙海巨像・阿圖姆 | Chapter-wide source region |
| 黃金沙海 | 沙行角獸; 沙塵掠食者; 沙海屠夫・拉格爾 | From lore source |
| 古代商道與風蝕沙丘周圍 | 沙行角獸 | From lore source |
| 沙層與風蝕岩影之間 | 沙塵掠食者 | From lore source |
| 遺跡外城 | 遺跡殘兵; 石像巡守者; 古城守衛長・托爾曼 | From lore source |
| 王墓地宮 | 地宮爬獸; 王墓石衛; 王墓巨像・卡姆拉; 沙海巨像・阿圖姆 | From lore source |
| 墓道陰影與石柱裂縫 | 地宮爬獸 | From lore source |
| 巨門與王族墓區周邊 | 王墓石衛 | From lore source |
| 古城入口 | 古城守衛長・托爾曼 | From lore source |
| 王墓地宮核心區域 | 王墓巨像・卡姆拉 | From lore source |
| 王墓地宮深處 | 沙海巨像・阿圖姆 | From lore source |

---

## Chapter 04 Monster Master Table

| Monster ID | Monster Name | Source Type | Threat Level | Region Distribution | Civilization |
|---|---|---|---|---|---|
| MON_CH04_NORMAL_001 | 沙行角獸 / Sand Hornbeast | Normal | Normal | 黃金沙海; 古代商道與風蝕沙丘周圍 | Desert Beast Civilization |
| MON_CH04_NORMAL_002 | 沙塵掠食者 / Dust Predator | Normal | Normal | 黃金沙海; 沙層與風蝕岩影之間 | Desert Beast Civilization |
| MON_CH04_NORMAL_003 | 遺跡殘兵 / Ruined Soldier | Normal | Normal | 遺跡外城 | Ruin Soldier Civilization |
| MON_CH04_NORMAL_004 | 石像巡守者 / Statue Patroller | Normal | Normal | 遺跡外城 | Stone Guardian Civilization |
| MON_CH04_NORMAL_005 | 地宮爬獸 / Crypt Crawler | Normal | Normal | 王墓地宮; 墓道陰影與石柱裂縫 | Desert Beast Civilization |
| MON_CH04_ELITE_001 | 王墓石衛 / Royal Tomb Stoneguard | Elite | Elite | 王墓地宮; 巨門與王族墓區周邊 | Stone Guardian Civilization; Royal Tomb Guardian Civilization |
| MON_CH04_ELITE_002 | 沙海屠夫・拉格爾 / Ragel, Butcher of the Sandsea | Elite | Elite | 黃金沙海 | Desert Executioner Civilization |
| MON_CH04_ELITE_003 | 古城守衛長・托爾曼 / Torlman, Warden of the Ruins | Elite | Elite | 遺跡外城; 古城入口 | Ruin Soldier Civilization |
| MON_CH04_BOSS_001 | 王墓巨像・卡姆拉 / Kamra, Colossus of the Royal Tomb | Boss | Boss | 王墓地宮核心區域 | Royal Tomb Guardian Civilization; Ancient Colossus Civilization |
| MON_CH04_BOSS_002 | 沙海巨像・阿圖姆 / Atum, Colossus of the Sandsea | Boss | Boss | 王墓地宮深處 | Ancient Colossus Civilization |

---

## Normal Monsters

### MON_CH04_NORMAL_001 - 沙行角獸 / Sand Hornbeast

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 黃金沙海; 古代商道與風蝕沙丘周圍
- Civilization: Desert Beast Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 沙行角獸.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Desert Beast Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 角獸類; Idle Rule > 野獸; Attack Rule > 衝撞; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 荒漠野獸.

#### Lore

- World Position: 黃金沙海中的高速掠食獸，長期棲息於古代商道與風蝕沙丘周圍，會追蹤迷失旅人與落單坐騎。
- Personality: 警戒、耐心、具追獵本能，會遠距離觀察旅人隊伍，等待落單與疲憊獵物後高速突襲。
- Entry Feeling: 從沙丘後快速衝入場中，低頭刨沙後抬起頭鎖定目標，前肢略微壓低像準備衝刺。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 厚重角質頭部、彎曲長角。
- Weapon Recognition: 巨角衝撞。
- Body Shape: 中大型四足獸。
- Posture: 低頭蓄力、重心前傾。
- Visual Outline: 體型略大於狼，身形修長，前肢粗壯有力，後肢偏長，背部與肩部覆蓋風蝕般硬質甲片，尾部細長，整體輪廓像羚羊與掠食獸混合的異獸。

#### Color

- Source Color Direction: 沙黃、岩石棕、深灰角質。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 荒漠野獸.

#### Animation

- Dynamic Recognition: 衝撞、刨地、重踏。
- Combat Style: 高速近戰壓力怪，以低頭衝撞與近距離撕咬進攻，節奏輕快但具有威脅感。
- Idle: 小幅喘息與呼吸起伏，前蹄偶爾刨沙，耳部與尾巴微動，始終維持警戒。
- Death: 衝刺姿態失衡後向側翻倒，角部先落地，身體滑行一小段距離後停止。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 古商隊皮革 | `monster_material_master_database.md` |  |
| 砂角碎片 | `monster_material_master_database.md` |  |
| 風蝕獸骨 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: none for reference layer

---

### MON_CH04_NORMAL_002 - 沙塵掠食者 / Dust Predator

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 黃金沙海; 沙層與風蝕岩影之間
- Civilization: Desert Beast Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 沙塵掠食者.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Desert Beast Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 爬行類; Idle Rule > 野獸; Attack Rule > 撲咬; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 荒漠野獸.

#### Lore

- World Position: 黃金沙海中的高傷害掠食怪，擅長埋伏於沙層與風蝕岩影之間。
- Personality: 安靜、耐心、爆發性強，偏好埋伏與瞬間撲殺，對震動極為敏感。
- Entry Feeling: 地面先微微鼓起，沙塵突然炸開後迅速現身，尾鉤向上甩動準備攻擊。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 細長掠食頭部、尖牙。
- Weapon Recognition: 利爪與撕咬。
- Body Shape: 中型敏捷野獸。
- Posture: 壓低身體、準備飛撲。
- Visual Outline: 低重心爬行獸，身體覆有沙色硬甲，頭部扁平，口器寬大，尾端帶刃狀尾鉤，整體輪廓偏向古沙漠伏擊型獵食者。

#### Color

- Source Color Direction: 沙黃、褐色斑紋、灰棕。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 荒漠野獸.

#### Animation

- Dynamic Recognition: 快速奔跑、飛撲。
- Combat Style: 高傷害單體壓力怪，以沙塵突襲造成高傷害，攻擊前帶有短暫預備動作與可閱讀性。
- Idle: 身體壓低貼近地面，尾鉤緩慢左右擺動，偶爾甩落沙粒。
- Death: 甲殼碎裂，身體伏地後逐漸被流沙覆蓋。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 風蝕砂晶 | `monster_material_master_database.md` |  |
| 沙刃尾鉤 | `monster_material_master_database.md` |  |
| 風化古幣 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: none for reference layer

---

### MON_CH04_NORMAL_003 - 遺跡殘兵 / Ruined Soldier

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 遺跡外城
- Civilization: Ruin Soldier Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 遺跡殘兵.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Ruin Soldier Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 遺跡守衛系; Idle Rule > 人形; Attack Rule; Death Rule > 人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 遺跡殘兵.

#### Lore

- World Position: 遺跡外城殘留的古代士兵，仍受古文明力量驅使守衛失落城市。
- Personality: 沉默、機械化、執行守衛本能，對踏入古城者展現敵意。
- Entry Feeling: 從半埋沒石牆與陰影中緩慢現身，武器拖行地面揚起細沙。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 殘破頭盔、古代士兵輪廓。
- Weapon Recognition: 破損長劍。
- Body Shape: 中型人形。
- Posture: 挺立巡守姿態。
- Visual Outline: 半人形古代士兵，穿著破損砂岩鎧甲與鏽蝕金屬片，面部被殘缺頭盔覆蓋，手持殘破長矛或古代短刃。

#### Color

- Source Color Direction: 石灰、鐵灰、沙塵黃。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 遺跡殘兵.

#### Animation

- Dynamic Recognition: 穩定步行、揮砍。
- Combat Style: 穩定近戰怪，以簡單直接攻擊維持壓力，節奏沉穩。
- Idle: 姿態僵硬，身體偶爾因殘存能量輕微震動，眼部裂縫透出微弱光芒。
- Death: 支撐失效，鎧甲碎裂，身體化為古代殘骸散落。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 王國殘鐵 | `monster_material_master_database.md` |  |
| 殘破軍徽 | `monster_material_master_database.md` |  |
| 王國石印 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: none for reference layer

---

### MON_CH04_NORMAL_004 - 石像巡守者 / Statue Patroller

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 遺跡外城
- Civilization: Stone Guardian Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 石像巡守者.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Stone Guardian Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Idle Rule > 石像／巨像; Attack Rule > 巨像重擊; Death Rule > 石像／巨像.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 石像守衛.

#### Lore

- World Position: 遺跡外城仍在巡守的古代石像守衛，負責驅逐外來入侵者。
- Personality: 沉默、遲緩、毫無情緒，如同執行古代命令般持續巡守。
- Entry Feeling: 原本如背景雕像般靜止，眼部符文亮起後，石體震落細砂開始活動。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 石雕面孔、發光符文眼。
- Weapon Recognition: 石拳。
- Body Shape: 大型石像人形。
- Posture: 穩定站立、守衛姿態。
- Visual Outline: 大型砂岩石像，肩膀厚重，雙臂粗壯，身體刻有風蝕紋路與古代王朝符文。

#### Color

- Source Color Direction: 岩石灰、風化黃、符文藍。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 石像守衛.

#### Animation

- Dynamic Recognition: 重踏、重拳。
- Combat Style: 高耐久大型怪，以石拳重擊造成小範圍壓力，出手前有清楚抬臂預警。
- Idle: 石體極慢震動，肩部砂石不時落下，眼部符文忽明忽暗。
- Death: 符文熄滅，手臂率先崩落，最後全身碎裂成砂岩殘塊。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 古代石片 | `monster_material_master_database.md` |  |
| 石像核心碎塊 | `monster_material_master_database.md` |  |
| 巨像殘片 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: none for reference layer

---

### MON_CH04_NORMAL_005 - 地宮爬獸 / Crypt Crawler

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 王墓地宮; 墓道陰影與石柱裂縫
- Civilization: Desert Beast Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 地宮爬獸.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Desert Beast Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 爬行類; Idle Rule > 野獸; Attack Rule > 撲咬; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 荒漠野獸.

#### Lore

- World Position: 王墓地宮中的高機動掠食怪，潛伏於墓道陰影與石柱裂縫之中。
- Personality: 警戒、迅速、習慣貼牆與陰影移動，對聲響與震動極度敏感。
- Entry Feeling: 從石柱陰影間迅速竄出，停頓瞬間後鎖定獵物。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 扁平爬蟲頭部、地底生物特徵。
- Weapon Recognition: 利爪與啃咬。
- Body Shape: 中大型爬行獸。
- Posture: 貼地潛伏。
- Visual Outline: 細長低伏型異獸，四肢貼地，背部附著古代封泥與碎石，雙眼在黑暗中帶微弱黃光。

#### Color

- Source Color Direction: 土黃、灰褐、岩石色。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 荒漠野獸.

#### Animation

- Dynamic Recognition: 快速竄行、撲擊。
- Combat Style: 高機動干擾怪，快速撲擊與繞行壓迫，不主打 Debuff。
- Idle: 身體低伏，四肢偶爾快速抖動，頭部左右掃視。
- Death: 四肢失力後貼地癱倒，背部封泥與碎石逐漸剝落。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 古代封泥 | `monster_material_master_database.md` |  |
| 地宮利爪 | `monster_material_master_database.md` |  |
| 古王族碎玉 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: none for reference layer
- Source Label Note: extracted lore text repeats a `沙塵掠食者` heading before the content whose world position and drops match 地宮爬獸; this draft maps the block by monster database, silhouette Bible, and material source.

---

## Elite Monsters

### MON_CH04_ELITE_001 - 王墓石衛 / Royal Tomb Stoneguard

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 王墓地宮; 巨門與王族墓區周邊
- Civilization: Stone Guardian Civilization; Royal Tomb Guardian Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 王墓石衛.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Stone Guardian Civilization; Royal Tomb Guardian Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Idle Rule > 石像／巨像; Attack Rule > 巨像重擊; Death Rule > 石像／巨像.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 石像守衛; 王墓守護.

#### Lore

- World Position: 王墓地宮深處的大型守墓者，沉睡於巨門與王族墓區周邊。
- Personality: 莊嚴、沉默、具有守墓者威嚴，只對闖入者做出反應。
- Entry Feeling: 地面微震，石衛從靜止姿態中站起，胸口符印逐漸發亮。
- Party Note: SOURCE MISSING. Source gives no elite party note text.

#### Silhouette

- Head Recognition: 王墓面甲、王族雕紋。
- Weapon Recognition: 巨型石製武器。
- Body Shape: 大型守衛石像.
- Posture: 正面守護姿態。
- Visual Outline: 大型人形石衛，厚重石甲包覆全身，胸口刻有古王徽印，持石槌或大型石盾。

#### Color

- Source Color Direction: 石灰、金黃紋飾。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 石像守衛; 王墓守護.

#### Animation

- Dynamic Recognition: 重踏、巨力揮擊。
- Combat Style: 大型守衛型怪，以守墓踐踏造成小範圍震擊，節奏緩慢但威脅明確。
- Idle: 幾乎靜止，只在極微弱震動中掉落砂塵與石屑。
- Death: 胸口符印破裂，石甲逐段崩塌，最後化成沉重石堆。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 王墓石核 | `monster_material_master_database.md` |  |
| 黃金沙核 | `monster_material_master_database.md` |  |
| 王墓秘石 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Formal Skill Database Entry: SOURCE MISSING.
- Target Line: SOURCE MISSING.
- Source combat wording is preserved as descriptive behavior only; no new skill is created.

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: party note; formal skill database entry; target line
- Material Source Note: lore extraction includes `石衛重甲片` and `古代王徽`; both are `未存在於 monster_material_master_database.md` and are not added.

---

### MON_CH04_ELITE_002 - 沙海屠夫・拉格爾 / Ragel, Butcher of the Sandsea

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 黃金沙海
- Civilization: Desert Executioner Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 沙海屠夫・拉格爾.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Desert Executioner Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Attack Rule > 重武器; Idle Rule > 人形; Death Rule > 重甲人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 沙海處刑.

#### Lore

- World Position: 黃金沙海中的頂級掠食者與商道屠殺者，長期襲擊穿越沙海的旅團與商隊，被倖存者視為沙海中的死神。
- Personality: 冷靜、殘忍、帶有掠食者耐性，不急於出手，而是觀察獵物破綻後再給予致命攻擊。
- Entry Feeling: 站在沙丘高處背對旅團，伴隨風沙緩慢回頭，拖著重刃一步步走下，刀鋒在地面留下深刻拖痕。
- Party Note: 「商隊之間流傳著一句話--若沙丘上留下長長拖痕，就不要再往前走。」

#### Silhouette

- Head Recognition: 遮面頭巾、粗獷輪廓。
- Weapon Recognition: 巨型屠刀。
- Body Shape: 高壯人類。
- Posture: 肩扛重武器。
- Visual Outline: 身形高壯，披著風蝕嚴重的厚重布袍與獸皮，肩部覆蓋簡易護甲，胸前掛滿奪來的徽章與殘骸，右手拖著帶缺口的大型弧刃。

#### Color

- Source Color Direction: 深棕、暗紅、鐵灰。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 沙海處刑.

#### Animation

- Dynamic Recognition: 重劈、壓迫前進。
- Combat Style: 高爆發單體精英。Source text names `裂沙斬`, but no formal skill database entry is provided.
- Idle: 緩慢呼吸，單手拖著重刃，偶爾抬頭觀察旅團或低頭查看刀刃。
- Death: 單膝跪地，以重刃勉強支撐身體，最後向前倒下，刀身沉重插入沙地。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 古商隊皮革 | `monster_material_master_database.md` |  |
| 屠夫重刃 | `monster_material_master_database.md` |  |
| 沙王徽記 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Formal Skill Database Entry: SOURCE MISSING.
- Target Line: SOURCE MISSING.
- Source combat wording is preserved as descriptive behavior only; no new skill is created.

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: formal skill database entry; target line
- Source Label Note: extracted lore text shows an `遺跡殘兵` heading before the content whose world position, drops, and party note match 沙海屠夫・拉格爾; this draft maps the block by monster database, silhouette Bible, and material source.

---

### MON_CH04_ELITE_003 - 古城守衛長・托爾曼 / Torlman, Warden of the Ruins

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 遺跡外城; 古城入口
- Civilization: Ruin Soldier Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 古城守衛長・托爾曼.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Ruin Soldier Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 遺跡守衛系; Attack Rule > 重武器; Idle Rule > 人形; Death Rule > 重甲人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 遺跡殘兵.

#### Lore

- World Position: 遺跡外城守軍首領，王朝崩毀後仍持續守護古城入口，不允許任何入侵者深入。
- Personality: 沉穩、忠誠、帶有守軍威嚴，如仍在執行古代命令般持續巡守。
- Entry Feeling: 從崩塌城門與塵土中沉重現身，石盾率先落地發出悶響，隨後緩慢站定迎敵。
- Party Note: 「即使王朝早已滅亡，仍有守衛守著它最後的大門。」

#### Silhouette

- Head Recognition: 古代將領頭盔。
- Weapon Recognition: 長柄武器。
- Body Shape: 高大人形守衛。
- Posture: 穩重站姿。
- Visual Outline: 高大的古代守衛，厚重砂岩鎧甲覆蓋全身，胸前刻有王城徽印，左手持巨大石盾，右手握古代重兵器，肩甲與頭盔殘留古王朝雕紋。

#### Color

- Source Color Direction: 石灰、銅綠、古金色。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Desert Civilization Colors > 遺跡殘兵.

#### Animation

- Dynamic Recognition: 穩定推進、橫掃。
- Combat Style: 高防大型精英。Source text names `守城重擊`, but no formal skill database entry is provided.
- Idle: 重心微幅移動，盾牌偶爾調整角度，身上鎧甲與石屑不時掉落。
- Death: 石盾率先碎裂，守衛長半跪後失去支撐，厚重石甲逐步崩落倒下。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 古代石片 | `monster_material_master_database.md` |  |
| 守衛長石印 | `monster_material_master_database.md` |  |
| 王國秘紋 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Formal Skill Database Entry: SOURCE MISSING.
- Target Line: SOURCE MISSING.
- Source combat wording is preserved as descriptive behavior only; no new skill is created.

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: formal skill database entry; target line

---

## Boss Monsters

### MON_CH04_BOSS_001 - 王墓巨像・卡姆拉 / Kamra, Colossus of the Royal Tomb

#### Identity

- Source Type: Boss
- Threat Level: Boss
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 王墓地宮核心區域
- Civilization: Royal Tomb Guardian Civilization; Ancient Colossus Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 王墓巨像・卡姆拉.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Royal Tomb Guardian Civilization; Ancient Colossus Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Boss Animation Rule > 王墓巨像・卡姆拉; Idle Rule > Boss; Attack Rule > 巨像重擊; Death Rule > Boss.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Boss Color Rule > 王墓巨像・卡姆拉.

#### Lore

- World Position: 王墓地宮核心區域的巨型守護者，被打造來阻止任何靠近古王陵墓的人。
- Personality: 沉默、威嚴、壓迫感強，如同古王墓最後一道防線。
- Entry Feeling: 巨型石門震動，伴隨沉重摩擦聲緩慢步出，胸口核心逐漸亮起，地面微微震動。
- Party Note: 「有人說，真正沉睡在王墓裡的從來不是王，而是守著王的人。」

#### Silhouette

- Head Recognition: 巨大石像頭部、王冠雕紋。
- Weapon Recognition: 巨拳與石柱重擊。
- Body Shape: 超大型石像巨人。
- Posture: 王者守護姿態。
- Visual Outline: 約一般單位兩倍大小的巨像，厚重石甲與古代金屬結構融合，肩部與胸口刻有巨大王族紋章，雙臂巨大且帶壓迫感。

#### Color

- Source Color Direction: 石灰、古金、符文藍。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Boss Color Rule > 王墓巨像・卡姆拉.

#### Animation

- Dynamic Recognition: 重踏、巨拳、震地。
- Combat Style: 巨型精英 source text names `地脈震擊`, but the locked silhouette Bible classifies 王墓巨像・卡姆拉 as Boss. No formal skill database entry is provided.
- Idle: 幾乎不移動，只在極慢節奏中轉動頭部與手臂，碎砂從肩部滑落。
- Death: 胸口核心碎裂，肩部與手臂率先崩塌，最後沉重倒地化為巨大石塊殘骸。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 王墓石核 | `monster_material_master_database.md` |  |
| 巨像核心 | `monster_material_master_database.md` |  |
| 古代王魂 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Formal Skill Database Entry: SOURCE MISSING.
- Target Line: SOURCE MISSING.
- Source combat wording is preserved as descriptive behavior only; no new skill is created.

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: formal skill database entry; target line
- Source Conflict: lore extraction labels this block as 精英怪, while `MONSTER_SILHOUETTE_BIBLE.md` and `archive/chapter04_monster_silhouette_260606_145841.docx` classify 王墓巨像・卡姆拉 as Boss. This draft preserves Boss classification and registers the conflict.

---

### MON_CH04_BOSS_002 - 沙海巨像・阿圖姆 / Atum, Colossus of the Sandsea

#### Identity

- Source Type: Boss
- Threat Level: Boss
- Chapter: Chapter 04 - 沙漠遺城
- Region Distribution: 王墓地宮深處
- Civilization: Ancient Colossus Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 04 Monster Table > 沙海巨像・阿圖姆.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 04 > Ancient Colossus Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Boss Animation Rule > 沙海巨像・阿圖姆; Idle Rule > Boss; Attack Rule > 巨像重擊; Death Rule > Boss.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Boss Color Rule > 沙海巨像・阿圖姆.

#### Lore

- World Position: 沉睡於王墓地宮深處的古文明守護者，被打造來阻止任何靠近失落王國核心的人。既是王墓守門者，也是古王朝最後的拒絕意志。
- Personality: 沉默、威嚴、無法動搖，像仍忠誠執行數百年前的命令。對闖入者毫不憤怒，而是以絕對壓迫感執行驅逐。
- Entry Feeling: 王墓深處傳來沉重震動，巨型石門緩慢開啟。阿圖姆原先如雕像般靜止，胸口核心逐漸亮起，雙眼發出古王朝光芒。
- Party Note: 「王墓深處從未真正沉睡。那巨像只是安靜等待，等待下一個試圖打開王國秘密的人。」

#### Silhouette

- Head Recognition: 巨大神像面孔、古文明雕刻。
- Weapon Recognition: 雙臂重擊、沙暴力量。
- Body Shape: 超大型文明巨像。
- Posture: 緩慢起身、俯視敵人。
- Visual Outline: 約一般單位三倍以上體型，厚重砂岩與古代金屬交錯構成巨大軀體，頭部像古代王冠與石像融合，肩部與胸口刻有巨大王朝紋章。

#### Color

- Source Color Direction: 沙黃、古金、岩石灰。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Boss Color Rule > 沙海巨像・阿圖姆.

#### Animation

- Dynamic Recognition: 巨拳落地、沙暴捲動、震地。
- Combat Style: 大型預警型 Boss。Source text names `巨像震踏` and `王墓崩塌`, but no formal skill database entries are provided.
- Idle: 動作極慢，僅伴隨沉重呼吸般震動。肩部與手臂不時滑落砂石，胸口核心明暗變化，頭部偶爾緩慢轉動觀察敵人。
- Death: 胸口核心逐漸碎裂失光，肩部與雙臂率先崩塌，巨像跪倒後沉重倒塌，揚起黃金沙塵與碎石。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 巨像王核 | `monster_material_master_database.md` |  |
| 沙海王印 | `monster_material_master_database.md` |  |
| 阿圖姆石心 | `monster_material_master_database.md` |  |
| 聖殿殘章 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Formal Skill Database Entry: SOURCE MISSING.
- Target Line: SOURCE MISSING.
- Source combat wording is preserved as descriptive behavior only; no new skill is created.

#### Integration Notes

- Lore Source: `archive/chapter04_monster_lore.docx`
- Silhouette Source: `archive/chapter04_monster_silhouette_260606_145841.docx`
- Missing Fields: formal skill database entry; target line
- Source Label Note: extracted lore text shows a `石像巡守者` heading before the content whose boss positioning, drops, and party note match 沙海巨像・阿圖姆; this draft maps the block by monster database, silhouette Bible, and material source.

---

## Chapter 04 Boss Core Positioning

| Boss | Core Role | Combat Reading Direction | Forbidden Direction |
|---|---|---|---|
| 王墓巨像・卡姆拉 | 王墓守護者與古文明巨像的過渡 Boss | 巨像重踏、石柱重擊、王冠壓迫 | Do not make it a fast spam attacker |
| 沙海巨像・阿圖姆 | 沙漠文明最終守護者 | 緩慢起身、巨拳落地、沙暴捲動、大型預警閱讀 | Do not make it a high-frequency Debuff / DOT boss |

---

## Missing Source Register

| Missing / Conflict Item | Source Gap | Handling |
|---|---|---|
| Chapter 04 source type count conflict | `MONSTER_SILHOUETTE_BIBLE.md` lists Chapter 04 as 5 Normal / 0 Special / 3 Elite / 2 Boss; `monster_material_master_database.md` lists 10 material source rows without threat type | Use locked silhouette Bible threat classification; do not infer from material order |
| Chapter 04 lore extraction heading conflicts | extracted lore text repeats or misplaces headings for 地宮爬獸, 沙海屠夫・拉格爾, and 沙海巨像・阿圖姆 | Map blocks by monster database, silhouette Bible, world position, drops, and party note; preserve as review note |
| 王墓巨像・卡姆拉 source type conflict | lore source text labels its block as 精英怪; silhouette Bible classifies it as Boss | Use Boss classification from locked silhouette Bible; preserve conflict note |
| 王墓石衛 lore-only material names | `石衛重甲片` and `古代王徽` appear in lore extraction but are `未存在於 monster_material_master_database.md` | Omitted from Drops; use `王墓石核`, `黃金沙核`, `王墓秘石` from material master |
| 王墓石衛 party note | lore source gives no elite party note text | Marked as `SOURCE MISSING` |
| Elite / Boss formal skill database entries | source text names some actions, but no formal skill database entries are provided | Marked as `SOURCE MISSING`; no skill names created |
| Elite / Boss individual Target Line usage | no source-specific skill targeting available | Marked as `SOURCE MISSING` |
| `material_usage_master_database.md` Chapter 04 usage categories | Chapter 04 section is reserved and has no usage entries | No usage categories added; Monster Database records material names only |

---

## Consolidation Summary

| Category | Count |
|---|---:|
| Normal Monsters | 5 |
| Special Source Monsters | 0 |
| Elite Monsters | 3 |
| Boss Monsters | 2 |
| Reference Layers | 10 |

---

## Bible Mapping Review

| Monster | Silhouette Bible | Civilization Bible | Animation Bible | Color Bible | Mapping Status |
|---|---|---|---|---|---|
| 沙行角獸 | Mapped | Mapped | Mapped | Mapped | OK |
| 沙塵掠食者 | Mapped | Mapped | Mapped | Mapped | OK |
| 遺跡殘兵 | Mapped | Mapped | Mapped | Mapped | OK |
| 石像巡守者 | Mapped | Mapped | Mapped | Mapped | OK |
| 地宮爬獸 | Mapped | Mapped | Mapped | Mapped | OK |
| 王墓石衛 | Mapped | Mapped | Mapped | Mapped | OK |
| 沙海屠夫・拉格爾 | Mapped | Mapped | Mapped | Mapped | OK |
| 古城守衛長・托爾曼 | Mapped | Mapped | Mapped | Mapped | OK |
| 王墓巨像・卡姆拉 | Mapped | Mapped | Mapped | Mapped | OK |
| 沙海巨像・阿圖姆 | Mapped | Mapped | Mapped | Mapped | OK |

No Chapter 04 monster in this draft is unable to map to the locked Monster Bible files.
