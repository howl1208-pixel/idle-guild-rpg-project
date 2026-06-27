# GAME_CURRENT_VERSION

版本狀態： 正式定案版本（Single Source of Truth）

用途： 本檔案為目前遊戲唯一正式版本依據。

僅記錄： - 已定案內容 - 正式系統 - 正式規則 - 正式不採用方向

不包含： - 草稿 - 推測方案 - 討論中內容
Source Priority：

若 Hub Tavern v2 與主 GAME_CURRENT_VERSION.md 衝突，以 Hub Tavern v2 規則為準。

不得用主檔舊規則覆蓋 Hub Tavern v2 已定案內容。

------------------------------------------------------------------------

# 核心設計哲學

-   玩家掌控感 \> 旅行感
-   觀賞型戰鬥
-   文明型 Build
-   長期掛機旅團
-   酒館主基地
-   低干擾 UI
-   低數值 RPG
-   手機直向優先
-   酒館可橫向模式

------------------------------------------------------------------------

# 戰鬥系統（正式版）

## 核心方向

-   無前後排
-   同層戰場
-   微動態背景
-   無縫接戰
-   技能冷卻制（無 MP）
-   中長期觀賞型戰鬥

## 戰場視覺構圖

-   `COMBAT_BATTLEFIELD_VISUAL_RULE_V4 (FINAL)`：戰場採 Corridor Composition，玩家隊形略順時針 5～8 度、敵方隊形略逆時針 5～8 度，維持同層戰場；玩家隊形往敵方隊形形成斜向對峙軸，Boss 保持敵方陣形視覺中心，Combat Focus Zone 仍水平置中；左上背景區為 Chapter Landmark Zone，禁止單位、UI、Target Line、召喚物或戰鬥特效佔用；戰場依章節主題讀作道路、走廊、峽谷路徑、邊境路線、遺跡通道或森林小徑；旅途感與對峙可讀性優先於戰場對稱。


## COMBAT_BATTLEFIELD_LAYOUT_V1

正式採用目前 S1 Kingdom Border Battlefield Layout Refinement 的場景比例，作為未來所有章節戰鬥背景的比例基準。

本規則鎖定戰鬥場景比例，不指定最終美術素材。

### 固定比例規則

1. 上方遠景 / Landmark 區：
   - 約佔畫面上方 15%～20%。
   - 只作為背景地標。
   - 不放角色、不放怪物、不放 UI。
   - 每章可替換地標，但不得改變比例結構。

2. Boss Anchor：
   - 位於敵方後中線。
   - 與 6 Enemy Formation 分離。
   - Boss 不共用一般 Enemy slot。

3. Enemy Formation Area：
   - 位於畫面上半偏右。
   - 支援敵方微左旋 Facing ↙。
   - 需容納最多 6 Enemy Units。
   - 不得進入 Landmark Zone。

4. Combat Focus Zone：
   - 位於畫面中央。
   - 保持水平。
   - 用於 Target Line、Skill FX、Boss Threat、AoE readability。
   - 不得改成斜區、梯形區或全螢幕特效區。

5. Player Formation Area：
   - 位於畫面中下偏左。
   - 支援玩家微右旋 Facing ↗。
   - 需容納最多 4 Player Units。
   - 不得壓到 UI Safe Area。

6. UI Safe Area：
   - 底部約 35%。
   - 預留給 Support Button、Summon Reserve、Battle Log Tabs、Battle Log、Skill / Gear / Team / Menu。
   - 不得被戰場背景或單位配置占用。

7. Corridor Axis：
   - 整體視覺軸線為左下 → 右上。
   - 用於支撐走廊式對峙感。
   - 玩家 Facing ↗。
   - 敵人 Facing ↙。

### 未來章節套用規則

所有章節背景只替換主題素材，不改比例：

