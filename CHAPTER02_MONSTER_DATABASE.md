# CHAPTER02_MONSTER_DATABASE.md

Version: v1
Status: Review Draft
Chapter: Chapter 02 - Traveler Wasteland
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
- This document consolidates existing Chapter 02 monster sources only.
- Missing data is marked as `SOURCE MISSING`.
- Drop Quantity is not recorded in this Monster Database.
- Drop rate is not recorded in this Monster Database.
- Drop materials must come from `monster_material_master_database.md`.

---

## Source Priority

1. `AGENTS.md`
2. `GAME_CURRENT_VERSION.md`
3. `CURRENT_PROJECT_STATE.md`
4. `combat_system_current.md`
5. `CLASS_TREE_CURRENT.md`
6. `archive/chapter02_monster_lore.docx`
7. `archive/chapter02_monster_silhouette_260606_150038.docx`
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
| Lore | `archive/chapter02_monster_lore.docx` | Consolidate only |
| Silhouette | `MONSTER_SILHOUETTE_BIBLE.md`; `archive/chapter02_monster_silhouette_260606_150038.docx` | Use approved silhouette Bible reference and Chapter 02 source row |
| Color | `MONSTER_COLOR_BIBLE.md`; `MONSTER_SILHOUETTE_BIBLE.md` | Use approved color Bible rule plus source color direction |
| Animation | `MONSTER_ANIMATION_BIBLE.md`; `archive/chapter02_monster_lore.docx`; `archive/chapter02_monster_silhouette_260606_150038.docx` | Use approved animation Bible rule plus source animation text |
| Civilization | `MONSTER_CIVILIZATION_BIBLE.md` | Use Chapter 02 civilization mapping where directly listed |
| Drops | `monster_material_master_database.md` | Material names only; no quantity or drop rate |
| Threat Level | Approved hierarchy | Normal / Elite / Boss only |
| Region Distribution | Source text only | Do not add regions |

---

## Chapter Overview

- Chapter: Chapter 02
- Region: 旅人荒境 / Traveler Wasteland
- Closed Beta Scope: Chapter 01~05 only
- Encounter System: weighted random encounters
- Boss Encounter System: weighted accumulated encounter
- Fixed Boss Stage: No
- Chapter 06+ Handling: Out of scope

---

## Chapter 02 Region Distribution Matrix

This matrix uses only region / location wording present in approved sources.

| Source Region Text | Monsters Referenced | Notes |
|---|---|---|
| 旅人荒境 | 荒野鬣犬; 流浪掠奪者; 沙塵蜥蜴; 裂風幼鳥; 荒野飛蟲; 異化旅獸; 荒野弩手; 裂風猛禽; 沙塵異獸; 荒野處刑者; 裂風獵鷹; 乾裂巨蜥; 裂風獅鷲 | Chapter-wide source region |
| 荒境 | 荒野鬣犬 | From lore source |
| 荒境商路 | 流浪掠奪者 | From lore source |
| 乾涸的荒地 | 沙塵蜥蜴 | From lore source |
| 岩石間 | 裂風幼鳥 | From lore source |
| 腐敗屍骸、乾裂獸骨與荒野水源附近 | 荒野飛蟲 | From lore source |
| 旅人荒境裡 | 異化旅獸 | From lore source |
| 岩地、殘骸或沙丘側邊 | 荒野弩手 | From lore source |
| 荒境高空 | 裂風猛禽 | From lore source |
| 旅人荒境沙層之下 | 沙塵異獸 | From lore source |
| 乾裂岩地與熱風區域 | 乾裂巨蜥 | From lore source |
| 旅人荒境高處岩壁與風蝕峽谷 | 裂風獅鷲 | From lore source |

---

## Chapter 02 Monster Master Table

