# CHAPTER01_MONSTER_DATABASE.md

Version: v1
Status: Review Draft
Chapter: Chapter 01 - Kingdom Border
Phase: Closed Beta Consolidation Phase
Scope: Monster Database Consolidation Only

---

## Document Rules

- Do not create new monsters.
- Do not create new civilizations.
- Do not create new classes.
- Do not create Chapter 06+ content.
- Character System = Locked.
- Weapon System = Locked.
- Monster Bible System = Locked.
- This document consolidates existing Chapter 01 monster sources only.
- Missing data is marked as `SOURCE MISSING`.
- Drop Quantity is not recorded in this Monster Database.
- Drop materials must come from `monster_material_master_database.md`.

---

## Source Priority

1. `AGENTS.md`
2. `GAME_CURRENT_VERSION.md`
3. `CURRENT_PROJECT_STATE.md`
4. `combat_system_current.md`
5. `CLASS_TREE_CURRENT.md`
6. `archive/chapter01_monster_lore.docx`
7. `archive/chapter01_monster_silhouette_260606_150045.docx`
8. `C:/Users/User/Documents/Codex/2026-06-01/new-chat/MONSTER_SILHOUETTE_BIBLE.md`
9. `C:/Users/User/Documents/Codex/2026-06-01/new-chat/MONSTER_CIVILIZATION_BIBLE.md`
10. `C:/Users/User/Documents/Codex/2026-06-01/new-chat/MONSTER_ANIMATION_BIBLE.md`
11. `C:/Users/User/Documents/Codex/2026-06-01/new-chat/MONSTER_COLOR_BIBLE.md`
12. `monster_material_master_database.md`
13. `material_usage_master_database.md`

---

## Source Index

| Data Type | Source | Integration Rule |
|---|---|---|
| Lore | `archive/chapter01_monster_lore.docx` | Consolidate only |
| Silhouette | `MONSTER_SILHOUETTE_BIBLE.md`; `archive/chapter01_monster_silhouette_260606_150045.docx` | Use approved silhouette Bible reference and Chapter 01 source row |
| Color | `MONSTER_COLOR_BIBLE.md`; `MONSTER_SILHOUETTE_BIBLE.md` | Use approved color Bible rule plus source color direction |
| Animation | `MONSTER_ANIMATION_BIBLE.md`; `archive/chapter01_monster_lore.docx`; `archive/chapter01_monster_silhouette_260606_150045.docx` | Use approved animation Bible rule plus source animation text |
| Civilization | `MONSTER_CIVILIZATION_BIBLE.md` | Use Chapter 01 civilization mapping where directly listed |
| Drops | `monster_material_master_database.md` | Material names only; no quantity |
| Threat Level | Approved hierarchy | Normal / Elite / Boss |
| Region Distribution | Source text only | Do not add regions |

---

## Chapter Overview

- Chapter: Chapter 01
- Region: 王國邊境 / Kingdom Border
- Closed Beta Scope: Chapter 01~05 only
- Encounter System: weighted random encounters
- Boss Encounter System: weighted accumulated encounter
- Fixed Boss Stage: No
- Chapter 06+ Handling: Out of scope

---

## Chapter 01 Region Distribution Matrix

This matrix uses only region / location wording present in approved sources.

| Source Region Text | Monsters Referenced | Notes |
|---|---|---|
| 王國邊境 | 邊境野狼; 哥布林斥侯; 流亡士兵; 污染史萊姆; 邊境野犬; 邊境盜賊; 重裝流寇; 狂暴狼人; 王國逃兵隊長; 黑狼王; 邊境掠奪者首領 | Chapter-wide source region |
| 道路與營地附近 | 哥布林斥侯 | From lore source |
| 廢棄研究設施周邊 | 污染史萊姆 | From lore source |
| 王國邊境森林與廢棄設施附近 | 狂暴狼人 | From lore source |
| 王國邊境森林與荒地 | 黑狼王 | From lore source |
| 邊境路線 | 邊境掠奪者首領 | From lore source |
| 旅人與商隊路線 | 邊境掠奪者首領 | From lore source |

---

## Chapter 01 Monster Master Table

