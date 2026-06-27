# AGENTS.md
# Documentation Loading Order

Before making any design, implementation, balancing, database, combat, worldbuilding, UI, or content decision:

1. Read `SOURCE_OF_TRUTH_INDEX.md`
2. Read referenced Source of Truth documents
3. Use those files as authoritative

If a conflicting rule is found:

```text
SOURCE_OF_TRUTH_INDEX.md
>
AGENTS.md
>
GAME_CURRENT_VERSION.md
>
CURRENT_PROJECT_STATE.md
>
*_CURRENT.md
>
*_FINAL.md
>
Legacy / Archive / Backup / Superseded files
```

Legacy, Archive, Backup, Superseded files must never override active rules.

---

# Required Reading Order

Before making any implementation:

1. Read `GAME_CURRENT_VERSION.md`
2. Read the latest `WEEKLY_SUMMARY_YYYY_MM_DD.md`
3. Follow finalized systems only

---

# Single Source of Truth

`GAME_CURRENT_VERSION.md` is the only official finalized version.

When conflicts exist:

```text
GAME_CURRENT_VERSION.md
>
WEEKLY_SUMMARY
>
discussion logs
```

Always follow finalized version only.

---

# Combat Rules Priority

Always prioritize:

- `combat_system_current.md`
- `GAME_CURRENT_VERSION.md`

Ignore:

- `Status = SUPERSEDED`
- `Status = ARCHIVE`

---

# Implementation Rules

Do NOT implement:

- Draft systems
- Discussion ideas
- Deprecated mechanics
- Placeholder assumptions
- Systems without finalized confirmation

Only implement:

- finalized systems
- finalized UI
- finalized combat rules
- finalized game loop

---

# Development Philosophy

Priority order:

```text
Player Control
>
Readability
>
Long-term progression
>
World immersion
>
Visual polish
```

Core principles:

- Player control > travel immersion
- Tavern = main base
- Observation-based combat
- Low-number RPG
- No front/back row
- Vertical mobile gameplay
- Tavern can switch to landscape mode
- Low-interference UI
- Long-term expedition gameplay
- Civilization-based build system

---

# UI Rules

Avoid:

- MMORPG UI
- visual clutter
- excessive popups
- high-frequency animations
- overloaded combat UI

Prefer:

- clean layout
- readable combat
- low interference
- mobile readability
- collapsible information

---

# Combat Rules

Combat must remain:

- readable
- observation-friendly
- medium pacing
- visually understandable

Do NOT create:

- screen explosion combat
- unreadable spam effects
- ultra-fast autoplay chaos

---

# System Scope Rule

Prefer playable MVP first.

Priority:

```text
Core gameplay loop
>
System stability
>
Polish
>
Extra features
```

Never over-engineer.

Focus:

```text
Tavern
-> Expedition
-> Combat
-> Reward
-> Return to Tavern
```

---

# Required Output After Implementation

After each task report:

1. New scene tree
2. New scripts
3. Modified files
4. Interaction flow
5. Recommended next step

---

# 專案名稱

文明旅團型世界遠征 RPG（手機直式掛機 RPG）

---

# 專案核心方向（不可更改）

本遊戲核心為：

「酒館主基地＋旅團世界遠征」

核心體驗：
- 世界旅行感
- 酒館生活感
- 長期掛機循環
- AI世界碎片
- 微動態氛圍
- 低壓長期養成

禁止偏離為：
- MMORPG
- 手操ARPG
- 高APM戰鬥
- 抽卡遊戲
- 大世界自由移動
- 重度模擬經營

---

# 核心遊戲循環（正式版）

```text
酒館主基地
↓
選擇遠征場景
↓
旅團遠征
↓
隨機遭遇
↓
自動戰鬥／世界事件
↓
獲得收益
↓
返回酒館
↓
整理旅團
↓
再次遠征
```

---

# 戰鬥系統限制（不可更改）

## 正式方向

- 全自動戰鬥
- 不採用手動技能
- 不採用走位操作
- 不採用手動閃招
- 不採用QTE
- 不採用高APM操作

---

# 戰鬥站位規則（重要）

## 本遊戲：

不採用：
- 前排／後排系統

所有角色：
皆位於同一戰場層級。

AI判定依照：
- 仇恨值
- HP比例
- 敵人類型
- 空中／地面
- Boss／精英／普通怪
- 職業定位