| Monster ID | Monster Name | Source Type | Threat Level | Region Distribution | Civilization |
|---|---|---|---|---|---|
| MON_CH02_NORMAL_001 | 荒野鬣犬 / Wasteland Hyena | Normal | Normal | 荒境 | Wasteland Predator Civilization |
| MON_CH02_NORMAL_002 | 流浪掠奪者 / Wandering Raider | Normal | Normal | 荒境商路 | Wasteland Raider Civilization |
| MON_CH02_NORMAL_003 | 沙塵蜥蜴 / Dust Lizard | Normal | Normal | 乾涸的荒地 | Wasteland Predator Civilization |
| MON_CH02_NORMAL_004 | 裂風幼鳥 / Riftwind Chick | Normal | Normal | 岩石間 | Riftwind Avian Civilization |
| MON_CH02_NORMAL_005 | 荒野飛蟲 / Wasteland Insect | Normal | Normal | 腐敗屍骸、乾裂獸骨與荒野水源附近 | Wasteland Insect Swarm Civilization |
| MON_CH02_NORMAL_006 | 異化旅獸 / Mutated Caravan Beast | Normal | Normal | 旅人荒境裡 | Mutated Beast Civilization |
| MON_CH02_SPECIAL_001 | 荒野弩手 / Wasteland Crossbowman | Special | Normal | 岩地、殘骸或沙丘側邊 | Wasteland Raider Civilization |
| MON_CH02_SPECIAL_002 | 裂風猛禽 / Riftwind Raptor | Special | Normal | 荒境高空 | Riftwind Avian Civilization |
| MON_CH02_SPECIAL_003 | 沙塵異獸 / Dust Aberration | Special | Normal | 旅人荒境沙層之下 | Mutated Beast Civilization |
| MON_CH02_ELITE_001 | 荒野處刑者 / Wasteland Executioner | Elite | Elite | 旅人荒境 | Wasteland Raider Civilization |
| MON_CH02_ELITE_002 | 裂風獵鷹 / Riftwind Falcon | Elite | Elite | 荒境高空與風沙氣流 | Riftwind Avian Civilization |
| MON_CH02_ELITE_003 | 乾裂巨蜥 / Cracked Giant Lizard | Elite | Elite | 乾裂岩地與熱風區域 | Wasteland Predator Civilization |
| MON_CH02_BOSS_001 | 裂風獅鷲 / Riftwind Gryphon | Boss | Boss | 旅人荒境高處岩壁與風蝕峽谷 | Sky Apex Predator Civilization |

---

## Normal Monsters

### MON_CH02_NORMAL_001 - 荒野鬣犬 / Wasteland Hyena

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 荒境
- Civilization: Wasteland Predator Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 荒野鬣犬.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Wasteland Predator Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 鬣犬類; Idle Rule > 野獸; Attack Rule; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 荒境掠食獸.

#### Lore

- World Position: 在荒境中喜愛群體活動獵捕生物。
- Personality: 狡猾的群聚掠食者，擅長觀察受傷與流血獵物，會包圍並持續追擊虛弱目標。
- Entry Feeling: 從居中位置左側緊盯獵物繞到右側後回到中間。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 鬣狗頭部、露齒、嘴角殘留獵物毛髮。
- Weapon Recognition: 利牙撕咬。
- Body Shape: 中小型、前高後低。
- Posture: 繞圈觀察、低頭追蹤。
- Visual Outline: 樣貌與非洲鬣狗一般，嘴角還帶著被獵捕生物的毛髮。

#### Color

- Source Color Direction: 沙黃棕、灰褐色。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 荒境掠食獸.

#### Animation

- Dynamic Recognition: 繞行、撲咬、持續追擊。
- Combat Style: 優先專注擁有「流血」Debuff 的敵方，會張口撕咬傷口並持續追擊虛弱目標。
- Idle: 上下呼吸起伏，不時像狗一樣甩甩頭。
- Death: 向右側傾倒後，四肢小幅度擺動停止。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 風乾獸皮 | `monster_material_master_database.md` |  |
| 鬣犬尖牙 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: none for reference layer

---

### MON_CH02_NORMAL_002 - 流浪掠奪者 / Wandering Raider

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 荒境商路
- Civilization: Wasteland Raider Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 流浪掠奪者.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Wasteland Raider Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 流浪掠奪者; Humanoid Type Rules > 荒境人類系; Idle Rule > 人形; Attack Rule; Death Rule > 人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 荒境掠奪者.

#### Lore

- World Position: 荒境商路上的流浪掠奪者，常伏擊旅團與商隊，靠搶奪補給與舊裝備維生。
- Personality: 謹慎、貪婪、擅長利用風沙掩護，遇到弱者會主動逼近，遇到強敵則保持距離試探。
- Entry Feeling: 直視敵人，將手上的彎刀向上拋擲一圈準備戰鬥。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 土黃色頭巾、面部半遮蔽。
- Weapon Recognition: 單手彎刀。
- Body Shape: 中型、精瘦。
- Posture: 保持距離、試探接近。
- Visual Outline: 頭部披著土黃色頭巾將面部覆蓋，身著同色系服裝稍有污染感，深色護腕略顯突兀，單手持著大幅度彎刀。

