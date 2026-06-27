# combat_skill_trigger_system_v1.md

Status: REVIEW
Scope: Combat Skill Trigger Conditions / Global Skill Queue Gate

---

## Purpose

本文件整理技能觸發條件第一版，用於後續討論：

```text
Skill Ready 不等於 Skill Cast。
```

技能 CD 結束後只代表該技能進入 Ready 狀態。
只有符合 Trigger Condition 時，該技能才允許加入 Global Skill Queue。

本文件為 REVIEW，不修改 `combat_system_current.md` 正式規則，不代表已實作。

---

## Current Compatibility Note

目前正式戰鬥規則仍以 `combat_system_current.md` 與 `GAME_CURRENT_VERSION.md` 為準。

現行正式規則摘要：

- 採用 Real-Time Combat + Global Skill Queue。
- 技能依 Ready Time 進入 Queue 作為預讀。
- Queue 依真實 Ready Time 排序。
- 同時間僅允許一個技能演出。

本 REVIEW 提案補充一層未定案的 Trigger Gate：

```text
Cooldown Complete
→ Skill Ready
→ Trigger Condition Check
→ Queue Eligible
→ Global Skill Queue
→ Skill Cast
```

若本規則未來升級為正式規則，需同步調整 `combat_system_current.md` 中「Ready Time 進 Queue」的描述。

---

## Core Rule

### Skill Ready

Skill Ready 代表：

- 技能冷卻已結束。
- 技能具備被檢查觸發條件的資格。
- 技能尚未必然加入 Global Skill Queue。
- 技能尚未必然施放。

### Trigger Condition

Trigger Condition 代表：

- 技能在 Ready 後，是否符合實際施放需求。
- 條件成立時，技能才可加入 Global Skill Queue。
- 條件不成立時，技能維持 Ready，等待下一次檢查。
- 條件不成立不重置 CD。

### Queue Eligible

Queue Eligible 代表：

- 技能已 Ready。
- 技能觸發條件成立。
- 技能有有效施放目標。
- 技能尚未存在於 Global Skill Queue 中。

---

## Trigger Condition v1

### 1. Healing Skill

治療技能只有在符合以下條件時才允許加入 Global Skill Queue：

- 至少一名隊友生命低於該技能指定比例。
- 該隊友仍為有效治療目標。
- 技能 Ready。

若沒有隊友低於指定比例，治療技能維持 Ready，不加入 Queue。

建議目標選擇方向：

- 優先選擇生命比例最低的有效隊友。
- 若技能設計指定職業或站位條件，依技能資料覆寫。

---

### 2. Shield Skill

護盾技能只有在符合以下條件時才允許加入 Global Skill Queue：

- 至少一名隊友生命低於該技能指定比例。
- 該隊友仍為有效護盾目標。
- 技能 Ready。

若沒有隊友低於指定比例，護盾技能維持 Ready，不加入 Queue。

可選擇的後續審核條件：

- 目標已有同類護盾時，若剩餘時間充足，可不觸發。
- 目標已有同類護盾但即將結束時，可允許觸發。

---

### 3. Summon Skill

召喚技能只有在符合以下條件時才允許加入 Global Skill Queue：

- 場上沒有自身召喚物。
- 技能 Ready。
- 場上召喚物上限允許施放。

若自身召喚物仍存在，召喚技能維持 Ready，不加入 Queue。

規則方向：

- 同一角色不應重複召喚同一召喚物造成堆疊。
- 若召喚物死亡或自然消失，該技能可在下一次 Trigger Check 時重新符合條件。

---

### 4. Buff Skill

Buff 技能只有在符合以下任一條件時才允許加入 Global Skill Queue：

- 目標身上不存在該 Buff。
- 目標身上該 Buff 剩餘時間過短。

同時需符合：

- 技能 Ready。
- 目標為有效 Buff 目標。

若 Buff 仍存在且剩餘時間充足，Buff 技能維持 Ready，不加入 Queue。

規則方向：

- 避免同類 Buff 無意義刷新。
- 避免 Buff 技能在戰鬥中搶占過多焦點。
- 剩餘時間門檻應由技能資料設定，不在本文件填數值。

---

### 5. Execute Skill

處決技能只有在符合以下條件時才允許加入 Global Skill Queue：

- 目標生命低於該技能指定比例。
- 目標仍為有效攻擊目標。
- 技能 Ready。

若沒有目標低於指定比例，處決技能維持 Ready，不加入 Queue。

規則方向：

- 處決技能應保留收割感。
- 不應在敵人生命充足時提前消耗技能焦點。
- 指定比例由技能資料設定，不在本文件填數值。

---

### 6. Pure Damage Skill

純傷害技能在符合以下條件時可加入 Global Skill Queue：

- 技能 Ready。
- 存在有效攻擊目標。

純傷害技能不需要額外生命比例、Buff、Debuff 或召喚狀態條件。

規則方向：

- 純傷害技能是最基本的 Ready 後可施放技能類型。
- 若未來某傷害技能帶有特殊條件，應改歸類為處決、Debuff、Buff 互動或其他條件技能。

---

### 7. Debuff Skill

Debuff 技能只有在符合以下任一條件時才允許加入 Global Skill Queue：

- 目標身上不存在該 Debuff。
- 目標身上該 Debuff 剩餘時間過短。

同時需符合：

- 技能 Ready。
- 目標為有效 Debuff 目標。

若 Debuff 仍存在且剩餘時間充足，Debuff 技能維持 Ready，不加入 Queue。

規則方向：

- 避免同類 Debuff 無意義刷新。
- 避免 Debuff 技能在戰鬥中搶占過多焦點。
- 剩餘時間門檻應由技能資料設定，不在本文件填數值。

---

## Trigger Check Timing

本文件不指定最終實作，但建議後續審核以下方向：

- 技能 CD 結束時進行一次 Trigger Check。
- 生命比例變化時，可重新檢查治療、護盾、處決技能。
- Buff / Debuff 新增、消失或接近結束時，可重新檢查對應技能。
- 召喚物死亡或消失時，可重新檢查召喚技能。
- 若技能已加入 Global Skill Queue，不應重複加入。

---

## Queue Cancellation Review Note

本文件暫不正式定案 Queue Cancellation。

後續可審核：

- 技能加入 Queue 後，若施放前目標死亡，依現行正式規則移出 Queue。
- 技能加入 Queue 後，若 Trigger Condition 已不成立，是否取消需另案討論。
- 為避免戰鬥閱讀混亂，取消規則不應造成 Queue UI 高頻跳動。

---

## Non-Goals

本文件不處理：

- 技能數值。
- 技能 CD 數值。
- 生命比例實際門檻。
- Buff / Debuff 剩餘時間門檻。
- 技能資料庫。
- Godot 實作。
- UI 改動。
- `combat_system_current.md` 正式規則修改。

---

## Summary

第一版核心結論：

```text
Ready = 冷卻完成，可被檢查。
Trigger = 條件成立，可進 Queue。
Queue = 等待焦點演出。
Cast = 實際施放。
```

技能是否施放不應只由 CD 決定。治療、護盾、召喚、Buff、處決與 Debuff 技能都需要符合各自 Trigger Condition；純傷害技能則在 Ready 且有有效目標後可進入 Global Skill Queue。