| Monster ID | Monster Name | Type | Threat Level | Region Distribution | Civilization |
|---|---|---|---|---|---|
| MON_CH01_NORMAL_001 | 邊境野狼 / Border Wolf | Normal | Normal | 王國邊境 | Border Wildlife Civilization |
| MON_CH01_NORMAL_002 | 哥布林斥侯 / Goblin Scout | Normal | Normal | 王國邊境; 道路與營地附近 | Goblin Scavenger Civilization |
| MON_CH01_NORMAL_003 | 流亡士兵 / Exiled Soldier | Normal | Normal | 王國邊境 | Border Outlaw Civilization |
| MON_CH01_NORMAL_004 | 污染史萊姆 / Polluted Slime | Normal | Normal | 王國邊境; 廢棄研究設施周邊 | Low Alchemy Pollution Civilization |
| MON_CH01_NORMAL_005 | 邊境野犬 / Wild Hound | Normal | Normal | 王國邊境 | Border Wildlife Civilization |
| MON_CH01_NORMAL_006 | 邊境盜賊 / Border Bandit | Normal | Normal | 王國邊境 | Border Outlaw Civilization |
| MON_CH01_ELITE_001 | 重裝流寇 / Heavy Marauder | Elite | Elite | 王國邊境 | Border Outlaw Civilization |
| MON_CH01_ELITE_002 | 狂暴狼人 / Rampaging Werewolf | Elite | Elite | 王國邊境森林與廢棄設施附近 | SOURCE MISSING |
| MON_CH01_ELITE_003 | 王國逃兵隊長 / Kingdom Deserter Captain | Elite | Elite | 王國邊境 | Kingdom Deserter Civilization |
| MON_CH01_BOSS_001 | 黑狼王 / Black Wolf King | Boss | Boss | 王國邊境森林與荒地 | Beast King Civilization |
| MON_CH01_BOSS_002 | 邊境掠奪者首領 / Border Raider Leader | Boss | Boss | 王國邊境; 邊境路線; 旅人與商隊路線 | Border Outlaw Civilization |

---

## Normal Monsters

### MON_CH01_NORMAL_001 - 邊境野狼 / Border Wolf

#### Identity

- Type: Normal
- Threat Level: Normal
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境
- Civilization: Border Wildlife Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 邊境野狼.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Border Wildlife Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 狼犬類; Idle Rule > 野獸; Attack Rule; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 邊境狼犬.

#### Lore

- World Position: 王國邊境常見野生掠食者，因邊境資源稀少與獵物減少而長期處於飢餓狀態。
- Personality: 長期飢餓使其警戒且不耐，會低頭觀察獵物、來回徘徊，偶爾露牙低鳴，等待破綻後進攻。
- Entry Feeling: 拖著略慢步伐進場，眼神始終盯著目標，因飢餓顯得疲憊但仍保持攻擊性。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 狼型頭部、深棕嘴部、略帶唾液感。
- Weapon Recognition: 利牙與撲咬動作。
- Body Shape: 中小型、略消瘦。
- Posture: 低頭警戒、微前傾、尾巴略翹。
- Visual Outline: 稍微消瘦的狼型野獸，灰色皮毛，嘴部帶深棕色污痕，嘴角帶些許口水，尾巴略微翹曲，整體有疲憊但危險的感覺。

#### Color

- Source Color Direction: 灰色皮毛／深棕口鼻／荒野灰。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 邊境狼犬.

#### Animation

- Dynamic Recognition: 快速撲咬、低鳴、甩尾。
- Combat Style: 快速短距離撲咬，攻擊後稍微停頓觀察，再尋找下一次時機。
- Idle: 小幅喘息與呼吸起伏，偶爾甩尾、低鳴、微微壓低身體。
- Death: 向側自然倒地，嘴角帶少量鮮血，維持野獸死亡後的自然感，不誇張演出。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 狼牙 | `monster_material_master_database.md` |  |
| 粗皮革 | `monster_material_master_database.md` |  |
| 狂狼利牙 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: none for reference layer

---

### MON_CH01_NORMAL_002 - 哥布林斥侯 / Goblin Scout

#### Identity

- Type: Normal
- Threat Level: Normal
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境; 道路與營地附近
- Civilization: Goblin Scavenger Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 哥布林斥侯.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Goblin Scavenger Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Global Monster Animation Rule; Animation Readability Rule; Idle Rule; Attack Rule; Death Rule.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Global Monster Color Rule; Color Hierarchy Rule; source color from `MONSTER_SILHOUETTE_BIBLE.md` Chapter 01 Monster Table.

#### Lore

