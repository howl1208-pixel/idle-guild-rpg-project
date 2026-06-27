# CHAPTER03_MONSTER_DATABASE.md

Version: v1
Status: Review Draft
Chapter: Chapter 03 - Skeleton Wasteland
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
- This document consolidates existing Chapter 03 monster sources only.
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
6. `archive/chapter03_monster_lore.docx`
7. `archive/chapter03_monster_silhouette_260606_145847.docx`
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
| Lore | `archive/chapter03_monster_lore.docx` | Consolidate only |
| Silhouette | `MONSTER_SILHOUETTE_BIBLE.md`; `archive/chapter03_monster_silhouette_260606_145847.docx` | Use approved silhouette Bible reference and Chapter 03 source row |
| Color | `MONSTER_COLOR_BIBLE.md`; `MONSTER_SILHOUETTE_BIBLE.md` | Use approved color Bible rule plus source color direction |
| Animation | `MONSTER_ANIMATION_BIBLE.md`; `archive/chapter03_monster_lore.docx`; `archive/chapter03_monster_silhouette_260606_145847.docx` | Use approved animation Bible rule plus source animation text |
| Civilization | `MONSTER_CIVILIZATION_BIBLE.md` | Use Chapter 03 civilization mapping where directly listed |
| Drops | `monster_material_master_database.md` | Material names only; no quantity, drop rate, weight, or numerical value |
| Threat Level | Approved hierarchy | Normal / Elite / Boss only |
| Region Distribution | Source text only | Do not add regions |

---

## Chapter Overview

- Chapter: Chapter 03
- Region: 骷髏荒原 / Skeleton Wasteland
- Closed Beta Scope: Chapter 01~05 only
- Encounter System: weighted random encounters
- Boss Encounter System: weighted accumulated encounter
- Fixed Boss Stage: No
- Chapter 06+ Handling: Out of scope

---

## Chapter 03 Region Distribution Matrix

This matrix uses only region / location wording present in approved sources.

| Source Region Text | Monsters Referenced | Notes |
|---|---|---|
| 骷髏荒原 | 骷髏戰士; 墓地食屍鬼; 亡魂祭司; 腐毒蜘蛛; 墮落弓兵; 荒原幽魂; 王國騎士殘魂・艾德倫; 黑霧祭司・維薩恩; 裂谷屍魔・格羅姆; 冥骨領主・莫爾加斯 | Chapter-wide source region |
| 白骨荒地 | 骷髏戰士; 墓地食屍鬼; 王國騎士殘魂・艾德倫; 冥骨領主・莫爾加斯 | From lore source |
| 腐化裂谷 | 墓地食屍鬼; 腐毒蜘蛛; 裂谷屍魔・格羅姆 | From lore source |
| 黑霧墓地 | 亡魂祭司; 荒原幽魂; 黑霧祭司・維薩恩; 冥骨領主・莫爾加斯 | From lore source |
| 墓地陰影 | 腐毒蜘蛛 | From lore source |
| 古戰場 | 骷髏戰士; 墮落弓兵; 王國騎士殘魂・艾德倫; 冥骨領主・莫爾加斯 | From lore source |
| 白骨荒地與黑霧墓地交界深處 | 冥骨領主・莫爾加斯 | From lore source |

---

## Chapter 03 Monster Master Table

| Monster ID | Monster Name | Source Type | Threat Level | Region Distribution | Civilization |
|---|---|---|---|---|---|
| MON_CH03_NORMAL_001 | 骷髏戰士 / Skeleton Warrior | Normal | Normal | 白骨荒地; 古戰場 | Skeleton Remnant Civilization |
| MON_CH03_NORMAL_002 | 墓地食屍鬼 / Grave Ghoul | Normal | Normal | 白骨荒地; 腐化裂谷 | Grave Ghoul Civilization |
| MON_CH03_NORMAL_003 | 亡魂祭司 / Wraith Priest | Normal | Normal | 黑霧墓地 | Black Fog Priest Civilization |
| MON_CH03_NORMAL_004 | 腐毒蜘蛛 / Rotvenom Spider | Normal | Normal | 腐化裂谷; 墓地陰影 | SOURCE MISSING |
| MON_CH03_NORMAL_005 | 墮落弓兵 / Fallen Archer | Normal | Normal | 古戰場 | Skeleton Remnant Civilization |
| MON_CH03_NORMAL_006 | 荒原幽魂 / Wasteland Wraith | Normal | Normal | 黑霧墓地 | Wraith Civilization |
| MON_CH03_ELITE_001 | 王國騎士殘魂・艾德倫 / Knight Revenant · Edren | Elite | Elite | 白骨荒地; 古戰場 | Fallen Kingdom Remnant Civilization |
| MON_CH03_ELITE_002 | 黑霧祭司・維薩恩 / Mist Priest · Vysarn | Elite | Elite | 黑霧墓地 | Black Fog Priest Civilization |
| MON_CH03_ELITE_003 | 裂谷屍魔・格羅姆 / Rift Ghoulfiend · Grom | Elite | Elite | 腐化裂谷 | Grave Ghoul Civilization |
| MON_CH03_BOSS_001 | 冥骨領主・莫爾加斯 / Morgas, Lord of Dreadbone | Boss | Boss | 白骨荒地與黑霧墓地交界深處 | Undead Lord Civilization |