#### Color

- Source Color Direction: 沙黃、土棕、深色護腕。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 荒境掠奪者.

#### Animation

- Dynamic Recognition: 彎刀甩動、試探、快速劈砍。
- Combat Style: 左手抓一把沙塵丟向敵方，右手接著劈下彎刀。
- Idle: 上下呼吸擺動，蹲下抓一把沙子準備下一次進攻。
- Death: 向後傾倒。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 舊鐵扣 | `monster_material_master_database.md` |  |
| 掠奪者護腕 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: none for reference layer

---

### MON_CH02_NORMAL_003 - 沙塵蜥蜴 / Dust Lizard

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 乾涸的荒地
- Civilization: Wasteland Predator Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 沙塵蜥蜴.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Wasteland Predator Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 爬行類; Idle Rule > 野獸; Attack Rule; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 荒境掠食獸.

#### Lore

- World Position: 在乾涸的荒地，因靈巧的身軀捕食著小型生物。
- Personality: 警覺性高、行動靈巧，會抬頭觀察獵物動向，依靠尾刺與毒素壓制小型獵物。
- Entry Feeling: 迅捷地爬入場中，抬頭備戰，尾巴微微抬起。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 細長蜥蜴頭。
- Weapon Recognition: 尾部掃擊、啃咬。
- Body Shape: 低矮爬行類。
- Posture: 貼地移動、快速竄行。
- Visual Outline: 稍微年幼的蜥蜴，身體稍微纖瘦輕盈，頭頸伸得高高地，深綠色身軀，類似鱷魚的大口，尾巴末端左右側附帶棘刺。

#### Color

- Source Color Direction: 沙黃、岩石灰、乾裂棕。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 荒境掠食獸.

#### Animation

- Dynamic Recognition: 快速爬行、甩尾。
- Combat Style: 用尾巴的尖刺甩向敵方並附帶些許毒素。
- Idle: 上下呼吸擺動，緊盯獵物。
- Death: 四肢先癱軟伏地後，頭頸與尾巴自然垂下落地。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 乾裂甲殼 | `monster_material_master_database.md` |  |
| 蜥蜴尾棘 | `monster_material_master_database.md` |  |
| 沙化核心 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: none for reference layer

---

### MON_CH02_NORMAL_004 - 裂風幼鳥 / Riftwind Chick

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 岩石間
- Civilization: Riftwind Avian Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 裂風幼鳥.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Riftwind Avian Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 飛禽類; Idle Rule > 野獸; Attack Rule; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 裂風鳥系.

#### Lore

- World Position: 因成鳥皆在岩石間築巢，還不會飛行的年幼體，靠著強壯的下肢追捕小蟲及小生物。
- Personality: 好奇但具有攻擊性，尚未成熟，遇到威脅時會用跳躍與利爪本能反擊。
- Entry Feeling: 走到位置中間後看到敵人，跳躍拍打翅膀準備應戰。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 幼鳥頭部、短鳥喙。
- Weapon Recognition: 下肢利爪。
- Body Shape: 小型鳥類。
- Posture: 左右觀察、警戒感。
- Visual Outline: 類似火雞的體態但下肢壯碩，因幼體關係鳥喙仍是淡黃色，羽毛以白灰色為主，頭頂有一束稍短的紅色羽毛。

#### Color

- Source Color Direction: 淺棕、沙黃、淡紅羽色。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 裂風鳥系.

#### Animation

- Dynamic Recognition: 跳躍、拍翅、爪擊。
- Combat Style: 利用下肢利爪向前撲擊。
- Idle: 頭部左右轉動，像雞一樣鎖定獵物。
- Death: 被最後一擊打到彈起，落地後癱軟。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 裂風羽毛 | `monster_material_master_database.md` |  |
| 幼鳥翼羽 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: none for reference layer

---

### MON_CH02_NORMAL_005 - 荒野飛蟲 / Wasteland Insect

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 腐敗屍骸、乾裂獸骨與荒野水源附近
- Civilization: Wasteland Insect Swarm Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 荒野飛蟲.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Wasteland Insect Swarm Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Global Monster Animation Rule; Animation Readability Rule; Idle Rule; Attack Rule; Death Rule.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Global Monster Color Rule; Color Hierarchy Rule; source color from `MONSTER_SILHOUETTE_BIBLE.md` Chapter 02 Monster Table.

#### Lore