- CH01 王國邊境：Kingdom Wall / Watchtower / Banner
- CH02 旅人荒境：荒原地標 / 風蝕岩 / 沙塵遠景
- CH03 骷髏荒原：墓碑 / 骸骨 / 枯樹
- CH04 沙漠遺城：遺跡 / 石像 / 沙丘
- CH05 聖堂國境：聖堂尖塔 / 聖徽旗 / 白石城牆
- CH06+ 暫不處理，若未來開放也必須沿用同一 Layout 比例。
## 空中敵人

-   僅遠程與法術可命中
-   第一章不出現
-   第二章後逐步登場

## 戰鬥節奏

核心： 玩家可閱讀。

方向： 觀賞性 \> 爆發感

正式戰鬥節奏：

-   `Combat Focus System v1 (FINAL)`：正式覆寫 `combat_tempo_v2` 與 `combat_readability_v1` 的戰鬥焦點規則；正式戰鬥類型為 `Semi Turn-Based Combat`，實際運作仍是 `Real-Time Timeline Combat`
-   `Combat Rhythm + Skill Queue UI v1 (FINAL)`：正式採用 `Real-Time Combat + Global Skill Queue`；普攻維持流動，技能依 Ready Time 進入全域隊列並輪流閱讀
-   `Boss Focus Weight v1 (FINAL)`：Boss Skill 為最高 Focus Queue priority；Boss 只在危險時刻以微縮放、微亮與低干擾 Target Line 自然浮出，不使用電影式停頓或 MMO 警告 UI
-   `Combat Tempo v2 (LOCK)`：作為背景節拍、普攻速度與行動錯拍參考，但焦點事件以 `Combat Focus System v1` 為準
-   `Combat Readability v1 (LOCK)`：作為命中、跳字、特效低疲勞參考，但焦點閱讀窗與 Gap 以 `Combat Focus System v1` 為準
-   `Combat Readability Prototype v1 (LOCK)`：以 4 名角色對 6 名敵人的高密度場面驗證戰鬥是否可自然理解
-   `Combat Readability Philosophy v1`：全章節戰鬥呈現遵循 `SEE → UNDERSTAND → PROCESS`
-   戰鬥可讀性問題優先視為「資訊密度」問題，而非單純降低整體戰鬥速度
-   同一時間只允許 1 個主要視覺焦點；Boss Skill 為 S Priority，優先於 Elite Skill \> Player Skill \> Important Heal \> Background Event
-   約 3 秒內原則上只讓玩家理解 1 個重要事件
-   普通戰鬥：約 45～80 秒
-   精英戰鬥：約 70～110 秒
-   Boss 戰鬥：約 120～240 秒
-   無縫接戰停頓：約 0.5～1 秒
-   普通攻擊採 Global Normal Attack Beat；任意兩次普通攻擊之間全場最短間隔為 1.0 秒，技能 Slow State 期間此全場節拍同步約降低 50%
-   普通攻擊節奏依職業與敏捷形成差異；敏捷影響下一次普通攻擊 Priority Weight，但不可突破全場 1.0 秒 Beat；衛兵 Base Rhythm 約 3.2～4.0 秒、遊蕩者約 2.0～2.8 秒、弓箭手約 2.4～3.0 秒、法師／見習祭司約 3.0～3.8 秒、Boss / 重裝敵約 3.5～5.0 秒
-   主動技能節奏：約 16～24 秒，並加入少量錯開
-   Boss 技能節奏：約 24～36 秒
-   敏捷不影響技能 CD；敏捷只影響普通攻擊節奏
-   技能施放前約 4 秒進入 `Global Skill Queue` 作為預讀；Queue 仍依真實 Ready Time 排序，技能只有 Ready 後才會施放，施放前死亡則移出 Queue
-   技能施放期間進入 Slow State，普通攻擊節奏約降低 50%，但不 Freeze 全場
-   戰場下方、戰鬥日誌上方顯示最多 6 格 Skill Queue UI，只顯示單位小頭像；最左側代表下一位施放者
-   角色旁技能名稱、CD 數字、冷卻條與角色旁技能提示正式移除
-   同時間禁止多個技能同時演出；所有重要事件必須進入 Focus Queue
-   普攻屬背景節拍，不進入 Focus Queue，不可搶技能焦點
-   背景持續交戰，但重要瞬間自然浮出；不可 Freeze 全場
-   Focus Window 建議 1.8～3 秒，用於理解單一焦點事件
-   Focus Gap 建議 1.4～3 秒，用於呼吸與資訊消化
-   Boss 技能需保留清楚焦點與可讀提示，但不可加入電影式長停頓或全場 Freeze
-   Boss skill 接近 ready 或位於 Queue 第一格時，只允許低存在感微亮與 110%～120% 微縮放；禁止常駐 spotlight、巨大警告、強 bloom、鏡頭強制聚焦
-   普攻以微小動作與血條變化為主；一般攻擊約 80% 不顯示跳字
-   命中反饋採短促微閃光，普通命中閃光約 0.05～0.08 秒；遠程／指定目標攻擊可使用低透明 Target Line 輔助 source-target 閱讀，近戰不使用 Target Line；傷害數字維持在目標身體上方並錯開顯示
-   DOT 維持低干擾呈現，不連續刷出細碎跳字
-   DOT、Buff tick、光環、小型 Debuff、小治療與小攻擊屬背景事件，不應與主要事件競爭視覺焦點
-   受擊單位固定站位，不因普通攻擊或技能演出產生擊退位移
-   正式戰鬥系統不採用 `Knockback／擊退` 狀態或強制位移效果
-   同場最多 4 名角色、1 名召喚物、6 名敵人
-   固定視角；普通傷害數字與特效保持低頻
-   戰鬥遠征畫面不提供戰鬥加速按鍵；目前固定 1x 觀賞節奏
-   禁止同步全隊冷卻、禁止改成傳統回合制或全場停止式回合、禁止全場長時間停頓、禁止為可讀性改動怪物數值或技能平衡
-   可讀性原型測試若仍感到擁擠，優先增加 `Focus Gap`，其次才微調 action-focus micro stagger；目前測試值為普通行動 0.40 秒、召喚行動 0.30 秒、主要技能起手 0.45 秒；不可破壞 Focus Queue 方向

