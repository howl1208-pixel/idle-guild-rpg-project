# combat_system_current.md

Version: v1
Status: CURRENT SOURCE OF TRUTH
Scope: Combat System

---

# Purpose

本文件為：

«Combat System 唯一真相文件（Single Source of Truth）»

用途：

- 提供正式戰鬥規則權威來源
- 提供 Combat Prototype 與實作依據
- 提供快速規則理解入口
- 避免引用過期規則與 Prototype

Priority:

1. "combat_system_current.md"
2. "GAME_CURRENT_VERSION.md"

Ignore:

- "Status = SUPERSEDED"
- "Status = ARCHIVE"

---

# Core Philosophy

正式哲學：

«普攻讓世界流動。
技能讓世界變慢。»

一句話：

«世界持續戰鬥，但技能輪流成為焦點。»

本系統：

不是：

- 真回合制
- 即時亂戰

而是：

«Real-Time Combat + Global Skill Queue»

---

# Battlefield Visual Rule

Rule ID:

«COMBAT_BATTLEFIELD_VISUAL_RULE_V4»

Status:

«FINAL»

Composition:

- Battlefield adopts Corridor Composition.
- A visual confrontation axis runs diagonally from player formation toward enemy formation.
- Player formation uses slight clockwise rotation, approximately 5～8 degrees.
- Enemy formation uses slight counter-clockwise rotation, approximately 5～8 degrees.
- Both formations must maintain a single-layer battlefield.
- Boss remains the visual center of enemy formation.
- Combat Focus Zone remains horizontal and centered.
- Upper-left background area becomes Chapter Landmark Zone.
- No units, UI, Target Lines, summons, or combat effects may occupy the Chapter Landmark Zone.
- Battlefield should visually read as a road, corridor, canyon path, border route, ruin passage, or forest trail depending on chapter theme.
- Travel feeling and confrontation readability take priority over battlefield symmetry.

Purpose:

«讓戰場讀起來像旅途中的路徑與遭遇，而不是對稱競技場。»

---

# Combat Tempo

正式方向：

«背景持續交戰，重要事件自然浮現。»

普攻：

«Background Rhythm»

技能：

«Focus Event»

正式目標：

«約 3 秒內只理解一件重要事件»

避免：

- 多技能同時演出
- 特效互打
- 資訊混亂
- 戰鬥不可閱讀


# Combat Battlefield Layout

Rule ID:

«COMBAT_BATTLEFIELD_LAYOUT_V1»

Status:

«FINAL»

Source:

«S1 Kingdom Border Battlefield Layout Refinement»

Purpose:

«鎖定所有章節戰鬥背景比例，使戰場優先服務可讀性、站位校準與 Mobile Portrait RPG UI 安全區。»

Fixed Ratio Rules:

1. Upper Landmark / Far Background Area:
   - Occupies approximately the upper 15%～20% of the screen.
   - Background landmark only.
   - No characters, monsters, UI, Target Lines, summons, or combat effects.
   - Chapter landmarks may change, but the ratio structure must not change.

2. Boss Anchor:
   - Uses an independent rear-center enemy anchor.
   - Separated from the 6 Enemy Formation.
   - Boss does not share normal Enemy slots.

3. Enemy Formation Area:
   - Upper half, right-biased.
   - Supports slight counter-clockwise Facing ↙.
   - Must support up to 6 Enemy Units.
   - Must not enter the Landmark Zone.

4. Combat Focus Zone:
   - Center screen.
   - Remains horizontal.
   - Used for Target Line, Skill FX, Boss Threat, and AoE readability.
   - Must not become a diagonal zone, trapezoid zone, or full-screen FX zone.

5. Player Formation Area:
   - Mid-lower, left-biased.
   - Supports slight clockwise Facing ↗.
   - Must support up to 4 Player Units.
   - Must not overlap the UI Safe Area.

6. UI Safe Area:
   - Bottom approximately 35%.
   - Reserved for Support Button, Summon Reserve, Battle Log Tabs, Battle Log, Skill / Gear / Team / Menu.
   - Must not be occupied by battlefield background placement or unit placement.