- World Position: 棲息於腐敗屍骸、乾裂獸骨與荒野水源附近，常追隨受傷生物與旅團足跡出現的小型群聚飛蟲。
- Personality: 膽小但擾人，依靠群體騷擾獵物，喜歡圍繞傷口、腐肉與潮濕氣味盤旋。
- Entry Feeling: 一小群飛蟲先分散飛入，再逐漸聚攏靠近目標。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 蒼蠅型頭部、複眼。
- Weapon Recognition: 蟲群撲擊。
- Body Shape: 小型飛蟲群。
- Posture: 聚散不定、群聚行動。
- Visual Outline: 有著蜻蜓大小的身軀，類似蒼蠅的樣貌，總是一小群出沒。

#### Color

- Source Color Direction: 黑灰、暗褐、透明薄翼。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Global Monster Color Rule; Color Hierarchy Rule; source color from `MONSTER_SILHOUETTE_BIBLE.md` Chapter 02 Monster Table.

#### Animation

- Dynamic Recognition: 盤旋、群聚、Swarm Burst。
- Combat Style: 群體瞬間撲擊（swarm burst）騷擾敵人，未來可作為小幅中毒或命中干擾來源。
- Idle: 左右盤旋、高低漂浮，偶爾分散又聚攏。
- Death: 蟲群被擊散，少量薄翼與黑點殘影飄落後消散。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 風化骨片 | `monster_material_master_database.md` |  |
| 飛蟲薄翼 | `monster_material_master_database.md` |  |
| 風蝕結晶 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: none for reference layer

---

### MON_CH02_NORMAL_006 - 異化旅獸 / Mutated Caravan Beast

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 旅人荒境裡
- Civilization: Mutated Beast Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 異化旅獸.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Mutated Beast Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 巨獸類; Idle Rule > 野獸; Attack Rule; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Pollution Civilization Colors > Mutated Beast Civilization 的異化側.

#### Lore

- World Position: 在旅人荒境裡專門攻擊商隊馬匹。
- Personality: 憑藉震動聲響察覺商隊與馬匹位置，會耐心尾隨後突然襲擊，專門攻擊脖頸等脆弱部位。
- Entry Feeling: 迅捷地跑到定位準備進攻。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 異化獸角、扭曲獸面。
- Weapon Recognition: 巨角衝撞、重壓。
- Body Shape: 大型四足獸。
- Posture: 低頭蓄力、重踏。
- Visual Outline: 跟馬差不多高，結實的體格、粗壯脖頸，頭部有像牛的尖角，一口大嘴配上鋒利尖牙，背脊兩側均有甲殼防護。

#### Color

- Source Color Direction: 沙棕、暗褐、異化灰黑。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Pollution Civilization Colors > Mutated Beast Civilization 的異化側.

#### Animation

- Dynamic Recognition: 衝撞、重踏、壓迫前進。
- Combat Style: 藉著有力的下顎張口啃咬。
- Idle: 搭配呼吸感張口咬合。
- Death: 甩動頭頸向左側摔倒，脖子的傷口稍微流出鮮血。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 乾裂甲殼 | `monster_material_master_database.md` |  |
| 異化獸角 | `monster_material_master_database.md` |  |
| 荒野異核 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: none for reference layer

---

## Special Source Monsters

### MON_CH02_SPECIAL_001 - 荒野弩手 / Wasteland Crossbowman

#### Identity

- Source Type: Special
- Threat Level: Normal
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 岩地、殘骸或沙丘側邊
- Civilization: Wasteland Raider Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 荒野弩手.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Wasteland Raider Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 荒野弩手; Humanoid Type Rules > 荒境人類系; Attack Rule > 弓弩射擊; Death Rule > 人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 荒境掠奪者.

#### Lore

- World Position: 與流浪掠奪者同一族群，負責遠距離壓制與商隊狩獵，通常躲在岩地、殘骸或沙丘側邊支援掠奪行動。
- Personality: 冷靜、耐心、帶有獵手習性，不喜歡正面接戰，習慣觀察後再出手。
- Entry Feeling: 在機弩尚未上弦狀態下瞄準敵人，接著拉弓上弦準備戰鬥。
- Party Note: 「旅者說：看見風沙裡有反光時，最好先低頭。」

#### Silhouette

- Head Recognition: 頭巾包覆、荒境射手感。
- Weapon Recognition: 十字弩。
- Body Shape: 中型人類。
- Posture: 穩定瞄準。
- Visual Outline: 服裝與流浪掠奪者相仿，頭部仍被土黃色頭巾包覆，雙手持十字弩，背部掛著箭袋與簡易補給包。
- Silhouette Recognition Focus: 荒境遠程單位。