禁止：
- Tank固定站前
- 遠程固定站後
- 傳統前後排架構

---

# 戰鬥畫面方向

| 系統 | 畫面方向 |
|---|---|
| 戰鬥 | 直向 Portrait |
| 酒館 | 橫向 Landscape |

只有酒館允許橫向切換。

禁止其他場景橫向化。

---

# 酒館系統（正式版）

酒館：
為遊戲首頁／主基地。

不是：
抽卡頁面。

---

# 酒館核心方向

- 旅者聚集地
- 世界呼吸感
- 酒館生活感
- 長期查看感
- 旅團基地

---

# 酒館正式不採用方向

禁止：
- 十連抽
- SSR抽卡核心
- 保底抽卡
- 無限刷新
- 鑽石抽卡角色
- 永久停留旅者
- 高壓管理玩法

---

# 酒館事件系統（正式版）

酒館事件：
為：

「AI世界碎片系統」

事件方向：
- 小故事
- 世界情報
- Buff事件
- 氛圍事件
- 稀有事件

禁止：
- 大量懲罰事件
- 情緒值系統
- 忠誠值系統
- 高壓管理
- 長時間負面狀態

---

# 酒館事件UI

事件：
不使用大型彈窗。

使用：
- 小型浮動訊息
- 酒館傳聞欄
- 微演出

---

# 遠征系統（正式版）

遠征：
為：

「世界旅行」

不是：
副本推關。

---

# 遠征正式方向

- 自動旅行
- 自動戰鬥
- 世界遭遇制
- 長期掛機
- 離線持續旅行

---

# 遠征遭遇規則（正式版）

所有遭遇：
皆採：

「權重隨機遭遇」

包含：
- 普通怪
- 菁英怪
- Boss
- 世界事件
- 稀有事件

---

# Boss規則（重要）

Boss：
不是固定關底。

Boss：
採：

「權重累積遭遇」

方向：
- 剛進場遭遇率低
- 長時間旅行提高遭遇率
- 遭遇Boss後重置權重

禁止：
- 固定Boss關卡
- 固定Boss循環
- 固定精英流程

---

# 離線收益規則

離線期間：
旅團仍會持續旅行。

但：
部分特殊事件採簡化結算。

禁止：
- 顯示精確離線收益倍率
- 顯示效率百分比
- 顯示離線懲罰

使用世界觀描述：
例如：

「旅團在你離開期間持續旅行。」

---

# 世界觀核心方向

世界：
為：

「持續運作中的文明世界」

方向：
- 旅行感
- 文明差異
- 世界流動感
- 長途冒險

不是：
- 固定副本世界
- 線性關卡世界

---

# 場景正式版本

封測版本：
1. 王國邊境
2. 旅人荒境
3. 骷髏荒原
4. 沙漠遺城
5. 聖堂國境
6. 森靈秘境

延後版本：
- 深淵裂谷
- 古代遺跡

---

# 戰鬥數值限制（重要）

本遊戲：
為：

「低數值 RPG」

禁止：
- 傷害膨脹
- 超高倍率技能
- 後期數十萬傷害
- MMO級數值

---

# 數值方向

第一章參考：
- 普攻約20～60
- 技能約50～120
- Boss技能約80～180

後期整體：
建議控制於：
1000～5000內。

---

# 技能系統限制

每角色：
固定：
- 普通攻擊1
- 主動技能1
- 被動技能1

5轉：
新增主動技能2

6轉：
新增被動技能2

禁止：
- 大量技能欄
- MMO技能輪轉
- 高APM輸入

---

# 普通攻擊規則（重要）

普通攻擊：
不需要技能名稱。

演出方向：
- 小幅角色晃動
- 小殘影
- 小型命中特效
- 簡短演出

禁止：
- 華麗技能式普攻
- 長動畫普攻

---

# AI系統（正式版）

AI：
必須可預測。

核心：
- 穩定循環
- 可閱讀
- 旅團觀看感

禁止：
- 電競型AI
- 高速反應AI
- 複雜即時操作AI

---

# 控制系統（正式版）

控制分為：
- 弱控
- 強控
- 特殊控

禁止：
- 永久控制
- 無限冰凍
- 無限睡眠

Boss：
不完全免疫控制。

採：
控制抗性。

---

# Buff／Debuff系統

UI方向：
- 卷軸式顯示
- Buff／Debuff分類
- 摺疊式狀態顯示