---

## Normal Monsters

### MON_CH03_NORMAL_001 - 骷髏戰士 / Skeleton Warrior

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 白骨荒地; 古戰場
- Civilization: Skeleton Remnant Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 骷髏戰士.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 03 > Skeleton Remnant Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Undead Animation Rule > 骷髏系; Idle Rule > 亡靈; Attack Rule; Death Rule > 亡靈骷髏.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 骷髏殘兵.

#### Lore

- World Position: 白骨荒地中最常見的不死士兵，似乎仍殘留古戰場軍勢的行軍與戰鬥本能。
- Personality: 空洞、沉默、執著。沒有情緒，只依照殘留命令行動，即使肢體殘破仍會緩慢逼近敵人。
- Entry Feeling: 地面白骨輕微震動後，骸骨緩慢站起，拖著武器進入戰場。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 骷髏頭、空洞眼窩。
- Weapon Recognition: 生鏽長劍。
- Body Shape: 中型骷髏人形。
- Posture: 微前傾、穩定推進。
- Visual Outline: 人形骸骨，身上殘留鏽蝕王國盔甲與破損布甲，手持生鏽短劍或骨刃。骨架乾瘦但站姿仍保有士兵紀律感。

#### Color

- Source Color Direction: 骨白、鐵鏽灰。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 骷髏殘兵.

#### Animation

- Dynamic Recognition: 揮砍、推進。
- Combat Style: 穩定近戰壓力，利用普通斬擊與持續逼近建立消耗戰氛圍。
- Idle: 身體輕微晃動，骨節偶爾錯位發出聲響，武器拖行地面。
- Death: 骨架失去支撐後崩散，骨頭與武器掉落地面。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 白骨碎片 | `monster_material_master_database.md` |  |
| 骷髏碎骨 | `monster_material_master_database.md` |  |
| 生鏽骨刃 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: none for reference layer

---

### MON_CH03_NORMAL_002 - 墓地食屍鬼 / Grave Ghoul

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 白骨荒地; 腐化裂谷
- Civilization: Grave Ghoul Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 墓地食屍鬼.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 03 > Grave Ghoul Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Undead Animation Rule > 腐屍系; Idle Rule > 亡靈; Attack Rule; Death Rule > 腐屍.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 食屍鬼／腐屍.

#### Lore

- World Position: 徘徊於白骨荒地與腐化裂谷交界的腐敗亡者，以屍體與腐肉維生。
- Personality: 飢餓、焦躁、偏野獸化，會被血腥味與生命氣息吸引。
- Entry Feeling: 從屍骸或墓碑後低伏爬出，發出低沉喘息聲後快速逼近。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 扭曲頭部、尖牙外露。
- Weapon Recognition: 利爪與撕咬。
- Body Shape: 矮壯型怪物。
- Posture: 四肢彎曲、準備撲擊。
- Visual Outline: 佝僂的人形腐屍，四肢細長但肌肉扭曲，灰白腐敗皮膚帶有裂痕與暗紅血漬，嘴部與利爪充滿腐化痕跡。

#### Color

- Source Color Direction: 腐肉灰綠、暗褐。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 食屍鬼／腐屍.

#### Animation

- Dynamic Recognition: 爬行、飛撲。
- Combat Style: 高侵略近戰怪，以撕咬與爪擊施加腐敗壓力，偏向持續騷擾與低強度 Debuff 威脅。
- Idle: 身體微微抽動，頭部不自然傾斜，偶爾磨牙或抓地。
- Death: 身體抽搐後失力趴倒，腐敗液體滲出地面。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 荒原灰塵 | `monster_material_master_database.md` |  |
| 乾枯骨粉 | `monster_material_master_database.md` |  |
| 食屍鬼利爪 | `monster_material_master_database.md` |  |
| 腐敗血液 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: none for reference layer