- World Position: 王國邊境常見的小型偷竊與騷擾型哥布林，經常在道路與營地附近徘徊。
- Personality: 靈敏、膽小但好奇，依靠異常敏銳的嗅覺發現人類蹤跡，雖然弱小卻喜歡試探與騷擾。
- Entry Feeling: 聞到氣味後抬高鼻子左右探索，發現人類後晃動身體準備動手。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 白色羽毛頭飾、綠色哥布林頭部。
- Weapon Recognition: 單手石塊投擲。
- Body Shape: 矮小、四肢纖細、微凸腹部。
- Posture: 駝背感、東張西望、略不安。
- Visual Outline: 傳統綠皮哥布林，四肢纖細、肚子微突，頭戴輕便白羽頭飾，手持石塊或小型雜物。

#### Color

- Source Color Direction: 哥布林綠／泥土棕／灰白羽毛。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Global Monster Color Rule; Color Hierarchy Rule; source color from `MONSTER_SILHOUETTE_BIBLE.md` Chapter 01 Monster Table.

#### Animation

- Dynamic Recognition: 撿石頭、投擲、快速晃動。
- Combat Style: 從地面快速撿起石塊投擲敵人，以騷擾為主，威脅較低。
- Idle: 慌張地低頭搜尋石塊，不時左右張望。
- Death: 向後傾倒成大字型，石塊散落地面。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 哥布林羽毛 | `monster_material_master_database.md` |  |
| 韌藤 | `monster_material_master_database.md` |  |
| 粗製石片 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: none for reference layer

---

### MON_CH01_NORMAL_003 - 流亡士兵 / Exiled Soldier

#### Identity

- Type: Normal
- Threat Level: Normal
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境
- Civilization: Border Outlaw Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 流亡士兵.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Border Outlaw Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 流亡士兵; Humanoid Type Rules > 流寇系; Idle Rule > 人形; Attack Rule; Death Rule > 人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 邊境流寇.

#### Lore

- World Position: 王國邊境流亡士兵與流寇，部分人曾屬舊帝國軍勢，如今淪為邊境掠奪者。
- Personality: 放不下過去榮耀與軍旅習慣，在邊境求生中逐漸走向暴力與掠奪。
- Entry Feeling: 發現目標後帶著自信神情慢步靠近，握緊武器準備下手。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 光頭、粗獷表情。
- Weapon Recognition: 破損單手刀。
- Body Shape: 中型、壯碩。
- Posture: 挺胸、略帶軍人感、正面壓迫。
- Visual Outline: 赤裸上身，配戴單邊肩甲，光頭，右手持破損單手刀，外表粗獷且帶風塵感。

#### Color

- Source Color Direction: 皮革棕／生鏽鐵灰／舊軍布色。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 邊境流寇.

#### Animation

- Dynamic Recognition: 沉重劈砍、前壓步伐。
- Combat Style: 基礎劈砍與直接攻擊，攻勢簡單但具有壓迫感。
- Idle: 正常呼吸起伏，偶爾調整握刀姿勢。
- Death: 單膝跪地，武器插地支撐，最後低頭倒下。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 破損護甲片 | `monster_material_master_database.md` |  |
| 生鏽鐵皮 | `monster_material_master_database.md` |  |
| 粗布 | `monster_material_master_database.md` |  |
| 鐵礦 | `monster_material_master_database.md` |  |
| 舊軍牌 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: none for reference layer

---

### MON_CH01_NORMAL_004 - 污染史萊姆 / Polluted Slime

#### Identity

- Type: Normal
- Threat Level: Normal
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境; 廢棄研究設施周邊
- Civilization: Low Alchemy Pollution Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 污染史萊姆.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Low Alchemy Pollution Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Pollution / Slime Animation Rule; Idle Rule > 史萊姆／污染; Attack Rule; Death Rule > 史萊姆／污染.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Pollution Civilization Colors.

#### Lore

- World Position: 因攝取鍊金廢棄物與魔素污染而異化的邊境生物，常出沒於廢棄研究設施周邊。
- Personality: 原本無害，但受到污染後產生低程度攻擊性，會本能接近活物。
- Entry Feeling: 緩慢蠕動進場，黏液拖曳地面，身體微微鼓動。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 無頭部輪廓、中央黑色核心。
- Weapon Recognition: 黏液彈射／腐蝕液體。
- Body Shape: 低矮圓形、凝膠狀。
- Posture: 上下波動、緩慢蠕動。
- Visual Outline: 粉紫色黏稠身軀帶凝結感，表面黏液緩慢流動，身體插著半截樹枝，中心可見黑色核心。

