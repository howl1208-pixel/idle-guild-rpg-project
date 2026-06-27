# CHAPTER05_MONSTER_DATABASE.md

Version: v1
Status: Review Draft
Chapter: Chapter 05 - Holy Border
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
- This document consolidates existing Chapter 05 monster sources only.
- Missing data is marked as `SOURCE MISSING`.
- Drop Quantity is not recorded in this Monster Database.
- Drop rate is not recorded in this Monster Database.
- Drop weight is not recorded in this Monster Database.
- Drop numerical values are not recorded in this Monster Database.
- Drop materials must come from `monster_material_master_database.md`.
- Materials not present in `monster_material_master_database.md` must be marked as `未存在於 monster_material_master_database.md`.

---

## Source Priority

1. `AGENTS.md`
2. `GAME_CURRENT_VERSION.md`
3. `CURRENT_PROJECT_STATE.md`
4. `combat_system_current.md`
5. `CLASS_TREE_CURRENT.md`
6. `monster_database.md`
7. `archive/chapter05_monster_lore.docx`
8. `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
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
| Monster Names | `monster_database.md`; `MONSTER_SILHOUETTE_BIBLE.md`; `archive/Chapter 05_Monster_Silhouette _260606_150018.docx` | Use listed Chapter 05 monster names only |
| Lore | `archive/chapter05_monster_lore.docx` | Consolidate only; preserve source conflicts as review notes |
| Silhouette | `MONSTER_SILHOUETTE_BIBLE.md`; `archive/Chapter 05_Monster_Silhouette _260606_150018.docx` | Use approved silhouette Bible reference and Chapter 05 source row |
| Color | `MONSTER_COLOR_BIBLE.md`; `MONSTER_SILHOUETTE_BIBLE.md` | Use approved color Bible rule plus source color direction |
| Animation | `MONSTER_ANIMATION_BIBLE.md`; `archive/chapter05_monster_lore.docx`; `archive/Chapter 05_Monster_Silhouette _260606_150018.docx` | Use approved animation Bible rule plus source animation text |
| Civilization | `MONSTER_CIVILIZATION_BIBLE.md` | Use Chapter 05 civilization mapping where directly listed |
| Drops | `monster_material_master_database.md` | Material names only; no quantity, drop rate, weight, or numerical value |
| Threat Level | `MONSTER_SILHOUETTE_BIBLE.md`; `archive/chapter05_monster_lore.docx` | Normal / Special / Elite / Boss only |
| Region Distribution | Source text only | Do not add regions |

---

## Chapter Overview

- Chapter: Chapter 05
- Region: 聖堂國境 / Holy Border
- Closed Beta Scope: Chapter 01~05 only
- Encounter System: weighted random encounters
- Boss Encounter System: weighted accumulated encounter
- Fixed Boss Stage: No
- Chapter 06+ Handling: Out of scope
- Chapter Core: 真正的神聖文明，被某人扭曲
- Formal Philosophy: 玩家不是被欺騙，而是逐漸看見真相
- Boss Rule: 第五章 Boss 僅有白冠主教・薩維恩 / Savien, White-Crowned Bishop

---

## Chapter 05 Region Distribution Matrix

This matrix uses only region / location wording present in approved sources.

| Source Region Text | Monsters Referenced | Notes |
|---|---|---|
| 聖堂國境 | 聖堂守衛; 禁忌修士; 聖域巨兵; 聖羽巡禮者; 墮落審判者; 聖歌幽魂; 聖歌祭司; 黑袍審問官; 聖域裁決者; 聖槍隊長・雷昂; 墮落主教・薩菲爾; 聖域巨兵・瓦倫特; 白冠主教・薩維恩 | Chapter-wide source region |
| 國境與聖堂間 | 聖羽巡禮者 | From lore source |
| 聖堂核心區 | 聖域巨兵 | From lore source |
| 修道院與聖域 | 聖歌幽魂 | From lore source |
| 聖光邊境與王庭巡禮 | 聖歌祭司 | From lore source |
| 墮落修道院 | 黑袍審問官 | From lore source |
| 王國聖域 | 聖域裁決者; 聖域巨兵・瓦倫特 | From lore source |
| 聖光邊境前線 | 聖槍隊長・雷昂 | From lore source |
| 聖堂國境高階白冠主教位置 | 白冠主教・薩維恩 | From lore source |

---

## Chapter 05 Monster Master Table

| Monster ID | Monster Name | Source Type | Threat Level | Region Distribution | Civilization |
|---|---|---|---|---|---|
| MON_CH05_NORMAL_001 | 聖堂守衛 / Holy Guard | Normal | Normal | 聖堂國境 | Holy Guard Civilization |
| MON_CH05_NORMAL_002 | 禁忌修士 / Forbidden Monk | Normal | Normal | 聖堂國境 | Forbidden Monastery Civilization |
| MON_CH05_NORMAL_003 | 聖域巨兵 / Sanctum Giant Guard | Normal | Normal | 聖堂核心區 | Sanctum Construct Civilization |
| MON_CH05_NORMAL_004 | 聖羽巡禮者 / Holy Feather Pilgrim | Normal | Normal | 國境與聖堂間 | Holy Pilgrim Civilization |
| MON_CH05_NORMAL_005 | 墮落審判者 / Fallen Inquisitor | Normal | Normal | 聖堂國境 | Inquisition Civilization |
| MON_CH05_NORMAL_006 | 聖歌幽魂 / Hymn Wraith | Normal | Normal | 修道院與聖域 | Hymn Spirit Civilization |
| MON_CH05_SPECIAL_001 | 聖歌祭司 / Hymn Priest | Special | Normal | 聖光邊境與王庭巡禮 | Hymn Spirit Civilization |
| MON_CH05_SPECIAL_002 | 黑袍審問官 / Black-Robed Inquisitor | Special | Normal | 墮落修道院 | Inquisition Civilization |
| MON_CH05_SPECIAL_003 | 聖域裁決者 / Sanctum Adjudicator | Special | Normal | 王國聖域 | Sanctum Construct Civilization |
| MON_CH05_ELITE_001 | 聖槍隊長・雷昂 / Leon, Captain of the Holy Lance | Elite | Elite | 聖光邊境前線 | Holy Guard Civilization |
| MON_CH05_ELITE_002 | 墮落主教・薩菲爾 / Saphir, Fallen Bishop | Elite | Elite | 聖堂國境 | Fallen Bishop Civilization |
| MON_CH05_ELITE_003 | 聖域巨兵・瓦倫特 / Valent, Sanctum Giant | Elite | Elite | 王國聖域 | Sanctum Construct Civilization |
| MON_CH05_BOSS_001 | 白冠主教・薩維恩 / Savien, White-Crowned Bishop | Boss | Boss | 聖堂國境 | White Crown Authority Civilization |

---

## Normal Monsters

### MON_CH05_NORMAL_001 - 聖堂守衛 / Holy Guard

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 聖堂國境
- Civilization: Holy Guard Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 聖堂守衛.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Holy Guard Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule > 聖堂守衛系; Idle Rule > 聖堂系; Attack Rule; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖堂守衛.

#### Lore

- World Position: 聖堂國境最常見的武裝守衛，負責巡守國境、維護秩序與驅逐異端。
- Personality: 高度服從命令，幾乎不與他人交流，眼神過於平靜，像是在等待某種指示。
- Entry Feeling: 穩定步伐進場，長槍輕敲地面確認姿態。規律站姿與統一動作感較強，偶爾同步抬頭觀察戰場。
- Party Note: 「守衛們沉默而守序，只是旅者總覺得--他們安靜得不像人。」

#### Silhouette

- Head Recognition: 聖堂頭盔、王國聖徽。
- Weapon Recognition: 長槍＋小型護盾。
- Body Shape: 中大型人類士兵。
- Posture: 挺直站姿、紀律感強。
- Visual Outline: 身穿白銀與淡金配色輕重混合鎧甲，胸口帶有王國聖徽，披著略短白披風，手持長槍與小型護盾，頭盔輪廓整齊莊嚴。

#### Color

- Source Color Direction: 白銀、淡金、白披風。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖堂守衛.

#### Animation

- Dynamic Recognition: 長槍突刺、穩定推進。
- Combat Style: 穩定近戰，以簡潔槍擊與壓迫式步伐攻擊，節奏穩定、不追求爆發。
- Idle: 身體自然呼吸起伏，偶爾調整握槍姿勢，小幅左右觀察戰場。
- Death: 長槍先滑落地面，單膝跪地後失去支撐向側傾倒，保留軍人感。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 聖光碎片 | `monster_material_master_database.md` |  |
| 光輝金屬 | `monster_material_master_database.md` |  |
| 守衛長槍片 | `monster_material_master_database.md` |  |
| 聖徽碎片 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: none for reference layer

---

### MON_CH05_NORMAL_002 - 禁忌修士 / Forbidden Monk

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 聖堂國境
- Civilization: Forbidden Monastery Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 禁忌修士.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Forbidden Monastery Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule > 禁忌修士系; Idle Rule > 聖堂系; Attack Rule > 法術; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 禁忌修道.

#### Lore

- World Position: 原為修道院修士，受污染信仰影響後轉向禁忌祈禱與黑暗儀式。
- Personality: 長期沉浸於禁忌禱言中，不斷低聲誦念，像是在等待神諭，也像是在服從某種存在。
- Entry Feeling: 低頭吟誦後才緩慢抬頭，身體帶有些許不自然僵硬感。
- Party Note: 「修院深處的聲音從未停止，但已經很久沒有人真正離開。」

#### Silhouette

- Head Recognition: 蒼白面容、疲憊雙眼。
- Weapon Recognition: 殘破祈禱書。
- Body Shape: 中型瘦削人形。
- Posture: 微駝背、低頭誦讀。
- Visual Outline: 穿著破舊灰白修士袍，袍面帶黑色污痕與殘缺祈文，雙眼略帶疲憊與瘋狂感，手持殘破祈禱書。

#### Color

- Source Color Direction: 灰白、黑色污痕、暗灰。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 禁忌修道.

#### Animation

- Dynamic Recognition: 誦經、低語、施法。
- Combat Style: 使用禁忌祈文干擾敵人，降低對手穩定性，屬於高干擾型普通怪。
- Idle: 微幅晃動身體、嘴巴低聲誦讀，雙手偶爾緊握祈書。
- Death: 身體跪坐倒地，祈書掉落地面，殘破紙頁散落。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 禁忌符紙 | `monster_material_master_database.md` |  |
| 黑聖灰燼 | `monster_material_master_database.md` |  |
| 墮落祈文 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: none for reference layer

---

### MON_CH05_NORMAL_003 - 聖域巨兵 / Sanctum Giant Guard

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 聖堂核心區
- Civilization: Sanctum Construct Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 聖域巨兵.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Sanctum Construct Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule > 聖域巨兵系; Idle Rule > 聖堂系; Attack Rule > 重武器; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖域巨兵.

#### Lore

- World Position: 聖堂核心區的重型守護兵器，負責守護重要聖域與王庭入口。
- Personality: 被賦予絕對守護命令，不會遲疑、不會質疑，也不會停止行動。
- Entry Feeling: 沉重步伐前進，動作一致且過於精準，彷彿被某種意志統御。
- Party Note: 「巨兵不會疲憊，也不會恐懼，它們只會守護，直到命令終止。」

#### Silhouette

- Head Recognition: 全覆式聖甲頭盔。
- Weapon Recognition: 巨型戰槌／盾槍。
- Body Shape: 超大型重裝單位。
- Posture: 沉重直立、壓迫感強。
- Visual Outline: 高於一般單位約兩倍，厚重白銀與金色裝甲包覆全身，肩甲巨大，胸口帶發光聖紋，武器為大型戰槌或厚重盾槍。

#### Color

- Source Color Direction: 白銀、聖金、聖紋微光。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖域巨兵.

#### Animation

- Dynamic Recognition: 重踏、重擊。
- Combat Style: 高耐久與重量壓制型戰鬥，攻擊頻率低但具壓迫感。
- Idle: 緩慢呼吸般起伏，盔甲間散發微光，偶爾調整站姿。
- Death: 身體失去支撐向前重重跪地，鎧甲與武器撞擊地面發出沉重聲響。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 巨兵鋼核 | `monster_material_master_database.md` |  |
| 聖鋼碎片 | `monster_material_master_database.md` |  |
| 神聖動力核 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: none for reference layer

---

### MON_CH05_NORMAL_004 - 聖羽巡禮者 / Holy Feather Pilgrim

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 國境與聖堂間
- Civilization: Holy Pilgrim Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 聖羽巡禮者.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Holy Pilgrim Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule > 聖羽巡禮系; Idle Rule > 聖堂系; Attack Rule > 法術; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖羽巡禮.

#### Lore

- World Position: 行走於國境與聖堂間的巡禮者，兼具傳遞信仰與協助軍勢的角色。
- Personality: 表面溫和虔誠，但笑容與行為過於一致，帶有某種近乎機械式的安定感。
- Entry Feeling: 緩慢行走、微笑凝視前方，羽飾輕晃，像在等待被引導的人。
- Party Note: 「他們總說自己受到了祝福，但旅者開始分不清，那究竟是虔誠還是麻木。」

#### Silhouette

- Head Recognition: 羽飾披肩、柔和面容。
- Weapon Recognition: 聖光法器。
- Body Shape: 修長人形。
- Posture: 緩步行走、儀式感。
- Visual Outline: 身披淡白長袍與羽飾披肩，腰間帶祈福小袋與銀飾，背部掛有象徵聖光的羽紋飾品。

#### Color

- Source Color Direction: 純白、淡金、羽白。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖羽巡禮.

#### Animation

- Dynamic Recognition: 祝福、祈禱。
- Combat Style: 偏支援與干擾，透過祝福與輔助影響戰場穩定性。
- Idle: 衣袍微幅擺動，偶爾低聲祈禱，羽飾隨動作輕晃。
- Death: 緩慢跪地後向側倒下，羽飾散落地面。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 聖羽羽毛 | `monster_material_master_database.md` |  |
| 光翼殘羽 | `monster_material_master_database.md` |  |
| 巡禮徽章 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: none for reference layer
- Source Label Note: extracted lore text shows a `禁忌修士` heading before the content whose world position, drops, and party note match 聖羽巡禮者; this draft maps the block by monster database, silhouette Bible, and material source.

---

### MON_CH05_NORMAL_005 - 墮落審判者 / Fallen Inquisitor

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 聖堂國境
- Civilization: Inquisition Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 墮落審判者.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Inquisition Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 審問官系; Holy Monster Animation Rule; Idle Rule > 聖堂系; Attack Rule > 重武器; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 審問官.

#### Lore

- World Position: 曾為聖堂異端審問官，後因極端信仰與污染逐漸走向扭曲。
- Personality: 對秩序抱有近乎偏執的執念，相信任何偏離規則者都應被消除，即使是自己人。
- Entry Feeling: 緩慢拖行武器，目光銳利而壓迫，帶著過度警戒感。
- Party Note: 「他們似乎早已忘記何謂守護，只記得何謂服從。」

#### Silhouette

- Head Recognition: 面罩遮面、冷峻眼神。
- Weapon Recognition: 審判刃＋鐵鍊。
- Body Shape: 中大型人形。
- Posture: 微前傾壓迫姿態。
- Visual Outline: 深黑與暗銀色盔甲，披著殘破長袍，手持沉重審判刃與鐵鍊，面部部分被面罩遮蔽。

#### Color

- Source Color Direction: 黑銀、暗紅、深灰。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 審問官.

#### Animation

- Dynamic Recognition: 拖刀前進、重斬。
- Combat Style: 高威脅近戰，攻擊帶壓迫感與少量干擾性。
- Idle: 微微前傾保持壓迫姿態，鐵鍊偶爾晃動。
- Death: 武器滑落後重重倒地，身體保持向前姿態。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 黑鐵審判刃 | `monster_material_master_database.md` |  |
| 墮落鐵鍊 | `monster_material_master_database.md` |  |
| 深罪徽章 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: none for reference layer

---

### MON_CH05_NORMAL_006 - 聖歌幽魂 / Hymn Wraith

#### Identity

- Source Type: Normal
- Threat Level: Normal
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 修道院與聖域
- Civilization: Hymn Spirit Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 聖歌幽魂.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Hymn Spirit Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule > 聖歌靈體系; Idle Rule > 聖堂系; Attack Rule > 法術; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖歌靈體.

#### Lore

- World Position: 殘留於修道院與聖域中的靈體，似乎仍持續吟唱早已失落的聖歌。
- Personality: 反覆吟唱古老聖歌，旋律平靜卻令人不安，像是在低聲傳遞某種命令。
- Entry Feeling: 漂浮進場時伴隨低頻殘響，歌聲若有似無地迴盪。
- Party Note: 「聖歌依然存在，但越接近聖域，那旋律越像命令，而不再像祈禱。」

#### Silhouette

- Head Recognition: 無明顯五官、靈體輪廓。
- Weapon Recognition: 聖歌能量。
- Body Shape: 漂浮靈體。
- Posture: 低頭漂浮。
- Visual Outline: 半透明白金靈體，衣袍邊緣帶微光粒子，頭部略低垂，周圍漂浮細微光塵。

#### Color

- Source Color Direction: 白金、淡藍、透明光體。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖歌靈體.

#### Animation

- Dynamic Recognition: 飄浮、吟唱、消散。
- Combat Style: 法術與支援壓力型怪物，透過聖歌影響敵我戰場節奏。
- Idle: 緩慢漂浮、衣袍飄動，周圍粒子緩慢流動。
- Death: 光芒逐漸暗去，身體化為細小光塵消散。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 聖歌殘譜 | `monster_material_master_database.md` |  |
| 光靈微塵 | `monster_material_master_database.md` |  |
| 神聖音核 | `monster_material_master_database.md` |  |

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: none for reference layer

---

## Special Source Monsters

### MON_CH05_SPECIAL_001 - 聖歌祭司 / Hymn Priest

#### Identity

- Source Type: Special
- Threat Level: Normal
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 聖光邊境與王庭巡禮
- Civilization: Hymn Spirit Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 聖歌祭司.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Hymn Spirit Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule > 聖歌靈體系; Idle Rule > 聖堂系; Attack Rule > 法術; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖歌靈體.

#### Lore

- World Position: 行走於聖光邊境與王庭巡禮中的祭司，負責穩定軍勢與維持士兵信仰，在混亂戰場中被視為精神核心。
- Personality: 平靜、虔誠、帶有安定感，即便身處戰場仍維持儀式感與秩序，不主動躁進。
- Entry Feeling: 緩步走入戰場，低頭祈禱，腳邊浮現淡金粒子，周圍伴隨極輕微聖歌氣音。
- Party Note: 「有人說，只要仍能聽見低聲聖歌，就代表國境仍未真正崩塌。」

#### Silhouette

- Head Recognition: 白金祭司冠飾。
- Weapon Recognition: 細長聖杖。
- Body Shape: 高瘦神職者。
- Posture: 儀式性站姿。
- Visual Outline: 身穿白金色祭司袍，衣袍邊緣帶聖紋刺繡，肩部披有輕羽披肩，胸前懸掛聖徽與祈禱珠，雙手持細長聖杖。

#### Color

- Source Color Direction: 白金、純白、淡金。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖歌靈體.

#### Animation

- Dynamic Recognition: 祝福、聖歌。
- Combat Style: 偏支援型，透過祝福穩定戰場，提升周圍怪物續戰能力與團隊穩定性.
- Idle: 微幅呼吸與衣袍晃動，偶爾低聲哼唱模糊聖歌，祈禱珠緩慢擺動。
- Death: 聖杖滑落地面，短暫單膝跪地後向側傾倒，聖光粒子逐漸散去。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 聖歌祈珠 | `monster_material_master_database.md` |  |
| 光輝聖羽 | `monster_material_master_database.md` |  |
| 巡守布料 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Individual Target Line: SOURCE MISSING.

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: target line
- Source Label Note: extracted lore text shows a `聖域巨兵` heading before the content whose type, world position, drops, and party note match 聖歌祭司; this draft maps the block by monster database, silhouette Bible, and material source.

---

### MON_CH05_SPECIAL_002 - 黑袍審問官 / Black-Robed Inquisitor

#### Identity

- Source Type: Special
- Threat Level: Normal
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 墮落修道院
- Civilization: Inquisition Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 黑袍審問官.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Inquisition Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Humanoid Animation Rule > 審問官系; Holy Monster Animation Rule; Idle Rule > 聖堂系; Attack Rule > 重武器; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 審問官.

#### Lore

- World Position: 聖堂異端審問體系中的執行者，被派遣至墮落修道院追捕異端與污染者。
- Personality: 冷酷、偏執、沉默，對異端帶有近乎病態的執念，戰鬥中會極度專注目標。
- Entry Feeling: 緩慢走出陰影，武器拖行地面發出低沉金屬聲，短暫停頓後鎖定敵人。
- Party Note: 「審問官從不相信善惡，只相信是否違反信仰。」

#### Silhouette

- Head Recognition: 半遮面審判面具。
- Weapon Recognition: 細長審判刃。
- Body Shape: 中大型人形。
- Posture: 前傾鎖定目標。
- Visual Outline: 深黑長袍外覆輕甲，頭部戴半遮面審判面具，腰間懸掛審判書與鎖鏈，手持細長審判刃。

#### Color

- Source Color Direction: 黑袍、暗灰、黑金。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 審問官.

#### Animation

- Dynamic Recognition: 拖刀、快速裁決。
- Combat Style: 高威脅單體壓力型，擅長快速裁決與高傷害壓迫。
- Idle: 身體略微前傾，鎖鏈輕微晃動，偶爾發出低沉鼻息聲。
- Death: 武器脫手滑落，身體向前半跪後重重倒地。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 審判徽印 | `monster_material_master_database.md` |  |
| 禁忌裁決書 | `monster_material_master_database.md` |  |
| 黑印碎片 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Individual Target Line: SOURCE MISSING.

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: target line

---

### MON_CH05_SPECIAL_003 - 聖域裁決者 / Sanctum Adjudicator

#### Identity

- Source Type: Special
- Threat Level: Normal
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 王國聖域
- Civilization: Sanctum Construct Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 聖域裁決者.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Sanctum Construct Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule > 聖域巨兵系; Idle Rule > 聖堂系; Attack Rule > 重武器; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖域巨兵.

#### Lore

- World Position: 王國聖域中的高階裁決守衛，負責守護王庭與執行聖堂最高命令。
- Personality: 沉默、絕對服從、威壓感強烈，像是王庭意志的具現化。
- Entry Feeling: 沉重步伐緩慢進場，地面傳來低沉震動，戰槌拖動產生石地摩擦聲。
- Party Note: 「有人說，聖域裁決者從不說話，因為它的存在本身就是審判。」

#### Silhouette

- Head Recognition: 裁決聖盔。
- Weapon Recognition: 巨型裁決戰槌。
- Body Shape: 超大型重裝單位。
- Posture: 絕對壓迫姿態。
- Visual Outline: 高於一般士兵近兩倍，厚重白銀與金色聖甲包覆全身，肩甲寬大，胸口刻有巨大裁決紋章，手持巨型裁決戰槌。

#### Color

- Source Color Direction: 白銀、聖金、聖紋藍光。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖域巨兵.

#### Animation

- Dynamic Recognition: 重踏、裁決重擊。
- Combat Style: 中範圍壓制型特殊怪，透過高傷害與重量感建立戰場威脅。
- Idle: 緩慢呼吸起伏，裝甲微光閃動，戰槌偶爾微幅調整角度。
- Death: 戰槌重擊地面後失去支撐，身體緩慢前傾跪倒，盔甲發出沉重崩落聲。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 裁決重核 | `monster_material_master_database.md` |  |
| 王庭秘紋 | `monster_material_master_database.md` |  |
| 聖域結晶 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Individual Target Line: SOURCE MISSING.

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: target line

---

## Elite Monsters

### MON_CH05_ELITE_001 - 聖槍隊長・雷昂 / Leon, Captain of the Holy Lance

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 聖光邊境前線
- Civilization: Holy Guard Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 聖槍隊長・雷昂.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Holy Guard Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule > 聖堂守衛系; Idle Rule > 聖堂系; Attack Rule; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖堂守衛; Elite Monster Color Rule.

#### Lore

- World Position: 聖光邊境前線的聖槍隊長，負責率領巡守部隊與維持國境秩序，是王國前線的重要戰力。
- Personality: 冷靜、自律、具軍人氣質，擁有明確指揮感，不輕易躁進，會觀察戰局後發動進攻。
- Entry Feeling: 帶著沉穩步伐進場，長槍落地發出低沉金屬聲，停步後微微抬起長槍進入戰鬥姿態。
- Party Note: 「即便前線崩潰，聖槍隊長依舊站在國境之前，像一道不肯退後的牆。」

#### Silhouette

- Head Recognition: 聖槍軍官頭盔。
- Weapon Recognition: 長柄聖槍。
- Body Shape: 高大騎士體格。
- Posture: 正面迎敵姿態。
- Visual Outline: 身穿銀白與金色邊飾戰甲，披著短白披風，胸甲刻有聖槍紋章，右手持長柄聖槍，左肩帶有王國軍徽，姿態挺拔。

#### Color

- Source Color Direction: 銀白、聖金、白披風。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖堂守衛; Elite Monster Color Rule.

#### Animation

- Dynamic Recognition: 高速突刺、壓迫推進。
- Combat Style: 偏高爆發近戰型，利用高速突刺與連續壓迫快速削弱敵方。
- Idle: 長槍穩定持握，身體微幅呼吸起伏，偶爾短促吐氣與調整腳步。
- Death: 長槍脫手插地，單膝跪地後向側前方倒下，盔甲碰撞地面發出厚重聲響。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 聖槍核心 | `monster_material_master_database.md` |  |
| 聖衛戰甲 | `monster_material_master_database.md` |  |
| 光輝印記 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Formal Skill Database Entry: SOURCE MISSING.
- Target Line: SOURCE MISSING.
- Source combat wording is preserved as descriptive behavior only; no new skill is created.

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: formal skill database entry; target line
- Source Label Note: extracted lore text shows a `聖羽巡禮者` heading before the content whose type, world position, drops, and party note match 聖槍隊長・雷昂; this draft maps the block by monster database, silhouette Bible, and material source.

---

### MON_CH05_ELITE_002 - 墮落主教・薩菲爾 / Saphir, Fallen Bishop

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 聖堂國境
- Civilization: Fallen Bishop Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 墮落主教・薩菲爾.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Fallen Bishop Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule; Idle Rule > 聖堂系; Attack Rule > 法術; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 墮落主教; Elite Monster Color Rule.

#### Lore

- World Position: 曾是聖堂高階神官，於禁忌儀式中墮落，成為污染修道院的支配者之一。
- Personality: 沉著、壓迫、帶偏執感，對信仰近乎瘋狂，相信墮落才是真正的救贖。
- Entry Feeling: 緩慢自黑霧中現身，腳邊浮現黯淡聖紋，低沉祈禱氣音伴隨微弱黑霧流動。
- Party Note: 「有人說，薩菲爾並未背叛信仰，只是走向了另一種極端。」

#### Silhouette

- Head Recognition: 破損聖徽、黑金長袍。
- Weapon Recognition: 厚重聖典。
- Body Shape: 高瘦神職者。
- Posture: 緩慢壓迫感。
- Visual Outline: 黑金色長袍覆蓋半腐化聖甲，肩部披掛破裂聖布，胸前懸浮破損聖徽，雙眼泛出微弱暗光，手持厚重聖典。

#### Color

- Source Color Direction: 黑金、暗紫、灰黑。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 墮落主教; Elite Monster Color Rule.

#### Animation

- Dynamic Recognition: 黑霧、詠唱。
- Combat Style: 高階 Buff／Debuff 壓力型精英，擅長削弱玩家並強化周圍敵軍。
- Idle: 衣袍與聖典緩慢晃動，偶爾發出幾乎聽不清的低聲禱語與沉重呼氣。
- Death: 聖典落地展開，身體微微前傾跪下，黑霧逐漸散去後倒地。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 墮落聖典 | `monster_material_master_database.md` |  |
| 黑聖徽記 | `monster_material_master_database.md` |  |
| 深罪灰燼 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Formal Skill Database Entry: SOURCE MISSING.
- Target Line: SOURCE MISSING.
- Source combat wording is preserved as descriptive behavior only; no new skill is created.

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: formal skill database entry; target line

---

### MON_CH05_ELITE_003 - 聖域巨兵・瓦倫特 / Valent, Sanctum Giant

#### Identity

- Source Type: Elite
- Threat Level: Elite
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 王國聖域
- Civilization: Sanctum Construct Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 聖域巨兵・瓦倫特.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > Sanctum Construct Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Holy Monster Animation Rule > 聖域巨兵系; Idle Rule > 聖堂系; Attack Rule > 重武器; Death Rule > 聖堂系.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖域巨兵; Elite Monster Color Rule.

#### Lore

- World Position: 王國聖域中的重型守衛兵器，被用於鎮守核心聖域與阻止外敵進入王庭。
- Personality: 沉默、威壓、極度穩定，像是被命令驅動的聖域機關兵器。
- Entry Feeling: 重步進場，地面產生微震與低沉金屬聲，戰鎚拖地產生重量感摩擦聲。
- Party Note: 「在王庭深處，瓦倫特被視為最後一道無聲防線。」

#### Silhouette

- Head Recognition: 巨型聖甲頭盔。
- Weapon Recognition: 超大型戰鎚。
- Body Shape: 超大型重裝兵器。
- Posture: 穩定站姿。
- Visual Outline: 近兩倍角色高度，全身覆蓋厚重白銀聖甲，關節帶有發光聖紋，雙肩巨大裝甲，雙手持超大型戰鎚。

#### Color

- Source Color Direction: 白銀、聖金、聖紋光。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Holy Civilization Colors > 聖域巨兵; Elite Monster Color Rule.

#### Animation

- Dynamic Recognition: 重擊、震地。
- Combat Style: 中範圍壓制型精英，以高耐久與重量型攻擊持續建立壓迫。
- Idle: 緩慢呼吸起伏，裝甲微光流動，偶爾微幅調整站姿與武器角度。
- Death: 戰鎚先落地，身體失去支撐緩慢跪下後沉重倒地，伴隨裝甲崩落聲。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 巨兵聖核 | `monster_material_master_database.md` |  |
| 聖鋼巨片 | `monster_material_master_database.md` |  |
| 神域動力石 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Formal Skill Database Entry: SOURCE MISSING.
- Target Line: SOURCE MISSING.
- Source combat wording is preserved as descriptive behavior only; no new skill is created.

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: formal skill database entry; target line

---

## Boss Monsters

### MON_CH05_BOSS_001 - 白冠主教・薩維恩 / Savien, White-Crowned Bishop

#### Identity

- Source Type: Boss
- Threat Level: Boss
- Chapter: Chapter 05 - 聖堂國境
- Region Distribution: 聖堂國境
- Civilization: White Crown Authority Civilization

#### Reference Layer

- Silhouette Reference: `MONSTER_SILHOUETTE_BIBLE.md` > Chapter 05 Monster Table > 白冠主教・薩維恩.
- Civilization Reference: `MONSTER_CIVILIZATION_BIBLE.md` > Chapter 05 > White Crown Authority Civilization.
- Animation Reference: `MONSTER_ANIMATION_BIBLE.md` > Boss Animation Rule > 白冠主教・薩維恩; Holy Monster Animation Rule > 白冠權威系; Idle Rule > Boss; Death Rule > Boss.
- Color Reference: `MONSTER_COLOR_BIBLE.md` > Boss Color Rule > 白冠主教・薩維恩.

#### Lore

- World Position: 聖堂國境中的高階白冠主教，負責維持王國信仰秩序與聖堂穩定，被人民視為聖域權威與精神支柱。然而在神聖表象下，實際上長期扭曲信仰與操控聖堂秩序。
- Personality: 冷靜、威嚴、極度克制，擁有高階神職的安定感與壓迫感。表面如同引導人民的神職者，實際上帶有強烈控制慾與近乎偏執的秩序觀。
- Entry Feeling: 巨大聖門緩慢開啟，低沉聖歌與白金光粒流動，薩維恩緩步現身，周圍展開神聖光環與巨大聖紋。短暫停頓後長杖落地，空氣產生輕微震動感。
- Party Note: 「他教導人們敬畏光明，卻沒有人發現，那光已不再溫暖。」

#### Silhouette

- Head Recognition: 純白冠飾、巨大聖徽。
- Weapon Recognition: 主教權杖。
- Body Shape: 高瘦神職者。
- Posture: 平靜俯視姿態。
- Visual Outline: 身穿厚重白金長袍與高階主教聖衣，頭戴純白冠飾，肩部披掛大型聖紋披肩，胸前懸掛巨大聖徽，手持象徵權威的長杖。整體莊嚴而高貴，但細看可見衣袍深處帶有微弱黑紋與異常光暈。

#### Color

- Source Color Direction: 白金、純白、淡金、微弱黑紋。
- Locked Monster Color Bible Reference: `MONSTER_COLOR_BIBLE.md` > Boss Color Rule > 白冠主教・薩維恩.

#### Animation

- Dynamic Recognition: 聖光流動、神聖刻印、低語共鳴。
- Combat Style: 高階團隊壓力型 Boss，擅長透過 Buff 強化與戰場控制建立穩定壓力，偏向團隊續戰與高階隊伍穩定性測試。
- Idle: 長袍與披肩緩慢擺動，微幅呼吸起伏，偶爾傳出低沉呼氣與極短促模糊低語，聖徽散發穩定光芒。
- Death: 長杖失去支撐落地，身體緩慢單膝跪下，白冠裂開並滑落，聖光逐漸消散，最後向前沉重倒下。

#### Drops

| Material | Source Database | Notes |
|---|---|---|
| 審判聖印（待更名） | `monster_material_master_database.md` | Source material name includes pending rename marker |
| 光輝聖核 | `monster_material_master_database.md` |  |
| 薩維恩聖徽 | `monster_material_master_database.md` |  |

#### Combat Source Notes

- Formal Skill Database Entry: SOURCE MISSING.
- Target Line: SOURCE MISSING.
- Source text names `聖域降諭` and `白冠祝福`, but no formal skill database entry is provided in the approved database layer.
- Source text includes CD values and target/effect details after a misplaced `聖歌幽魂` heading; this Monster Database does not record CD, numerical values, drop rates, quantities, or weights.

#### Integration Notes

- Lore Source: `archive/chapter05_monster_lore.docx`
- Silhouette Source: `archive/Chapter 05_Monster_Silhouette _260606_150018.docx`
- Missing Fields: formal skill database entry; target line
- Source Label Note: extracted lore text shows a `墮落審判者` heading before the Boss identity block for 白冠主教・薩維恩; this draft maps the block by Boss-only authority, monster database, silhouette Bible, and material source.

---

## Chapter 05 Boss Core Positioning

| Boss | Core Role | Combat Reading Direction | Forbidden Direction |
|---|---|---|---|
| 白冠主教・薩維恩 | 高階信仰 Boss / 邪教化信仰核心 Boss / Buff 對抗 Boss / 團隊穩定性檢查 Boss / 第五章世界觀轉折 Boss | 神聖文明壓迫感; 神聖表象下的不安感; 高階團隊戰壓力; 高辨識度文明演出; 高可閱讀性技能設計 | Do not use over-control, high-frequency DOT, long unable-to-act states, or unreadable skills |

---

## Missing Source Register

| Missing / Conflict Item | Source Gap | Handling |
|---|---|---|
| Chapter 05 source heading conflicts | extracted lore text misplaces headings before 聖羽巡禮者, 聖歌祭司, 聖槍隊長・雷昂, and 白冠主教・薩維恩 blocks | Map blocks by monster database, silhouette Bible, world position, drops, and party note; preserve as review note |
| Special monster individual Target Line usage | no source-specific skill targeting available | Marked as `SOURCE MISSING` |
| Elite / Boss formal skill database entries | source text describes combat roles and names some actions, but no formal skill database entries are provided in the approved database layer | Marked as `SOURCE MISSING`; no skill entries created |
| Elite / Boss individual Target Line usage | no source-specific skill targeting available | Marked as `SOURCE MISSING` |
| Boss source skill details include CD and effect values | `archive/chapter05_monster_lore.docx` includes CD/effect details after a misplaced heading | Not recorded; this Monster Database does not include numerical values |
| `審判聖印（待更名）` material name | material exists in `monster_material_master_database.md` but includes pending rename marker | Recorded exactly as source material name; no rename performed |
| `material_usage_master_database.md` Chapter 05 usage categories | Chapter 05 section is reserved and has no usage entries | No usage categories added; Monster Database records material names only |

---

## Consolidation Summary

| Category | Count |
|---|---:|
| Normal Monsters | 6 |
| Special Source Monsters | 3 |
| Elite Monsters | 3 |
| Boss Monsters | 1 |
| Reference Layers | 13 |

---

## Bible Mapping Review

| Monster | Silhouette Bible | Civilization Bible | Animation Bible | Color Bible | Mapping Status |
|---|---|---|---|---|---|
| 聖堂守衛 | Mapped | Mapped | Mapped | Mapped | OK |
| 禁忌修士 | Mapped | Mapped | Mapped | Mapped | OK |
| 聖域巨兵 | Mapped | Mapped | Mapped | Mapped | OK |
| 聖羽巡禮者 | Mapped | Mapped | Mapped | Mapped | OK |
| 墮落審判者 | Mapped | Mapped | Mapped | Mapped | OK |
| 聖歌幽魂 | Mapped | Mapped | Mapped | Mapped | OK |
| 聖歌祭司 | Mapped | Mapped | Mapped | Mapped | OK |
| 黑袍審問官 | Mapped | Mapped | Mapped | Mapped | OK |
| 聖域裁決者 | Mapped | Mapped | Mapped | Mapped | OK |
| 聖槍隊長・雷昂 | Mapped | Mapped | Mapped | Mapped | OK |
| 墮落主教・薩菲爾 | Mapped | Mapped | Mapped | Mapped | OK |
| 聖域巨兵・瓦倫特 | Mapped | Mapped | Mapped | Mapped | OK |
| 白冠主教・薩維恩 | Mapped | Mapped | Mapped | Mapped | OK |

No Chapter 05 monster in this draft is unable to map to the locked Monster Bible files.