---

### MON_CH03_NORMAL_003 - 亡魂祭司 / Wraith Priest

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 黑霧墓地
- Civilization: Black Fog Priest Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 亡魂祭司.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 03 > Black Fog Priest Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Undead Animation Rule > 黑霧祭司系; Idle Rule > 亡靈; Attack Rule > 法術; Death Rule > 幽魂.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 黑霧祭司.

#### Lore

- World Position: 黑霧墓地中殘留的亡者祭司，似乎仍在重複某場早已失去意義的祭儀。
- Personality: 執念深重、低語不止，像是不停誦念某段被遺忘的禱詞。
- Entry Feeling: 黑霧聚攏後逐漸形成人形輪廓，祭袍與法杖隨後浮現。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 枯骨面容、兜帽遮蔽。
- Weapon Recognition: 法杖與亡靈法術。
- Body Shape: 高瘦人形。
- Posture: 微漂浮、施法姿態。
- Visual Outline: 半腐朽祭司形象，披著破爛祭袍，部分軀體透明或露出骸骨，手持殘缺法杖與詛咒符紙。

#### Color

- Source Color Direction: 暗紫、灰黑、骨白。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 黑霧祭司.

#### Animation

- Dynamic Recognition: 舉杖施法、黑霧流動。
- Combat Style: Debuff／法術怪，利用詛咒與弱化效果建立第三章壓力與淨化教學。
- Idle: 身體微幅漂浮，祭袍下擺緩慢擺動，口中持續低語。
- Death: 身體化為黑霧散去，符紙燃燒後化灰，法杖落地碎裂。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 亡者布條 | `monster_material_master_database.md` |  |
| 靈魂碎片 | `monster_material_master_database.md` |  |
| 詛咒符紙 | `monster_material_master_database.md` |  |
| 亡者灰燼 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: none for reference layer

---

### MON_CH03_NORMAL_004 - 腐毒蜘蛛 / Rotvenom Spider

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 腐化裂谷; 墓地陰影
- Civilization: SOURCE MISSING

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 腐毒蜘蛛.
- Civilization Reference: SOURCE MISSING. `MONSTER_CIVILIZATION_BIBLE.md` Chapter 03 does not directly list 腐毒蜘蛛 under a civilization row.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Global Monster Animation Rule; Animation Readability Rule; Idle Rule; Attack Rule; Death Rule.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Global Monster Color Rule; Color Hierarchy Rule; source color from `MONSTER_SILHOUETTE_BIBLE.md` Chapter 03 Monster Table.

#### Lore

- World Position: 棲息於腐化裂谷與墓地陰影中的毒性節肢怪物，以腐敗血肉與黑暗氣息為養分。
- Personality: 謹慎、陰濕、耐心等待獵物露出破綻，偏本能型掠食者。
- Entry Feeling: 從骨堆或裂縫間快速爬出，腹部毒囊微微鼓動。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 多眼蜘蛛頭部。
- Weapon Recognition: 毒牙、蛛肢。
- Body Shape: 中型蜘蛛。
- Posture: 低伏地面。
- Visual Outline: 中型蜘蛛，腹部膨脹且帶暗綠毒囊，外殼灰黑混雜腐綠色紋路，肢體細長而尖銳。

#### Color

- Source Color Direction: 黑褐、毒綠。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Global Monster Color Rule; Color Hierarchy Rule; source color from `MONSTER_SILHOUETTE_BIBLE.md` Chapter 03 Monster Table.

#### Animation

- Dynamic Recognition: 快速爬行、噴毒。
- Combat Style: 中毒／DOT 壓力怪，利用毒液與持續傷害造成續戰壓力。
- Idle: 八足細微抖動，毒液偶爾滴落地面，腹部緩慢起伏。
- Death: 八足蜷縮，腹部毒囊破裂滲出腐綠液體。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 乾枯骨粉 | `monster_material_master_database.md` |  |
| 腐蝕石塊 | `monster_material_master_database.md` |  |
| 毒蛛毒液 | `monster_material_master_database.md` |  |
| 腐蝕蛛絲 | `monster_material_master_database.md` |  |
| 黑毒囊 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: direct civilization row