#### Color

- Source Color Direction: 沙黃、深棕。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 荒境掠奪者.

#### Animation

- Dynamic Recognition: 裝填、瞄準、射擊。
- Combat Style: 拉上弓弦後尋找時機瞄準射擊，偏好攻擊生命較低、正在施法或處於弱勢狀態的目標。
- Idle: 呼吸帶動身體上下起伏，不時摸索箭袋重新上弦。
- Death: 向後倒下，弩弓破碎落地。

#### Combat Readability

- Target Line: SOURCE MISSING.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 舊鐵扣 | `monster_material_master_database.md` |  |
| 破損弩機 | `monster_material_master_database.md` |  |
| 古代箭頭 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: individual Target Line usage

---

### MON_CH02_SPECIAL_002 - 裂風猛禽 / Riftwind Raptor

#### Identity

- Source Type: Special
- Threat Level: Normal
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 荒境高空
- Civilization: Riftwind Avian Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 裂風猛禽.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Riftwind Avian Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 飛禽類; Idle Rule > 野獸; Attack Rule; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 裂風鳥系.

#### Lore

- World Position: 裂風幼鳥的成年體，長期盤旋於荒境高空，以旅團、小型獸與飛蟲為食。
- Personality: 冷靜、耐心、具掠食者觀察習性，習慣先盤旋觀察弱點再俯衝。
- Entry Feeling: 從空中盤旋下降，於場中短暫振翅後停留。
- Party Note: 「當頭頂只剩盤旋黑影時，多半已經太晚。」

#### Silhouette

- Head Recognition: 紅色羽冠、尖鳥喙。
- Weapon Recognition: 利爪、鳥喙。
- Body Shape: 大型猛禽。
- Posture: 高處觀察。
- Visual Outline: 接近禿鷹體型，頭頂紅色羽毛更成熟，黃與深棕羽毛交錯，鮮黃色鳥喙，翅膀尾端帶少許鮮紅羽毛。
- Silhouette Recognition Focus: 裂風鳥系成熟體。

#### Color

- Source Color Direction: 深棕、沙黃、暗紅羽紋。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 裂風鳥系.

#### Animation

- Dynamic Recognition: 振翅、俯衝、撕裂。
- Combat Style: 對目標進行俯衝，以鳥喙突刺與利爪撕裂攻擊，偏好受傷或低生命值目標。
- Idle: 原地振翅，頭部左右觀察，偶爾低鳴。
- Death: 振翅失衡，墜落後向前撲倒。

#### Combat Readability

- Target Line: SOURCE MISSING.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 裂風羽毛 | `monster_material_master_database.md` |  |
| 猛禽利爪 | `monster_material_master_database.md` |  |
| 裂風核心 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: individual Target Line usage

---

### MON_CH02_SPECIAL_003 - 沙塵異獸 / Dust Aberration

#### Identity

- Source Type: Special
- Threat Level: Normal
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 旅人荒境沙層之下
- Civilization: Mutated Beast Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 沙塵異獸.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Mutated Beast Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Global Monster Animation Rule; Animation Readability Rule; Idle Rule; Attack Rule; Death Rule.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Pollution Civilization Colors > Mutated Beast Civilization 的異化側.

#### Lore

- World Position: 潛伏於旅人荒境沙層之下，等待獵物誤入範圍後伏擊的掠食者。
- Personality: 極具耐性與埋伏本能，不急躁，習慣等待敵人放鬆戒心後突然襲擊。
- Entry Feeling: 地面先鬆動並翻起沙塵，接著從沙土中跳躍而出。
- Party Note: 「荒境最危險的，往往不是你看見的東西。」

#### Silhouette

- Head Recognition: 異化沙獸頭部.
- Weapon Recognition: 巨爪、異化肢體.
- Body Shape: 不規則大型異獸.
- Posture: 前傾壓迫.
- Visual Outline: 貌似巨大蠍型生物，體型接近成人大小，背甲帶有尖刺，一大一小的鉗子形成不對稱壓迫感.
- Silhouette Recognition Focus: 荒境異化代表生物.

#### Color

- Source Color Direction: 沙黃、灰褐、晶石色.
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Pollution Civilization Colors > Mutated Beast Civilization 的異化側.

#### Animation

