Version: v2
Status: REVIEW
Scope: Combat Prototype

---

Purpose

建立 Target Line（命中線）正式使用規則。

核心目標：

- 提升遠程攻擊可閱讀性
- 避免近戰命中線造成畫面污染
- 保持對峙空白區乾淨
- 降低 4角色 + 6敵 情境下的資訊噪音
- 維持舒適觀看與低疲勞戰鬥體驗

正式哲學：

«命中線只給需要閱讀輔助的攻擊。»

---

Core Philosophy

Target Line：

不是：

«所有攻擊都顯示的 UI 線»

而是：

«遠程指定目標的低存在感輔助提示»

正式哲學：

«看得到攻擊關係，但不污染畫面。»

---

Enable Target Line

Target Line 僅適用於以下攻擊類型。

---

弓箭系

適用：

- 弓箭手
- 十字弓
- 長弓
- 精靈弓
- 黑妖弓

原因：

«遠距離射擊需要確認目標。»

---

遠程法師系

適用：

- 火球
- 雷擊
- 冰錐
- 奧術飛彈
- 遠程詛咒
- 遠程法術攻擊

原因：

«遠程法術命中目標不一定直觀，需要輔助閱讀。»

---

術士遠程指向技能

適用：

- 遠程治療
- 遠程 Buff
- 遠程 Debuff
- 遠程詛咒

不適用：

- 自身 Buff
- 範圍 Aura
- 召喚技能
- 無指定目標技能

原因：

«僅指定目標技能需要 Target Line。»

---

Boss / Elite 遠程技能

適用：

- Boss 遠程指定技能
- 精英怪遠程指定技能
- 投射物技能
- 遠距衝擊技能

原因：

«協助玩家理解被鎖定目標。»

---

Disable Target Line

以下類型不使用 Target Line。

---

近戰系

不適用：

- 衛兵近戰攻擊
- 遊蕩者近戰攻擊
- 狼類撲咬
- 盜匪刺擊
- 巨蜥撕咬
- 大部分近戰精英技能

原因：

近戰已有：

- 前踏
- 攻擊方向
- Hit Reaction
- Threat Marker

閱讀性足夠。

正式哲學：

«近戰靠動作閱讀，不靠線條閱讀。»

---

Visual Rule

Target Line 必須保持低存在感。

規格：

- 高透明
- 細線
- 低亮度
- 低飽和
- 短時間

建議時間：

0.15 ~ 0.30 秒

禁止：

- 高亮雷射線
- 常駐線
- 粗線
- 閃爍線
- MMO Warning 感

---

Role in Combat Reading

Target Line 屬於：

«Secondary Confirmation»

不是：

«Primary Focus»

閱讀順序：

角色前搖
↓
玩家理解誰施放
↓
Target Line 出現
↓
玩家理解目標是誰
↓
技能命中
↓
Hit Reaction

---

Battle Space Rule

Target Line 優先使用：

«雙方對峙空白區»

目的：

«讓資訊發生在角色之間，而不是角色身上。»

避免：

- 穿越多個角色身體
- 疊在 Buff / Debuff 上
- 干擾角色輪廓

---

Comfort Mode Alignment

Comfort Mode 下：

Target Line 保留。

但：

- 亮度降低
- 透明度提高
- 停留時間縮短

原因：

«Target Line 屬於戰況閱讀核心，但必須低干擾。»

---

Final Rule

遠程攻擊：

«可使用 Target Line»

近戰攻擊：

«不使用 Target Line»

正式哲學：

«有線 = 遠程指定
無線 = 近戰交鋒»