#### Color

- Source Color Direction: 粉紫色／黏液灰／黑色核心。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Pollution Civilization Colors.

#### Animation

- Dynamic Recognition: 身體鼓動、液體噴濺、蠕動。
- Combat Style: 利用消化液與身體碎塊彈射攻擊，嘗試黏附與限制目標。
- Idle: 身體上下波動，核心偶爾閃動，黏液緩慢滴落。
- Death: 逐漸失去形狀，最後化成一灘平靜粉紫色黏液。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 汙染黏液 | `monster_material_master_database.md` |  |
| 魔素碎晶 | `monster_material_master_database.md` |  |
| 變質膠質 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: none for reference layer

---

### MON_CH01_NORMAL_005 - 邊境野犬 / Wild Hound

#### Identity

- Type: Normal
- Threat Level: Normal
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境
- Civilization: Border Wildlife Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 邊境野犬.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Border Wildlife Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 狼犬類; Idle Rule > 野獸; Attack Rule; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 邊境狼犬.

#### Lore

- World Position: 王國邊境常見群體犬科動物，相較野狼更擅長依靠群體求生。
- Personality: 因群體生活而較具自信與協同行動傾向，會緊盯目標尋找時機。
- Entry Feeling: 銳利眼神鎖定敵人，緩慢向前逼近並低聲吠鳴。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 犬型頭部、銳利眼神。
- Weapon Recognition: 利牙與撲咬。
- Body Shape: 中小型、較健康壯實。
- Posture: 低頭凝視、短暫蓄力。
- Visual Outline: 深棕色犬類外觀，體格較健康結實，眼神銳利，整體更具活力。

#### Color

- Source Color Direction: 深棕／荒野灰棕。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 邊境狼犬.

#### Animation

- Dynamic Recognition: 短距離撲擊、喘息、低吼。
- Combat Style: 攻擊前低吼，快速短距離撲咬後退回原位。
- Idle: 小幅喘息與呼吸起伏，偶爾輕甩尾巴與低鳴。
- Death: 向側自然倒地，嘴角少量鮮血，保有自然野獸死亡感。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 風乾獸皮 | `monster_material_master_database.md` |  |
| 野犬尖牙 | `monster_material_master_database.md` |  |
| 狂躁犬牙 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: none for reference layer

---

### MON_CH01_NORMAL_006 - 邊境盜賊 / Border Bandit

#### Identity

- Type: Normal
- Threat Level: Normal
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境
- Civilization: Border Outlaw Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 邊境盜賊.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Border Outlaw Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 邊境盜賊; Humanoid Type Rules > 流寇系; Idle Rule > 人形; Attack Rule; Death Rule > 人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 邊境流寇.

#### Lore

- World Position: 王國邊境結黨行動的低階盜匪，依靠埋伏與數量優勢掠奪旅者。
- Personality: 狡猾、現實、會試探敵人，較少正面硬拚，更依賴威嚇與機會。
- Entry Feeling: 拿著長槍左右比劃，試探般向前靠近。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 披頭散髮、黑色頭髮。
- Weapon Recognition: 雙手長槍。
- Body Shape: 中型、略精瘦。
- Posture: 前傾持槍、準備刺擊姿勢。
- Visual Outline: 黑髮披散，穿著破舊服裝，雙手持簡單長槍，外觀略顯落魄但仍帶危險感。

#### Color

- Source Color Direction: 破布灰／泥土棕／鐵灰。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 邊境流寇.

#### Animation

- Dynamic Recognition: 槍尖比劃、前刺動作、警戒站姿。
- Combat Style: 找準距離後向前突刺，以簡單但直接的方式壓迫敵人。
- Idle: 維持攻擊架式，上下呼吸擺動，偶爾重新握槍。
- Death: 身體向前趴倒，長槍插地後失去支撐。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 粗布 | `monster_material_master_database.md` |  |
| 生鏽鐵片 | `monster_material_master_database.md` |  |
| 破舊槍柄 | `monster_material_master_database.md` |  |
| 邊境錢袋 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: none for reference layer

---

## Elite Monsters

### MON_CH01_ELITE_001 - 重裝流寇 / Heavy Marauder

#### Identity