---

### MON_CH03_NORMAL_005 - 墮落弓兵 / Fallen Archer

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 古戰場
- Civilization: Skeleton Remnant Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 墮落弓兵.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 03 > Skeleton Remnant Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Undead Animation Rule > 骷髏系; Attack Rule > 弓弩射擊; Death Rule > 亡靈骷髏.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 骷髏殘兵.

#### Lore

- World Position: 古戰場死去的王國弓兵，被黑暗侵蝕後仍保留生前射擊本能。
- Personality: 沉默、機械化、像仍執行最後軍令般等待射擊時機。
- Entry Feeling: 黑霧中緩慢舉弓，拉弦後鎖定目標。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 骷髏頭、殘破頭盔。
- Weapon Recognition: 長弓。
- Body Shape: 中型骷髏人形。
- Posture: 側身拉弓。
- Visual Outline: 骸骨弓兵，身著殘破王國布甲與破碎羽飾，持有腐木長弓與黑羽箭矢。

#### Color

- Source Color Direction: 骨白、舊木棕。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 骷髏殘兵.

#### Animation

- Dynamic Recognition: 拉弓、射擊。
- Combat Style: 遠距離穩定壓力，偏好攻擊生命較低、施法中或弱勢目標（不採前後排邏輯）。
- Idle: 緩慢調整拉弦姿勢，箭矢周圍有淡黑霧殘留。
- Death: 弓弦斷裂，身體向後散落成碎骨。

#### Combat Readability

- Target Line: SOURCE MISSING.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 白骨碎片 | `monster_material_master_database.md` |  |
| 小型金幣袋 | `monster_material_master_database.md` |  |
| 黑羽箭矢 | `monster_material_master_database.md` |  |
| 腐木箭桿 | `monster_material_master_database.md` |  |
| 墮落羽毛 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: individual Target Line usage

---

### MON_CH03_NORMAL_006 - 荒原幽魂 / Wasteland Wraith

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 黑霧墓地
- Civilization: Wraith Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 荒原幽魂.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 03 > Wraith Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Undead Animation Rule > 幽魂系; Idle Rule > 亡靈; Attack Rule; Death Rule > 幽魂.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 幽魂.

#### Lore

- World Position: 黑霧墓地徘徊的亡者殘影，無法安息的靈體。
- Personality: 空洞、哀怨、迷失，會本能靠近活物並吸取生命氣息。
- Entry Feeling: 黑霧先於地面聚集，再緩慢升起化作人形。
- Party Note: 普通怪不顯示特殊描述。

#### Silhouette

- Head Recognition: 無明顯五官、幽魂輪廓。
- Weapon Recognition: 幽體衝擊。
- Body Shape: 漂浮靈體。
- Posture: 半透明漂浮。
- Visual Outline: 半透明幽魂輪廓，下半身逐漸化為黑霧，人形輪廓模糊，眼部散發淡藍或幽綠微光。

#### Color

- Source Color Direction: 幽藍、灰白、黑霧。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 幽魂.

#### Animation

- Dynamic Recognition: 飄浮、穿梭、消散。
- Combat Style: 幽體／法術壓力怪，具幽體機制：物理傷害降低30%、魔法正常，不完全免疫近戰。
- Idle: 身體微幅漂浮，輪廓忽明忽暗，偶爾發出無聲哀鳴。
- Death: 形體被撕裂為霧氣，雙眼幽光最後熄滅。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 亡者布條 | `monster_material_master_database.md` |  |
| 荒原灰塵 | `monster_material_master_database.md` |  |
| 幽魂殘片 | `monster_material_master_database.md` |  |
| 靈界塵埃 | `monster_material_master_database.md` |  |
| 冥火微粒 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: none for reference layer

---

## Elite Monsters

### MON_CH03_ELITE_001 - 王國騎士殘魂・艾德倫 / Knight Revenant · Edren

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 白骨荒地; 古戰場
- Civilization: Fallen Kingdom Remnant Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 王國騎士殘魂・艾德倫.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 03 > Fallen Kingdom Remnant Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Undead Animation Rule > 幽魂系; Humanoid Animation Rule > 王國士兵系; Attack Rule; Death Rule > 重甲人形.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Kingdom Civilization Colors > 王國殘魂; Undead Civilization Colors > 幽魂.

#### Encounter Identity