演出模式：

-   完整
-   簡化（推薦）
-   極簡

以上模式免費提供，不作為付費解除干擾項目。

------------------------------------------------------------------------

# 酒館主基地（正式版）

Hub Tavern 是唯一 home screen。

正式不採用：

- town home screen
- function-button lobby

## Tavern Layout

Tavern primary visible areas 必須包含：

- window
- bar counter
- fireplace
- six-seat round table
- upper/lower traveler area
- bard
- blacksmith area

Market / warehouse / black market 不佔據 tavern primary visual space。

## Six-Seat Round Table

六人圓桌是 Hub Tavern 的視覺與功能核心。

正式規則：

- 六人圓桌正式取代舊遠征入口。
- 圓桌顯示已招募遠征成員。
- Leader 固定坐 primary seat。
- 其他成員可換座位。
- 空座位保持可見。

正式世界地圖入口：

Hub Tavern → 六人圓桌 → 1～2 秒 zoom transition → World Map

## Traveler System

Traveler refresh periods：

- Day
- Dusk
- Night

規則：

- Traveler professions 不綁定刷新時段。
- 被招募 traveler 會離開 traveler area。
- passerby NPC 補上視覺空缺。

## Bard System

Bard 內容包含：

- rumors
- Boss rumors
- black market clues
- market hints
- world-event hints
- implicit tutorials
- small lyrics

Bard 約每 2～3 小時更新。

## Story Log

Story Log 是 Battle Log / Loot Log 之外的第三 log tab。

Story Log 記錄：

- Boss arrival
- Boss skills
- micro events
- world events
- black market rumors
- bard rumors
- character death records
------------------------------------------------------------------------

# 世界地圖／遠征（正式版）

核心：

玩家掌控感 \> 旅行感

正式流程：