- Type: Elite
- Threat Level: Elite
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境
- Civilization: Border Outlaw Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 重裝流寇.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Border Outlaw Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 重裝流寇; Humanoid Type Rules > 流寇系; Idle Rule > 人形; Attack Rule; Death Rule > 重甲人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors; Elite Monster Color Rule > 重裝／守衛型.

#### Encounter Identity

- Encounter Type: Elite
- Encounter Method: Weighted random encounter
- Encounter Role: 穩定近戰壓力型精英
- Spawn Context: 王國邊境流寇頭目

#### Lore

- World Position: 王國邊境流寇頭目，過去曾為舊帝國軍勢中的小隊長，現帶領邊境流亡者與掠奪者活動。
- Personality: 經驗老道、沉穩、帶軍人習慣，雖淪為流寇仍保有戰場紀律與判斷能力。
- Entry Feeling: 左腳向前沉重跨步，將盾牌略微抬起，深吸一口氣後擺出防守架勢。
- Party Note: 「邊境有人說，他只是把王國軍令換成了更值錢的東西。」

#### Silhouette

- Head Recognition: 全罩式頭盔、黑色紋路點綴。
- Weapon Recognition: 右手大型單刀＋左手盾牌。
- Body Shape: 大型、厚重、高壓迫感。
- Posture: 重心偏穩、盾牌前傾、防守架勢。
- Visual Outline: 身穿全套厚重盔甲，包含頭部護具，鎧甲邊緣帶黑色磨損線條與歲月痕跡。右手持簡單大刀，左手持厚重盾牌，整體輪廓沉重而具壓迫感。

#### Color

- Source Color Direction: 鐵灰／舊鋼黑／深棕皮革。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors; Elite Monster Color Rule > 重裝／守衛型.

#### Animation

- Dynamic Recognition: 沉重步伐、盾牌抬起、小幅防禦動作、重砍。
- Combat Style: 穩定近戰壓力型精英。受擊時會自然提高盾牌防禦，進攻則以沉重揮擊壓迫敵人。
- Idle: 穩定呼吸起伏，偶爾調整盾牌角度與握刀姿勢，維持警備狀態。
- Death: 單膝跪地後武器與盾牌緩慢放下，最後沉重向前倒地。

#### Combat Readability

- Focus Queue Priority: Elite Skill.
- Threat Marker: Use low-presence threat marker only.
- Target Line: SOURCE MISSING.
- Forbidden: no giant warning FX; no visual spam.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 破損護甲片 | `monster_material_master_database.md` |  |
| 重裝鐵片 | `monster_material_master_database.md` |  |
| 生鏽重盾碎片 | `monster_material_master_database.md` |  |
| 流寇軍牌 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: specific skill name

---

### MON_CH01_ELITE_002 - 狂暴狼人 / Rampaging Werewolf

#### Identity

- Type: Elite
- Threat Level: Elite
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境森林與廢棄設施附近
- Civilization: SOURCE MISSING

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 狂暴狼人.
- Civilization Reference: SOURCE MISSING. `MONSTER_CIVILIZATION_BIBLE.md` Chapter 01 does not directly list 狂暴狼人 under a civilization row.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Global Monster Animation Rule; Animation Readability Rule; Idle Rule; Attack Rule; Death Rule.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Global Monster Color Rule; Color Hierarchy Rule; source color from `MONSTER_SILHOUETTE_BIBLE.md` Chapter 01 Monster Table.

#### Encounter Identity

- Encounter Type: Elite
- Encounter Method: Weighted random encounter
- Encounter Role: 高侵略近戰精英
- Spawn Context: 邊境神秘鍊金實驗失敗後誕生的危險個體

#### Lore

- World Position: 由邊境神秘鍊金實驗失敗後誕生的危險個體，脫離控制後徘徊於王國邊境森林與廢棄設施附近。
- Personality: 狂躁、失控、極具攻擊性，對聲響與生命氣息異常敏感，會迅速撲向任何被察覺的目標。
- Entry Feeling: 從陰影中高速躍入場中，落地時因慣性略微挺直身體，接著立刻鎖定目標。
- Party Note: 「有些獵人說，牠最可怕的不是爪子，而是看起來像還記得自己曾是人。」

#### Silhouette