7. Corridor Axis:
   - Overall visual axis is bottom-left → upper-right.
   - Supports corridor confrontation readability.
   - Players face ↗.
   - Enemies face ↙.

Chapter Theme Application:

- CH01 Kingdom Border: Kingdom Wall / Watchtower / Banner
- CH02 Traveler Wastes: wasteland landmark / wind-eroded rock / dust horizon
- CH03 Skeleton Wasteland: gravestones / bones / dead trees
- CH04 Desert Ruined City: ruins / statues / dunes
- CH05 Holy Border: cathedral spire / holy emblem banner / white stone wall
- CH06+ remains out of current scope, but must follow the same layout ratio if opened later.
---

# Global Skill Queue

正式方向：

«技能依 Ready Time 排隊施放»

規則：

- 技能施放前約 4 秒加入 Queue 作為預讀
- Queue 依真實 Ready Time 排序
- 技能只有 Ready 後才會施放
- 同時間僅允許一個技能演出
- 技能施放時，其它技能等待
- 技能施放期間，新的技能可持續加入 Queue
- 尚未施放前死亡 → 技能取消並移出 Queue

正式哲學：

«一次只閱讀一個技能。»

---

# Source / Target Readability

正式方向：

«玩家必須看得出誰打誰。»

規則：

- 遠程攻擊可使用低透明短線提示攻擊者與目標
- 遠程治療、遠程 Buff、遠程 Debuff 與 Boss / Elite 指定目標技能可使用 Target Line
- 近戰攻擊不使用 Target Line，改以動作、前踏、hit reaction 閱讀
- 攻擊者可短暫微亮，但微亮不等於 Target Line
- 目標仍以短促 hit flash 與 HP 變化為主要反饋
- 提示時間必須短、透明、低干擾

避免：

- 大型箭頭
- 長時間鎖定線
- MMO 式目標框
- 角色擊退或強制位移

正式哲學：

«有線 = 遠程指定。
無線 = 近戰交鋒。»

---

# Skill Focus Slow

當任一技能施放：

戰場：

«進入 Slow State»

不是：

«Freeze»

正式方向：

«世界節奏降低約 50%»

---

# Slow State 保留

保留：

- 呼吸
- 待機
- Buff / Debuff 微動
- Status FX
- 普通攻擊

---

# Slow State 暫停

暫停：

- 其它技能施放

正式哲學：

«技能是一瞬間，世界變慢。»

---

# Normal Attack Rhythm

正式方向：

«普攻是全場節拍，而不是各打各的。»

不影響：

«技能 CD»

最低極限：

«任意兩次普通攻擊之間，全場最低間隔 = 1.0 秒»

任何高敏捷、Buff、加速、被動或裝備效果皆不得突破此 Global Beat。

敏捷：

«影響下一次普通攻擊 Priority Weight»

不是：

«突破全場節拍»

Combo / 追擊 / 雙擊例外：

僅可作為同一次 Attack Package 的追加 hit，不可重置 Global Beat。

---

# Attack Interval

公式方向：

Attack Interval
=
Base Rhythm × SPD Modifier

最終：

Attack Interval = max(計算結果, 1.0 秒)

---

# 職業節奏方向

衛兵

定位：

«沉重»

體感：

Base Rhythm 3.2 ~ 4.0 秒

---

遊蕩者

定位：

«快速»

體感：

Base Rhythm 2.0 ~ 2.8 秒，高敏後約 1.2 ~ 1.8 秒，但不得低於 1.0 秒

---

弓箭手

定位：

«中高速度»

體感：

Base Rhythm 2.4 ~ 3.0 秒，高敏後約 1.5 ~ 2.2 秒

---

法師 / 術士

定位：

«偏慢»

體感：

Base Rhythm 3.0 ~ 3.8 秒，高敏後約 2.0 ~ 2.8 秒

---

普通野獸

定位：

«短爆發撲擊»

體感：