Hub Tavern → 六人圓桌 → 1～2 秒 zoom transition → World Map → 遠征開始 → 戰鬥循環 → 玩家撤退 / 返回 Hub Tavern

World Map formal direction：

- 使用 central kingdom + radial world-map structure。
- 正式方向是 mobile portrait Navigation Screen。
- Open regions 圍繞 central kingdom，顯示在單一 portrait screen。
- Region selection 顯示 Selected / Available state。
- 不使用 large draggable world map / Camera / Drag / Zoom。
- 不使用 linear chapter-stage selection。

第一章：

王國邊境：

-   草原商路
-   邊境營地
-   潮濕沼地
------------------------------------------------------------------------

# 遠征／掛機循環

遭遇敵人 → 自動戰鬥 → 獲得素材／金幣／半成品／核心材料 → 場景推進 → 遭遇事件 → 菁英怪（隨機） →
Boss（隨機） → 循環

規則： - 玩家撤退前不離開區域 - 行囊滿停止拾取 -
金幣／經驗最多累積12小時

------------------------------------------------------------------------

# 素材經濟循環（正式版）

採用：
- 基礎素材
- 基礎加工品
- 穩定消耗池
- 素材來源分流
- 長期金幣循環

封測正式素材流程：

```text
基礎素材
→ 基礎加工品
→ 裝備
```

裝備／素材正式規則：

- EQUIPMENT_CURRENT.md 是裝備、素材、鐵匠、掉落規則的唯一正式規格入口。
- WORKSHOP_CURRENT.md 是工坊職責與基礎加工品規則的唯一正式規格入口。
- 普通怪低率掉落白裝不加入系統；所有怪物不直接掉落可穿戴成品裝備。
- 普通怪掉落素材與金幣；精英怪掉落高級素材、基礎加工品來源、殘缺裝素材；Boss 掉落 Boss 素材與 Boss 核心素材。
- 裝備來源以鐵匠製作為主；怪物只提供素材、核心材料、Boss 素材、Boss 核心素材與殘缺裝素材，不提供可穿戴成品裝備。
- 一般怪物素材名稱必須引用 monster_material_master_database.md；殘缺裝素材不是怪物素材，獨立於 monster_material_master_database.md。
- 殘缺裝資料庫為 BROKEN_EQUIPMENT_DATABASE.md；後續紫裝配方必須引用本資料庫。
- monster_material_master_database.md 優先於 material_usage / equipment / recipe / balance；素材用途資料庫與配方資料庫不得自行創造母資料庫不存在的怪物素材名稱。
- 工坊只負責飾品、基礎加工品、藥劑、卷軸。
- 鐵匠負責武器、防具、白裝、綠裝、藍裝、紫裝、暗金裝。
- 白裝、綠裝、藍裝正式流程：怪物素材／場景素材 → 工坊加工一次 → 基礎加工品 → 鐵匠製作裝備。
- 白裝、綠裝、藍裝不需要第二層加工。
- 紫裝正式流程：基礎加工品 + 殘缺裝素材 → 鐵匠製作紫裝。
- 紫裝額外需求殘缺裝素材，不需要文明加工品。
- 暗金正式流程：基礎加工品 + Boss素材 + Boss核心素材 → 鐵匠製作暗金裝。
- 暗金額外需求 Boss 素材與 Boss 核心素材，不需要文明加工品。
- 裝備品質與定位：白裝為基礎過渡裝；綠裝為小型 Build 過渡裝；藍裝為正式 Build 起點；紫裝為核心 Build 裝；暗金為 Boss 榮耀裝。
- 白裝、綠裝、藍裝未來可由 Codex 依照規則與素材資料庫批次生成。
- 紫裝與暗金裝不可自動大量生成，需先依設計討論定案。
- 紫裝目標取得節奏為 1～2 天；Boss／暗金裝目標取得節奏為 2～5 天，第一章平均 3～4 天。
- 殘缺裝不是藍裝素材；殘缺裝定位為紫裝核心素材；殘缺裝不是成品裝備，不可直接裝備。
- 每章殘缺裝數量控制在 2～4 件；每章至少 1 件殘缺裝可製作全職業通用飾品。
- 殘缺裝不需要覆蓋所有職業，依章節世界觀決定；某章已支援的職業，下一章不必再重複支援。
- 未獲殘缺裝支援的職業，仍可透過基礎加工品製作白裝、綠裝、藍裝，並透過殘缺裝素材路線製作紫裝，不可被卡死。
- Boss 裝不強制要求玩家從白裝一路升到紫裝。
- 強化系統、加工系統、進化系統可保留設計資料，但封測前只允許採用已明確定案的部分；進化系統封測前不實作。
- 本階段不要生成完整白裝、綠裝、藍裝表。
- 本階段不要生成紫裝或暗金裝表。
- Chapter 01 場景素材定位：怪物素材支援裝備主循環；場景素材支援旅團支援循環。
- Chapter 01 場景素材用途：廢棄鐵片／荒廢木材／王國舊布料／汙染結晶碎片用於基礎加工品方向；荒野草藥／毒沼草用於藥劑方向；乾燥獸骨／邊境石材用於飾品方向。
- Chapter 01 Beta 工坊保留基礎加工品、藥劑、飾品；卷軸系統暫不開放。
- 腐化木枝保留為卷軸系統／特殊消耗品 Future Reserved，不作為 Chapter 01 Beta 正式用途。