- Head Recognition: 狼型頭部、尖牙外露、兇狠眼神。
- Weapon Recognition: 雙爪與尖牙。
- Body Shape: 高瘦大型、肌肉明顯、半弓身。
- Posture: 前傾壓低身體、隨時撲擊姿態。
- Visual Outline: 直立行走的狼人，身體微微前傾，銳利牙齒與尖爪殘留血痕，毛色偏深灰與黑褐混色，眼神帶有危險瘋狂感。

#### Color

- Source Color Direction: 深灰棕毛皮／血痕紅／黑灰陰影。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Global Monster Color Rule; Color Hierarchy Rule; source color from `MONSTER_SILHOUETTE_BIBLE.md` Chapter 01 Monster Table.

#### Animation

- Dynamic Recognition: 跳躍撲擊、雙爪揮砍、快速前壓。
- Combat Style: 高侵略近戰精英，以雙爪撕裂與尖牙撲擊為主，偏好鎖定受傷與弱勢目標。
- Idle: 身體微微弓起，伴隨呼吸起伏，利爪偶爾不安地擺動與抓地。
- Death: 身體逐漸蜷縮後向側傾倒，殘留低沉喘息後失去動作。

#### Combat Readability

- Focus Queue Priority: Elite Skill.
- Threat Marker: Use low-presence threat marker only.
- Target Line: SOURCE MISSING.
- Forbidden: no giant warning FX; no visual spam.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 狂狼利牙 | `monster_material_master_database.md` |  |
| 異化獸血 | `monster_material_master_database.md` |  |
| 狼化皮革 | `monster_material_master_database.md` |  |
| 實驗殘片 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: specific skill name

---

### MON_CH01_ELITE_003 - 王國逃兵隊長 / Kingdom Deserter Captain

#### Identity

- Type: Elite
- Threat Level: Elite
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境
- Civilization: Kingdom Deserter Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 王國逃兵隊長.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Kingdom Deserter Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 王國逃兵隊長; Humanoid Type Rules > 王國士兵系; Idle Rule > 人形; Attack Rule; Death Rule > 人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Kingdom Civilization Colors > 王國逃兵.

#### Encounter Identity

- Encounter Type: Elite
- Encounter Method: Weighted random encounter
- Encounter Role: 防守反擊型精英
- Spawn Context: 攜帶王國情報逃離國境的警備隊長

#### Lore

- World Position: 攜帶王國情報逃離國境的警備隊長，熟悉王國軍制與邊境巡防方式。
- Personality: 冷靜、戒備、帶有軍官習慣與警戒性，時刻觀察戰場與周遭動向。
- Entry Feeling: 原先背對敵人，察覺秘密暴露後緩慢轉身，重新握緊武器進入戰鬥。
- Party Note: 「有人說，他不是想背叛王國，只是不再相信它還值得守護。」

#### Silhouette

- Head Recognition: 王國警備頭盔、軍事感輪廓。
- Weapon Recognition: 短矛＋小圓盾。
- Body Shape: 中大型、標準士兵體格。
- Posture: 正面站姿、偏軍人感、穩定壓迫。
- Visual Outline: 身穿中規中矩的王國警備裝束，戴警衛頭盔，左手持小圓盾，右手持鋼製短矛，整體帶軍事秩序感。

#### Color

- Source Color Direction: 王國鐵灰／軍布深藍灰／皮革棕。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Kingdom Civilization Colors > 王國逃兵.

#### Animation

- Dynamic Recognition: 短矛左右揮擊、卸力盾擺動、穩定推進。
- Combat Style: 防守反擊型精英。受擊時會以小圓盾卸除力道，再利用短矛左右揮擊與刺擊壓迫敵人。
- Idle: 雙手自然垂下，維持呼吸節奏，偶爾觀察敵方動作並重新調整站姿。
- Death: 短矛脫手飛出，身體向後倒下，頭盔略微滑落。

#### Combat Readability

- Focus Queue Priority: Elite Skill.
- Threat Marker: Use low-presence threat marker only.
- Target Line: SOURCE MISSING.
- Forbidden: no giant warning FX; no visual spam.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 王國軍牌 | `monster_material_master_database.md` |  |
| 鋼製短矛碎片 | `monster_material_master_database.md` |  |
| 警備護甲布 | `monster_material_master_database.md` |  |
| 機密殘頁 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: specific skill name

---

## Boss Monsters

### MON_CH01_BOSS_001 - 黑狼王 / Black Wolf King

#### Identity