- Encounter Type: Elite
- Encounter Method: Weighted random encounter
- Encounter Role: 高防壓迫型精英
- Spawn Context: 白骨荒地殘存的王國亡軍指揮者

#### Lore

- World Position: 白骨荒地殘存的王國亡軍指揮者，生前為王國騎士，死後仍徘徊於古戰場守護早已毀滅的軍令與榮耀。
- Personality: 沉默、執著、帶有軍人紀律與亡軍意志。即使已死亡仍維持守軍姿態，不會輕易後退。
- Entry Feeling: 地面傳出沉重腳步聲與金屬摩擦聲，黑霧中高大騎士輪廓逐漸浮現，將長劍重重插地後進入戰鬥。
- Party Note: 「有人說，他到現在仍以為王國沒有滅亡。」

#### Silhouette

- Head Recognition: 王國騎士頭盔、魂火眼眶。
- Weapon Recognition: 長劍＋騎士盾。
- Body Shape: 高大騎士輪廓。
- Posture: 正面守護姿態。
- Visual Outline: 身披殘破厚重王國鎧甲，部分盔甲鏽蝕崩裂，身體由殘魂與骸骨構成。披風破損且被黑霧侵蝕，手持巨大騎士長劍，頭盔眼窩散發幽藍魂火。
- Silhouette Recognition Focus: 騎士亡魂。

#### Color

- Source Color Direction: 銀灰、幽藍。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Kingdom Civilization Colors > 王國殘魂; Undead Civilization Colors > 幽魂.

#### Animation

- Dynamic Recognition: 穩定推進、劍擊。
- Combat Style: 高防壓迫型精英，以穩定近戰與亡軍號令支援周圍不死怪，形成消耗戰壓力。
- Idle: 緩慢呼吸般的魂火閃爍，鎧甲偶爾發出金屬碰撞聲，長劍沉重拖地。
- Death: 單膝跪地後長劍插地支撐，魂火逐漸熄滅，鎧甲最後崩散倒下。

#### Combat Readability

- Focus Queue Priority: Elite Skill.
- Threat Marker: Use low-presence threat marker only.
- Target Line: SOURCE MISSING.
- Forbidden: no giant warning FX; no visual spam.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 白骨碎片 | `monster_material_master_database.md` |  |
| 亡軍徽章 | `monster_material_master_database.md` |  |
| 騎士殘甲 | `monster_material_master_database.md` |  |
| 王國殘鐵 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: specific skill name; individual Target Line usage

---

### MON_CH03_ELITE_002 - 黑霧祭司・維薩恩 / Mist Priest · Vysarn

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 黑霧墓地
- Civilization: Black Fog Priest Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 黑霧祭司・維薩恩.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 03 > Black Fog Priest Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Undead Animation Rule > 黑霧祭司系; Idle Rule > 亡靈; Attack Rule > 法術; Death Rule > 幽魂.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 黑霧祭司.

#### Encounter Identity

- Encounter Type: Elite
- Encounter Method: Weighted random encounter
- Encounter Role: 高 Debuff 壓力精英
- Spawn Context: 黑霧墓地的高階死靈祭司

#### Lore

- World Position: 黑霧墓地的高階死靈祭司，傳聞其曾主持某場禁忌儀式，使整片墓地長年被黑霧壟罩。
- Personality: 冷漠、執念深重、帶有儀式感，像在觀察敵人是否值得被獻祭。
- Entry Feeling: 黑霧於地面擴散旋轉，祭司輪廓從霧中浮現，法杖敲擊地面後開始低語。
- Party Note: 「有人懷疑，墓地裡那些低語，其實一直來自同一個人。」

#### Silhouette

- Head Recognition: 遮面兜帽。
- Weapon Recognition: 黑霧法杖。
- Body Shape: 高瘦施法者。
- Posture: 微漂浮施法。
- Visual Outline: 高瘦人形，身披厚重暗色祭袍，部分軀體虛化，胸口與法杖纏繞黑霧符文，面容被陰影與詛咒遮蔽。
- Silhouette Recognition Focus: 黑霧核心輪廓。

#### Color

- Source Color Direction: 黑紫、暗灰。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 黑霧祭司.

#### Animation

- Dynamic Recognition: 黑霧擴散、施法。
- Combat Style: 高 Debuff 壓力精英，以侵蝕、降攻與弱化效果逐步消耗玩家，建立續戰壓力。
- Idle: 身體微幅漂浮，祭袍緩慢飄動，黑霧在身邊流轉。
- Death: 黑霧快速向內塌縮，祭袍失去支撐落地，法杖最後碎裂。