- Dynamic Recognition: 衝擊、重壓.
- Combat Style: 利用尾巴倒勾刺擊與鉗子揮擊，偏向打亂敵方節奏與壓迫近距離目標.
- Idle: 巨鉗緩慢開合，尾刺輕微晃動，偶爾發出甲殼摩擦聲.
- Death: 先跪伏後癱軟，原先高舉的尾巴最後才失力垂下.

#### Combat Readability

- Target Line: SOURCE MISSING.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 沙塵晶石 | `monster_material_master_database.md` |  |
| 沙獸尖殼 | `monster_material_master_database.md` |  |
| 荒漠異骨 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: individual Target Line usage

---

## Elite Monsters

### MON_CH02_ELITE_001 - 荒野處刑者 / Wasteland Executioner

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 旅人荒境
- Civilization: Wasteland Raider Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 荒野處刑者.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Wasteland Raider Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 荒野處刑者; Humanoid Type Rules > 荒境人類系; Attack Rule > 重武器; Death Rule > 人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 荒境掠奪者; Elite Monster Color Rule.

#### Encounter Identity

- Encounter Type: Elite
- Encounter Method: Weighted random encounter
- Encounter Role: 高階執行者
- Spawn Context: 流浪掠奪者中的高階執行者

#### Lore

- World Position: 流浪掠奪者中的高階執行者，負責夜間暗殺、商隊清剿與背叛者處決。
- Personality: 冷靜、殘忍、耐心，喜歡觀察敵方虛弱時刻後迅速出手，不浪費體力與動作。
- Entry Feeling: 緩步走入場中，低頭擦拭刀刃後抬頭直視敵人。
- Party Note: 「有人說，他們總在風停時出現。」

#### Silhouette

- Head Recognition: 遮面頭巾、處刑者輪廓。
- Weapon Recognition: 巨型處刑重刃。
- Body Shape: 大型人類。
- Posture: 緩慢逼近、壓迫感。
- Visual Outline: 屬於刺客形象，不再配戴頭巾，暗色系服裝混有風沙磨損感，手持沉重處刑刃，身形精瘦但危險。
- Silhouette Recognition Focus: 荒境處刑者。

#### Color

- Source Color Direction: 深棕、鐵灰、暗紅。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Bandit Civilization Colors > 荒境掠奪者; Elite Monster Color Rule.

#### Animation

- Dynamic Recognition: 重劈、前壓。
- Combat Style: 偏好追擊生命值較低或處於異常狀態的敵方，利用高速斬擊與沉重處刑攻擊壓制目標。
- Idle: 緩慢呼吸，手指輕敲刀柄，偶爾甩掉刀刃上的沙塵。
- Death: 半跪後失去支撐向側邊倒下，武器沉重落地。

#### Combat Readability

- Focus Queue Priority: Elite Skill.
- Threat Marker: Use low-presence threat marker only.
- Target Line: SOURCE MISSING.
- Forbidden: no giant warning FX; no visual spam.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 舊鐵扣 | `monster_material_master_database.md` |  |
| 處刑重刃碎片 | `monster_material_master_database.md` |  |
| 流亡徽章 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: specific skill name; individual Target Line usage

---

### MON_CH02_ELITE_002 - 裂風獵鷹 / Riftwind Falcon

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 荒境高空與風沙氣流
- Civilization: Riftwind Avian Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 裂風獵鷹.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Riftwind Avian Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 飛禽類; Idle Rule > 野獸; Attack Rule; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 裂風鳥系; Elite Monster Color Rule > 野獸精英.

#### Encounter Identity

- Encounter Type: Elite
- Encounter Method: Weighted random encounter
- Encounter Role: 天空掠食支配者
- Spawn Context: 裂風猛禽的成熟個體

#### Lore

- World Position: 裂風猛禽的成熟個體，已完全適應荒境高空與風沙氣流，是旅人荒境上空的掠食支配者。
- Personality: 極度冷靜、自信且富狩獵智慧，會長時間觀察目標並等待最佳俯衝時機。
- Entry Feeling: 高空盤旋數圈後急速下降，掀起風沙停留於場中。
- Party Note: 「牠不急著殺你，只是等你先露出疲態。」

#### Silhouette

- Head Recognition: 長羽冠、尖銳鳥喙。
- Weapon Recognition: 利爪、鳥喙。
- Body Shape: 大型飛禽。
- Posture: 高傲俯視。
- Visual Outline: 比裂風猛禽更巨大，羽毛由深棕與沙黃色構成，紅色羽冠更長更鮮明，鳥喙更加尖長銳利，雙翼末端帶有深紅色風蝕羽紋。
- Silhouette Recognition Focus: 天空掠食支配者。