- Type: Boss
- Threat Level: Boss
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境森林與荒地
- Civilization: Beast King Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 黑狼王.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Beast King Civilization; Boss Civilization Rule > 黑狼王.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 狼犬類; Boss Animation Rule > 黑狼王; Idle Rule > Boss; Attack Rule; Death Rule > Boss.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 巨型野獸; Boss Color Rule > 黑狼王.

#### Encounter Identity

- Encounter Type: Boss
- Encounter Method: Weighted accumulated encounter
- Encounter Role: 高機動野獸型 Boss
- Weight Reset Rule: Reset after boss encounter
- Fixed Stage Boss: No

#### Lore

- World Position: 王國邊境森林與荒地中的狼群首領，長期支配周遭狩獵區域。因邊境資源稀少與生存競爭，使其比一般野狼更加凶暴與狡猾，被旅者視為邊境真正的野性威脅。
- Personality: 冷靜、耐心、具領地意識。不同於普通野狼的焦躁，黑狼王更像經驗豐富的獵手，會觀察敵人弱點與時機後才發動攻擊。
- Entry Feeling: 遠處先傳來低沉狼嚎與草叢晃動聲，黑狼王緩慢步入場中，停下後低頭觀察敵人，最後發出警告般低吼。
- Party Note: 「老獵人說，當森林裡所有聲音突然安靜下來，就代表牠已經先看到你了。」

#### Silhouette

- Head Recognition: 巨大狼首、深黑毛皮、銳利黃瞳、獠牙外露。
- Weapon Recognition: 巨大狼爪與撕咬。
- Body Shape: 大型野獸、高壓迫感、比一般狼明顯更巨大。
- Posture: 低頭壓身、前傾威嚇、尾部低壓，帶王者壓迫感。
- Visual Outline: 比一般野狼巨大許多，黑灰色毛皮夾雜深棕色斑紋，身形結實而修長，肩部與背部帶有舊傷痕跡。雙眼帶深黃色光澤，嘴邊殘留乾涸血跡，尾巴低垂但富有力量感。整體輪廓強調「成熟掠食者」與「狼王感」。
- Silhouette Recognition Focus: 巨大狼首＋黑色毛皮＋大型野獸輪廓。

#### Color

- Source Color Direction: 黑灰毛皮／深棕傷痕／黃瞳。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 巨型野獸; Boss Color Rule > 黑狼王.

#### Animation

- Dynamic Recognition: 高速撲擊、大幅狼爪揮擊、低吼與重踏步。
- Combat Style: 高機動野獸型 Boss，以高速撲咬與利牙撕裂壓迫敵人。偏好追擊受傷與生命較低目標，作為玩家理解野獸型 Boss 節奏與「流血威脅感」的入門。
- Idle: 呼吸帶動胸口與肩膀起伏，偶爾露牙低鳴，尾巴緩慢擺動，始終緊盯敵人動向。
- Death: 身體逐漸失去力量，先半跪式伏地，最後側身倒下，帶著最後一次低沉喘息停止動作。

#### Combat Readability

- Focus Queue Priority: S Priority.
- Boss Skill Presentation: subtle focus emergence only.
- Boss First Queue Slot: may use 110%~120% micro scale and +10%~20% micro brightness per combat source rules.
- Boss Skill Near Ready: may use +5%~10% body brightness per combat source rules.
- Target Line: SOURCE MISSING.
- Forbidden: no cinematic hard pause; no forced camera; no giant warning FX; no MMORPG raid alert UI; no permanent boss spotlight.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 狂狼利牙 | `monster_material_master_database.md` |  |
| 狼王獸皮 | `monster_material_master_database.md` |  |
| 狼王利爪 | `monster_material_master_database.md` |  |
| 邊境獸核 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: specific boss skill name

---

### MON_CH01_BOSS_002 - 邊境掠奪者首領 / Border Raider Leader

#### Identity

- Type: Boss
- Threat Level: Boss
- Chapter: Chapter 01 - 王國邊境
- Region Distribution: 王國邊境; 邊境路線; 旅人與商隊路線
- Civilization: Border Outlaw Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 01 Monster Table > 邊境掠奪者首領.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 01 > Border Outlaw Civilization; Boss Civilization Rule > 邊境掠奪者首領.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 邊境掠奪者首領; Humanoid Type Rules > 流寇系; Boss Animation Rule > 邊境掠奪者首領; Idle Rule > Boss; Attack Rule; Death Rule > Boss.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 掠奪者首領; Boss Color Rule > 邊境掠奪者首領.

