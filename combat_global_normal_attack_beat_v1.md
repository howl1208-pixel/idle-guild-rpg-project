Version: v1
Status: REVIEW
Scope: Combat Prototype

---

Purpose

建立：

«Global Normal Attack Beat（全場普通攻擊節拍）»

核心目標：

- 避免全場普通攻擊過度躁動
- 提升戰鬥可閱讀性
- 維持旅團交戰感
- 保持 Combat Focus System 技能焦點
- 保留職業差異與節奏感
- 避免高敏角色造成機關槍式戰鬥

正式哲學：

«普攻是全場節拍，而不是各打各的。»

---

Core Philosophy

普通攻擊：

不是：

«各單位獨立計時器自由攻擊»

而是：

«全場共享攻擊節拍（Global Beat）»

正式哲學：

«世界在流動，但不能躁動。»

---

Global Normal Attack Beat Rule

正式定案：

«任意兩次普通攻擊之間
最短間隔 = 1 秒»

公式概念：

Next Normal Attack Time
≥
Previous Normal Attack + 1.0 秒

正式方向：

«全場一次只發生一個普通攻擊節點。»

避免：

0.00 衛兵普攻
0.20 野狼普攻
0.40 遊蕩者普攻
0.70 哥布林普攻

造成：

«機關槍式戰鬥
畫面躁動
持續受擊感»

---

Example

正式節奏：

0.00 衛兵普攻

1.00 野狼普攻

2.00 遊蕩者普攻

3.00 哥布林普攻

正式哲學：

«戰場有呼吸。»

而不是：

«全場亂打。»

---

Agility Rule

敏捷：

«不可突破全場 1 秒節拍»

敏捷不允許：

- 突破 Global Beat
- 插隊破壞節拍
- 高頻亂打

正式方向：

«敏捷影響下一次普通攻擊機率與排序權重。»

---

Agility Effect

敏捷：

影響：

«Normal Attack Priority Weight»

代表：

高敏單位：

«更容易取得下一次普通攻擊權»

例如：

低敏：

衛兵
重裝敵人
Boss

較少輪到。

高敏：

遊蕩者
狼類
高速怪物

更容易輪到。

但：

仍必須遵守：

全場普攻最短間隔 ≥ 1 秒

正式哲學：

«高敏是更靈巧，不是更吵。»

---

Combo Exception Rule

以下情況：

允許突破：

«Global Beat 1 秒限制»

但：

僅限：

«同一次攻擊事件（Attack Package）»

不是：

«新的一次普通攻擊輪次»

---

Allowed Cases

允許：

職業被動

例如：

雙劍士
25% 普攻雙擊

---

裝備效果

例如：

雙擊護符
追擊短刃
連射弓

---

技能追加普攻

例如：

追擊箭
額外斬擊
追加一刀

---

Double Strike Example

合法：

0.00 雙劍士第一擊

0.18 第二擊（雙擊）

1.00 野狼普攻

注意：

第二擊：

«不重置 Global Beat»

正確：

0.00 第一擊

0.18 第二擊

1.00 下一次全場普攻

禁止：

0.00 第一擊

0.18 第二擊

↓

1.18 下一次普攻

原因：

«雙擊屬於同一次 Attack Package。»

不是：

«獨立輪次。»

---

Skill Focus Slow Alignment

當技能施放：

戰場：

«進入 Slow State»

正式：

«全場節奏降低約 50%»

普通攻擊：

同步變慢。

例如：

原本：

1 秒 Global Beat

技能期間體感：

約 2 秒

正式哲學：

«技能是一瞬間，世界變慢。»

---

Comfort Mode Alignment

Comfort Mode：

普通攻擊：

- 簡化演出
- 不顯示普通攻擊戰場跳字
- 傷害進戰鬥日誌
- 保留血條變化
- 保留微小 Hit Flash
- 保留小型受擊震動

避免：

- 普攻高頻動畫
- 滿畫面數字
- 普攻搶技能焦點

---

Player Experience Goal

玩家觀看戰鬥：

應自然感受到：

砍……

停……

咬……

停……

射……

停……

技能來了……

世界慢下來……

而不是：

砍砍砍砍砍

一直受擊

一直亂打

---

Final Philosophy

不是：

«每個人一直亂打»

而是：

«戰場有節拍，角色有特色。»

一句話：

«普攻遵守節拍，連擊是例外。»