#### Combat Readability

- Focus Queue Priority: Elite Skill.
- Threat Marker: Use low-presence threat marker only.
- Target Line: SOURCE MISSING.
- Forbidden: no giant warning FX; no visual spam.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 黑霧結晶 | `monster_material_master_database.md` |  |
| 死靈法珠 | `monster_material_master_database.md` |  |
| 黑霧符紙 | `monster_material_master_database.md` |  |
| 冥界骨灰 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: specific skill name; individual Target Line usage

---

### MON_CH03_ELITE_003 - 裂谷屍魔・格羅姆 / Rift Ghoulfiend · Grom

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 腐化裂谷
- Civilization: Grave Ghoul Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 裂谷屍魔・格羅姆.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 03 > Grave Ghoul Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Undead Animation Rule > 腐屍系; Idle Rule > 亡靈; Attack Rule; Death Rule > 腐屍.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 食屍鬼／腐屍.

#### Encounter Identity

- Encounter Type: Elite
- Encounter Method: Weighted random encounter
- Encounter Role: 高 DOT／創傷壓力精英
- Spawn Context: 腐化裂谷深處異變的巨型亡者

#### Lore

- World Position: 腐化裂谷深處異變的巨型亡者，長年暴露於死亡污染與腐化氣息中，已失去原始物種樣貌。
- Personality: 暴躁、遲鈍、具有掠食本能，會本能壓迫所有靠近生命體。
- Entry Feeling: 地面先出現沉重震動與腐敗液體滲流，龐大身影拖著身軀走出裂谷陰影。
- Party Note: 「有人說，那不是活物，而是一整片腐敗學會了站起來。」

#### Silhouette

- Head Recognition: 巨大腐敗頭部。
- Weapon Recognition: 巨爪與重拳。
- Body Shape: 巨型屍魔。
- Posture: 前傾壓迫。
- Visual Outline: 巨大腐敗肉體與骸骨混合構成，身形厚重，部分骨刺穿出皮膚，體表覆蓋黑綠腐化組織與乾裂甲殼，身體持續滲出黑色毒液。
- Silhouette Recognition Focus: 大型腐屍輪廓。

#### Color

- Source Color Direction: 腐綠、暗褐、灰黑。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 食屍鬼／腐屍.

#### Animation

- Dynamic Recognition: 重踏、猛撲。
- Combat Style: 高 DOT／創傷壓力精英，以腐化爆裂、中毒與創傷逐步削弱玩家續戰能力。
- Idle: 厚重呼吸帶動全身腐肉起伏，毒液緩慢滴落地面，偶爾發出低沉嘶吼。
- Death: 身體沉重跪倒，腐敗組織崩裂塌陷，最後只剩殘骨與黑色液體。

#### Combat Readability

- Focus Queue Priority: Elite Skill.
- Threat Marker: Use low-presence threat marker only.
- Target Line: SOURCE MISSING.
- Forbidden: no giant warning FX; no visual spam.

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 腐化血塊 | `monster_material_master_database.md` |  |
| 屍魔重骨 | `monster_material_master_database.md` |  |
| 裂谷腐肉 | `monster_material_master_database.md` |  |
| 黑血毒液 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: specific skill name; individual Target Line usage

---

## Boss Monsters

### MON_CH03_BOSS_001 - 冥骨領主・莫爾加斯 / Morgas, Lord of Dreadbone

#### Identity

- Source Type: Boss
- Threat Level: Boss
- Chapter: Chapter 03 - 骷髏荒原
- Region Distribution: 白骨荒地與黑霧墓地交界深處
- Civilization: Undead Lord Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 03 Monster Table > 冥骨領主・莫爾加斯.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 03 > Undead Lord Civilization; Boss Civilization Rule > 冥骨領主・莫爾加斯.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Undead Animation Rule > 亡靈君王系; Boss Animation Rule > 冥骨領主・莫爾加斯; Idle Rule > Boss; Attack Rule; Death Rule > Boss.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 亡靈君王; Boss Color Rule > 冥骨領主・莫爾加斯.

#### Encounter Identity

- Encounter Type: Boss
- Encounter Method: Weighted accumulated encounter
- Encounter Role: 死亡荒原支配者
- Weight Reset Rule: Reset after boss encounter
- Fixed Stage Boss: No

#### Lore