#### Color

- Source Color Direction: 深棕、沙黃、深紅羽紋。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 裂風鳥系; Elite Monster Color Rule > 野獸精英.

#### Animation

- Dynamic Recognition: 高速俯衝、撕裂。
- Combat Style: 高速俯衝攻擊與利爪撕裂，偏好追擊低生命值、受傷或正在施放技能的敵方。
- Idle: 原地微振翅維持平衡，頭部高傲地左右觀察，偶爾發出低沉鳴叫。
- Death: 翅膀失速後向地面重重墜落，羽毛散落。

#### Combat Readability

- Focus Queue Priority: Elite Skill.
- Threat Marker: Use low-presence threat marker only.
- Target Line: SOURCE MISSING.
- Forbidden: no giant warning FX; no visual spam.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 裂風羽毛 | `monster_material_master_database.md` |  |
| 獵鷹風翼 | `monster_material_master_database.md` |  |
| 天空結晶 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: specific skill name; individual Target Line usage

---

### MON_CH02_ELITE_003 - 乾裂巨蜥 / Cracked Giant Lizard

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 乾裂岩地與熱風區域
- Civilization: Wasteland Predator Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 乾裂巨蜥.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Wasteland Predator Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 爬行類; Beast Animation Rule > 巨獸類; Idle Rule > 野獸; Attack Rule; Death Rule > 野獸.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 荒境掠食獸; Elite Monster Color Rule > 野獸精英.

#### Encounter Identity

- Encounter Type: Elite
- Encounter Method: Weighted random encounter
- Encounter Role: 荒境大型爬行霸主
- Spawn Context: 沙塵蜥蜴的成熟體

#### Lore

- World Position: 沙塵蜥蜴的成熟體，荒境中的中大型掠食者，長期佔據乾裂岩地與熱風區域。
- Personality: 極具警覺性與地盤意識，習慣先觀察敵人後再突然爆發攻擊，對靠近領域者具有強烈敵意。
- Entry Feeling: 緩慢爬入場中，抬起頭頸掃視敵人，尾巴沉重拖行地面。
- Party Note: 「若你聽見尾巴拖地聲，通常代表牠已經看見你了。」

#### Silhouette

- Head Recognition: 巨型蜥蜴頭部。
- Weapon Recognition: 巨爪、重尾。
- Body Shape: 超大型爬行類。
- Posture: 厚重移動。
- Visual Outline: 體型明顯巨大化，深綠與沙黃色混雜甲殼，背部長出乾裂狀厚甲，頭頸更粗壯，尾刺變得更巨大且危險。
- Silhouette Recognition Focus: 荒境大型爬行霸主。

#### Color

- Source Color Direction: 乾裂土黃、岩石灰。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > 荒境掠食獸; Elite Monster Color Rule > 野獸精英.

#### Animation

- Dynamic Recognition: 重踏、甩尾、撲擊。
- Combat Style: 利用巨大尾刺橫掃與毒性撕咬進行壓制，偏好攻擊生命值較低或持續受傷的敵方。
- Idle: 厚重呼吸帶動全身起伏，尾巴偶爾拍打地面，緊盯目標。
- Death: 四肢先失力跪倒，頭頸與尾巴最後才緩慢垂落地面。

#### Combat Readability

- Focus Queue Priority: Elite Skill.
- Threat Marker: Use low-presence threat marker only.
- Target Line: SOURCE MISSING.
- Forbidden: no giant warning FX; no visual spam.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 乾裂甲殼 | `monster_material_master_database.md` |  |
| 巨蜥重皮 | `monster_material_master_database.md` |  |
| 遠古沙核 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: specific skill name; individual Target Line usage

---

## Boss Monsters

### MON_CH02_BOSS_001 - 裂風獅鷲 / Riftwind Gryphon

#### Identity

- Source Type: Boss
- Threat Level: Boss
- Chapter: Chapter 02 - 旅人荒境
- Region Distribution: 旅人荒境高處岩壁與風蝕峽谷
- Civilization: Sky Apex Predator Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 02 Monster Table > 裂風獅鷲.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 02 > Sky Apex Predator Civilization; Boss Civilization Rule > 裂風獅鷲.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Beast Animation Rule > 飛禽類; Boss Animation Rule > 裂風獅鷲; Idle Rule > Boss; Attack Rule; Death Rule > Boss.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > Sky Apex Predator Civilization; Boss Color Rule > 裂風獅鷲.