Base Rhythm 2.2 ~ 3.0 秒，高敏後約 1.2 ~ 2.0 秒

---

重裝敵人 / Boss

定位：

«壓迫感、重量感»

體感：

Base Rhythm 3.5 ~ 5.0 秒

正式哲學：

«職業差異來自節拍。»

不是：

«技能數量或特效量。»

---

# Skill Queue UI

正式哲學：

«玩家看戰況，而不是盯冷卻。»

---

# UI 位置（直立式）

位置：

«戰場下方
戰鬥日誌上方»

排列方式：

«單列水平排列»

方向：

左 → 右

規則：

左側 = 下一位施放
右側 = 後續施放

---

# 顯示規則

正式：

«最多顯示 6 個 Queue»

不足：

«保持留白»

不使用：

- Placeholder
- 虛框
- 額外 UI 補位

---

# 顯示內容

只顯示：

«單位小頭像»

不顯示：

- 技能名稱
- 技能圖示
- CD 數字
- 倒數
- 進度條
- 額外文字

正式哲學：

«知道誰要動就夠。»

---

# 下一施放單位提示

左側第一位：

僅：

- 微亮
- 輕外框
- 小箭頭

避免：

- 高亮閃爍
- 大動畫
- 過度 UI 注意力

正式方向：

«低存在感提示。»

---

# Character Skill Cooldown UI

正式採用：

«完全移除角色旁技能 CD»

移除：

- 技能 icon
- CD 圓圈
- 倒數數字
- 冷卻條

原因：

- 手機直立畫面空間有限
- 已存在 Skill Queue UI
- 降低資訊疲勞

正式哲學：

«玩家看戰況，而不是看冷卻。»

---

# Comfort Mode

正式方向：

«降低資訊疲勞»

普通攻擊：

- 簡化演出
- 不顯示普通攻擊戰場跳字
- 保留血條變化

技能：

- 保留焦點
- 降低粒子量
- 降低亮度
- 略縮短演出

正式哲學：

«長時間觀看仍舒適。»

---

# Status Layering

正式方向：

«同類型狀態合併顯示»

避免：

- Buff / Debuff 污染畫面
- 手機 UI 過度擁擠

正式：

«低存在感、低渲染、可閱讀»

---

# Skill FX Philosophy

正式方向：

«小而精準、高辨識、低疲勞»

正式：

- 技能 FX 不佔滿畫面
- 優先角色輪廓辨識
- 技能為焦點
- 普攻降存在感

避免：

- 滿畫面技能特效
- MMO 式誇張粒子

---

# Threat Readability

精英 / Boss：

使用：

«Threat Marker»

方向：

«低存在感提示»

避免：

«MMO 式大型警告 UI»

正式哲學：

«玩家能預讀威脅，但不被 UI 轟炸。»

---

# Boss Focus Weight

正式方向：

«Boss Focus Emergence»

Boss Skill：

«最高 Focus Queue priority（S Priority）»

規則：

- Boss Skill 優先於 Elite Skill、Player Skill、Important Heal、Background Event
- Boss 位於 Skill Queue 第一格時，可使用 110% ~ 120% 微縮放
- Boss 位於 Skill Queue 第一格時，可使用 +10% ~ +20% 微亮
- Boss skill 接近 ready 時，Boss body 可使用 +5% ~ +10% 微亮
- Boss 指定目標技能保留低透明短 Target Line

禁止：

- 電影式停頓
- 強制鏡頭
- 巨大 warning FX
- MMORPG raid alert UI
- 常駐 Boss spotlight

正式哲學：

«dangerous but comfortable readability»

---

# Summon Slots

位置：

«玩家角色區右上方（微偏右上）»

正式：

«最多 4 格»

未召喚：

«高透明空框»

召喚後：

«自然填入»

正式方向：

«不與 Skill Queue 爭奪視覺焦點»

---

# Final Philosophy

不是：

«滿畫面技能亂炸»

也不是：

«真回合制停格»

而是：

«世界持續交戰，技能自然輪流被理解。»