- World Position: 白骨荒地與黑霧墓地交界深處徘徊的亡軍支配者。傳聞其曾是古王國戰爭中統率亡軍的大將，在死亡與詛咒侵蝕後仍持續守望著早已滅亡的戰場。其存在使骷髏荒原長年維持死亡與黑霧壓迫。
- Personality: 冷靜、沉重、帶有統率者氣質。極具耐性，不急於殺死敵人，而是透過消耗與壓迫讓敵人逐漸崩潰。彷彿仍在指揮一場永遠無法結束的戰爭。
- Entry Feeling: 戰場先傳出低沉號角殘響與鎧甲拖行聲，周圍黑霧開始聚集，白骨地面緩慢裂開。巨大身影自黑霧中步出，將武器重重插入地面後，冥火在眼窩中亮起。
- Party Note: 「有人說，他其實從未離開戰場，只是不再記得自己究竟守護著什麼。」

#### Silhouette

- Head Recognition: 巨大骸骨王冠、幽藍魂火雙眼。
- Weapon Recognition: 冥骨權杖、亡靈召喚。
- Body Shape: 超大型亡靈領主。
- Posture: 王者俯視姿態。
- Visual Outline: 巨大骸骨王者形象，體型明顯高於一般亡軍。身披破碎王國重甲與殘破披風，部分骨骼被黑霧與冥火纏繞。頭部戴著破損骨冠，眼窩燃燒深紫魂火，手持巨大殘缺王劍或冥骨戰刃。鎧甲帶有年代侵蝕與戰場磨損感，不走華麗魔王風格，而偏向「古戰場亡軍統帥」。
- Silhouette Recognition Focus: 王冠＋魂火雙眼＋亡靈君王。

#### Color

- Source Color Direction: 骨白、幽藍、黑紫。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Undead Civilization Colors > 亡靈君王; Boss Color Rule > 冥骨領主・莫爾加斯.

#### Animation

- Dynamic Recognition: 召喚、魂火流動、權杖重擊。
- Combat Style: 高 Debuff／續戰壓力 Boss。透過來源文字中的「冥河侵蝕」逐步施加侵蝕與群體壓力，並利用來源文字中的「死者呼喚」召喚少量骸骨士兵製造亡軍壓迫感。整體節奏偏穩定消耗戰，逐步測試玩家續戰能力與 Debuff 管理能力，而非瞬間爆發秒殺。
- Idle: 厚重站姿伴隨微幅魂火閃爍，殘破披風與黑霧緩慢飄動，偶爾低頭俯視敵人，武器尖端摩擦地面。
- Death: 單膝沉重跪地，武器支撐身體，眼中魂火逐漸熄滅。黑霧自骨骼縫隙逸散，最後骨冠與鎧甲崩落，巨大骨架失去支撐倒下。

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
| 冥王核心 | `monster_material_master_database.md` |  |
| 冥界王骨 | `monster_material_master_database.md` |  |
| 黑魂結晶 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter03_monster_lore.docx`
- Silhouette Source: `archive/chapter03_monster_silhouette_260606_145847.docx`
- Missing Fields: individual Target Line usage; formal skill database entries

---

## Chapter 03 Boss Core Positioning

Source text:

- 死亡荒原支配者
- 高 Debuff 壓力 Boss
- 消耗戰教學 Boss
- 小型召喚 Boss
- 亡軍文明核心存在
- 續戰能力檢查點

Formal philosophy from source:

```text
牠不是為了瞬間殺死你。
牠是：
「讓你明白，死亡荒原從來不打算讓任何人輕易活著離開。」
```

---

## Missing Source Register

| Missing Data | Impact | Handling |
|---|---|---|
| 腐毒蜘蛛 direct civilization row | `MONSTER_CIVILIZATION_BIBLE.md` Chapter 03 does not directly list 腐毒蜘蛛 under a civilization row | Marked as `SOURCE MISSING`; no civilization inferred |
| Fallen Archer individual Target Line usage | No source-specific skill targeting available | Marked as `SOURCE MISSING` |
| Elite individual skill names | Cannot define skill database entries | Marked as `SOURCE MISSING`; no skill names created |
| Elite / Boss individual Target Line usage | No source-specific skill targeting available | Marked as `SOURCE MISSING` |
| Boss formal skill database entries | Source text names boss actions, but no formal skill database entries are provided | Marked as `SOURCE MISSING`; no skill entries created |