#### Encounter Identity

- Encounter Type: Boss
- Encounter Method: Weighted accumulated encounter
- Encounter Role: 穩定近戰壓力型 Boss
- Weight Reset Rule: Reset after boss encounter
- Fixed Stage Boss: No

#### Lore

- World Position: 活躍於王國邊境的流寇首領，帶領盜匪與流亡者襲擊旅人與商隊。熟悉邊境路線與巡防漏洞，是王國秩序衰退的縮影之一。
- Personality: 狡猾、貪婪、自信，善於利用威嚇與經驗壓制敵人，對弱者毫不留情，但也懂得判斷局勢。
- Entry Feeling: 緩慢從人群後走出，一邊打量敵人一邊將武器扛上肩，露出帶嘲諷意味的笑容後進入戰鬥。
- Party Note: 「有人說，比野獸更危險的，是那些早已習慣掠奪同類的人。」

#### Silhouette

- Head Recognition: 粗獷長髮或半覆面、明顯傷痕感。
- Weapon Recognition: 大型重武器（重刀／巨斧方向）或大型長槍。
- Body Shape: 中大型、厚實壯碩、掠奪者首領氣勢。
- Posture: 直面敵人、站姿穩重、單側持武器形成壓迫感。
- Visual Outline: 高壯人類男性，披著舊軍用披肩與粗糙護甲，身上帶多處舊傷與磨損。頭髮凌亂，眼神兇狠，手持大型彎刀或沉重戰刃，腰間掛有搜刮來的雜物與錢袋。
- Silhouette Recognition Focus: 首領體格＋大型武器＋粗獷掠奪者感。

#### Color

- Source Color Direction: 舊鐵灰／泥土棕／深紅布料點綴。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 掠奪者首領; Boss Color Rule > 邊境掠奪者首領.

#### Animation

- Dynamic Recognition: 大幅度重擊、前壓步伐、威嚇動作。
- Combat Style: 穩定近戰壓力型 Boss，利用沉重揮擊與連續攻勢壓迫敵人。比普通流亡士兵更具節奏與威脅，但不以高爆發秒殺為核心。
- Idle: 呼吸穩定，偶爾扭動肩膀與調整握刀姿勢，像在等待最佳時機下手。
- Death: 武器脫手落地，單膝跪下後向前倒地，原本強撐的氣勢逐漸消失。

#### Combat Readability

- Focus Queue Priority: S Priority.
- Boss Skill Presentation: subtle focus emergence only.
- Boss First Queue Slot: may use 110%~120% micro scale and +10%~20% micro brightness per combat source rules.
- Boss Skill Near Ready: may use +5%~10% body brightness per combat source rules.
- Target Line: SOURCE MISSING.
- Forbidden: no cinematic hard pause; no forced camera; no giant warning FX; no MMORPG raid alert UI; no permanent boss spotlight.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 掠奪者護腕 | `monster_material_master_database.md` |  |
| 破損戰刃碎片 | `monster_material_master_database.md` |  |
| 舊軍牌 | `monster_material_master_database.md` |  |
| 邊境錢袋 | `monster_material_master_database.md` |  |
| 流寇徽記 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter01_monster_lore.docx`
- Silhouette Source: `archive/chapter01_monster_silhouette_260606_150045.docx`
- Missing Fields: specific boss skill name

---

## Chapter 01 Boss Core Positioning

Source text:

- 新手區高存在感 Boss
- 野獸威脅與人類威脅對照
- 玩家首次理解 Boss 戰鬥節奏
- 文明邊境世界觀建立
- 王國秩序崩壞伏筆
- 高可讀性與舒服觀看

Formal philosophy from source:

```text
牠們不是終點。
牠們是：
「旅人第一次真正意識到，王國邊境並不安全。」
```

---

## Missing Source Register

| Missing Data | Impact | Handling |
|---|---|---|
| 狂暴狼人 direct civilization row | `MONSTER_CIVILIZATION_BIBLE.md` Chapter 01 does not directly list 狂暴狼人 under a civilization row | Marked as `SOURCE MISSING`; no civilization inferred |
| Specific skill names for Elite / Boss monsters | Cannot define skill database entries | Marked as `SOURCE MISSING`; no skill names created |
| Target Line usage by individual Elite / Boss skill | No source-specific skill targeting available | Marked as `SOURCE MISSING` |