封測版本暫不採用：

- 文明加工品
- 高階文明素材
- 王國精鋼
- 皇家鍛鐵
- 王國紋章鋼片
- 第二層加工鏈
- 第三層加工鏈

------------------------------------------------------------------------

# 行囊系統（正式版）

採： 旅團容量制（Capacity）

不採： 格子背包

容量： 120 → 180 → 260 → 360 → 500 → 800+

遠征拾取： - 平衡探索 - 素材收集 - 半成品／核心材料回收 - 高價值探索

消耗品容量摘要：

- 消耗品不參與行囊容量、素材容量、遠征容量計算。
- 行囊滿停止拾取僅影響怪物素材、場景素材、半成品、裝備素材。
- 行囊滿停止拾取不影響消耗品倉庫與特殊收藏倉庫。
- 消耗品倉庫與特殊收藏倉庫獨立管理。
- 消耗品倉庫包含藥劑、卷軸、支援品；特殊收藏倉庫包含寶箱、活動箱、世界寶箱、特殊收藏品。
------------------------------------------------------------------------

# 職業方向（正式版）

初始職業：

-   衛兵
-   弓箭手
-   法師
-   見習祭司
-   遊蕩者

------------------------------------------------------------------------

# 正式不採用方向

-   前後排
-   SSR抽卡
-   十連抽
-   格子背包
-   MMORPG自由跑圖
-   紙娃娃系統
-   高數值膨脹
-   高干擾 UI

------------------------------------------------------------------------

# Superseded Rules

The following rules are deprecated and must not be used as current design direction:

- map table / 地圖桌 as formal expedition / World Map entry
- linear chapter-stage selection
- town screen as alternative home screen
- function-button lobby presentation
- market / warehouse / black market occupying primary tavern visual space
- large draggable world map with Camera / Drag / Zoom as formal World Map direction

------------------------------------------------------------------------

# Codex開發方向

優先： 主循環可玩化

流程： Hub Tavern → 六人圓桌 → 1～2 秒 zoom transition → World Map → 遠征開始 → 戰鬥循環 → 玩家撤退 / 返回 Hub Tavern

## 10. Safe Merge Stage 1 Runtime Alignment

- Hub Tavern v2.2 prototype scene is now the project startup scene for verification: `res://scenes/HubTavernPrototype.tscn`.
- The legacy `res://scenes/TavernMainScene.tscn` remains preserved and unchanged as a rollback point.
- World Map Prototype v1 is present at `res://scenes/WorldMapPrototype.tscn` and is entered only through the six-seat round table prototype flow.
- This merge does not add expedition logic, combat behavior, or worldbuilding changes.