#### Encounter Identity

- Encounter Type: Boss
- Encounter Method: Weighted accumulated encounter
- Encounter Role: 天空領域霸主
- Weight Reset Rule: Reset after boss encounter
- Fixed Stage Boss: No

#### Lore

- World Position: 棲息於旅人荒境高處岩壁與風蝕峽谷中的稀有天空生物，被少數旅者視為荒境真正的領域霸主。極少現身，多數人只見過巨大陰影與留下的殘骸。成熟裂風獵鷹也會主動避開其領域。
- Personality: 高傲、冷靜、極具領域意識與狩獵智慧。通常先長時間觀察入侵者，只有在確認威脅、飢餓或領域遭侵犯時才會主動攻擊。習慣節省體力，但真正出手時具有極高爆發性。
- Entry Feeling: 遠處先傳來巨大陰影掠過與低沉鳴聲，風沙短暫改變方向。數秒後巨大身影自高空盤旋而下，雙翼掀起風壓與沙塵後落地，停駐場中並高傲俯視敵人。
- Party Note: 「有人走完整片荒境都沒見過牠，也有人只看見一次，就再也沒回來。」

#### Silhouette

- Head Recognition: 鷹首、巨大鳥喙、紅色羽冠。
- Weapon Recognition: 巨爪、鳥喙、俯衝攻擊。
- Body Shape: 超大型飛行獸、獅身鷹首。
- Posture: 高傲俯視、雙翼展開。
- Visual Outline: 具獅與猛禽融合特徵。前半身覆蓋風蝕羽毛與強壯猛禽前肢，後半身保有獅型肌肉輪廓與粗壯尾巴。雙翼巨大，羽色由沙黃、深棕與風蝕灰構成，部分羽毛帶有乾裂與風沙磨損痕跡。頭部兼具猛禽銳利與野獸壓迫感，巨大鳥喙與利爪具強烈威懾性。整體輪廓更偏向「荒境稀有猛獸」，而非一般飛禽放大版。
- Silhouette Recognition Focus: 巨翼＋鷹首＋獅身＋紅羽冠＝第二章天空霸主。

#### Color

- Source Color Direction: 深棕羽毛、沙黃色羽毛、深紅羽紋。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Beast Civilization Colors > Sky Apex Predator Civilization; Boss Color Rule > 裂風獅鷲.

#### Animation

- Dynamic Recognition: 高空盤旋、高速俯衝、巨翼拍擊。
- Combat Style: 利用高速俯衝、利爪撕裂與鳥喙重擊壓制敵人。偏好追擊生命值較低、受傷或處於弱勢狀態的目標；偶爾短暫升空重新觀察戰場後再發動突襲。整體節奏偏冷靜但具有強烈爆發威脅。
- Idle: 巨翼偶爾微幅展開調整平衡，頭部高傲俯視敵人，利爪輕抓地面，伴隨低沉呼吸與羽毛受風沙吹拂的細微擺動。
- Death: 雙翼先逐漸失去支撐垂落，沉重跪地後發出低鳴，頭部最後緩慢垂下，羽毛與沙塵被風緩慢帶走。

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
| 獅鷲風羽 | `monster_material_master_database.md` |  |
| 裂風之爪 | `monster_material_master_database.md` |  |
| 破空鳥喙 | `monster_material_master_database.md` |  |
| 天空殘翼 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter02_monster_lore.docx`
- Silhouette Source: `archive/chapter02_monster_silhouette_260606_150038.docx`
- Missing Fields: specific boss skill name; individual Target Line usage

---

## Chapter 02 Boss Core Positioning

Source text:

- 荒境稀有生物
- 天空領域霸主
- 非裂風鳥類成熟鏈
- 高空觀察型掠食者
- 旅人恐懼與傳聞來源
- 荒野文明中的稀少存在

Formal philosophy from source:

```text
牠不是裂風猛禽的最終型。
牠是：
「旅人荒境裡，極少數真正被記住名字的生物。」
```

---

## Missing Source Register

| Missing Data | Impact | Handling |
|---|---|---|
| Special monster individual Target Line usage | No source-specific skill targeting available | Marked as `SOURCE MISSING` |
| Elite / Boss individual skill names | Cannot define skill database entries | Marked as `SOURCE MISSING`; no skill names created |
| Elite / Boss individual Target Line usage | No source-specific skill targeting available | Marked as `SOURCE MISSING` |