禁止：
- 全圖示展開轟炸
- 大量手機UI遮蔽

---

# 裝備系統（正式版）

裝備品質：
- 普通
- 精良
- 稀有
- 傳承
- Boss裝

---

# 裝備正式方向

綠裝：
弱特化

藍裝：
主流Build核心

紫裝：
文明型Build

Boss裝：
玩法改變型裝備

---

# Boss裝限制

Boss裝：
不使用：
- 隨機綴詞
- 洗詞
- 隨機詞條池

Boss裝：
為固定特殊效果。

---

# 強化系統（正式版）

強化：
為：

「穩定小幅成長」

不是：
核心數值爆發。

禁止：
- 爆裝
- 降階
- 耐久損壞
- 高壓強化懲罰

---

# 強化限制

+6開始：
需要核心碎片。

方向：
高階強化需要更多代價。

---

# 美術方向（重要）

美術方向：
- 8～16bit像素風
- 微動態背景
- 低干擾演出
- 掛機觀看舒適

禁止：
- 過度華麗特效
- 滿版粒子
- 手機閱讀性崩壞

---

# 戰鬥背景方向

採：
「靜態主戰場＋活背景」

背景分層：
- 遠景
- 中景
- 主戰場
- 前景

只做：
微動態。

禁止：
- 高速卷軸
- 劇烈鏡頭晃動

---

# 角色外觀系統

不採用：
- 紙娃娃系統
- 自由換裝外觀

角色外觀：
依轉職階段進化。

---

# 武器系統（正式版）

武器：
依文明與職業分流。

禁止：
全職通用武器池。

---

# 衛兵系武器

初始：
劍

後續：
- 劍盾
- 連枷
- 雙劍
- 巨劍

---

# 弓箭手系武器

初始：
弓

後續：
- 十字弓
- 長弓
- 精靈弓
- 黑妖弓

---

# 遊蕩者系武器

初始：
匕首

後續：
- 雙刃
- 袖劍
- 樂器

---

# 法師／術士武器

主武器：
法杖

差異：
特殊法器演出。

禁止：
全職分裂武器。

---

# 世界事件方向

事件：
為：

「世界碎片」

方向：
- 小故事
- 世界感
- 微Buff
- 文明傳聞

禁止：
- 大量主線文本
- 長篇劇情彈窗
- 沉重閱讀壓力

---

# UI核心方向

UI：
必須：

- 手機優先
- 低干擾
- 可閱讀
- 直向舒適

禁止：
- MMORPG複雜UI
- 滿版按鈕
- 多層資訊轟炸

---

# 專案核心總結（重要）

本遊戲正式定位：

「酒館主基地型世界遠征掛機 RPG」

核心特色：
- 酒館主基地
- AI世界碎片
- 世界旅行感
- 長期掛機循環
- 文明型職業系統
- 低數值RPG
- 微動態世界
- MMO式旅團氛圍
- 回來查看感

禁止偏離上述方向。

---

# 本地開發資訊

- Engine: Godot 3.6.1
- Main scene: `res://scenes/TavernMainScene.tscn`
- Tavern main controller: `res://scripts/tavern_main_scene.gd`
- Battle controller: `res://scripts/battle_scene.gd`
- Resolution target for battle: 720 x 1280 portrait

核心文件：
- `GAME_CURRENT_VERSION.md` (唯一正式版本依據)
- `WEEKLY_SUMMARY_2026_05_24.md` (目前最新正式週摘要)
- `NEXT_STEPS.md` (開發路線圖，不作為正式系統定案依據)
- `docs/battle_rules_v1.md`
- `docs/battle_ui_current_layout_v2.md`
- `docs/combat_tempo_rules.md`
- `docs/status_system_rules.md`
- `docs/ai_archetype_rules.md`
- `docs/class_design_rules.md`

---

# Codex完成流程

每次開發完成後：

1. 更新 `CHANGELOG.md`
2. 更新 `DEVLOG.md`
3. 驗證 Godot 3.6.1 可啟動
4. 列出目前已知問題
5. 附上或更新最新戰鬥截圖（可行時）

Godot 啟動驗證路徑：

```text
C:\Users\User\Desktop\Godot_v3.6.1-stable_win64.exe
```

注意：
- Godot 3 對 `:=` 型別推斷較嚴格，模糊型別請使用明確型別或普通 `var`。
- 若 Godot 錯誤面板提供行號，優先修正該行。


