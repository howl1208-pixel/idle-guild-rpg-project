# CLASS_TREE_CURRENT

Status: Source Of Truth

Source priority:

1. Latest class advancement images.
2. `CBT_CLASS_ADVANCEMENT_AND_SKILL_UNLOCK_SCOPE_V1.md` for CBT unlock scope only.

Rules:

- The latest class advancement images are the only truth for class tree structure.
- Do not add professions that are not shown in the images.
- Do not fill missing professions by inference.
- If images conflict with older documents, the images win.
- If images conflict with older documents in a way that affects implementation, report the conflict and do not decide silently.
- CBT class advancement cap follows `CBT_CLASS_ADVANCEMENT_AND_SKILL_UNLOCK_SCOPE_V1.md`.

---

## CBT Scope

CBT advancement cap:

- 1轉 to 6轉: available for CBT implementation.
- 7轉 to 9轉: data retained, not open in CBT.

Skill unlock rule:

- Normal attack: 1 fixed.
- Active skills: 2 fixed.
- Passive skills: 2 fixed.
- 5轉 unlocks active skill 2.
- 6轉 unlocks passive skill 2.

Appearance scope:

- 1轉 to 3轉: 初階冒險者.
- 4轉 to 6轉: 專業職業.
- 7轉 to 9轉: 傳說職業.
- CBT implements only the first two appearance stages.

---

## Source Images

- `Photo 1.jpg`: 遊蕩者派生表.
- `Photo 2.jpg`: 衛兵派生表.
- `Photo 3.jpg`: 祭司派生表.
- `Photo 4.jpg`: 法師派生表.
- `Photo 5.jpg`: 弓箭手派生表.

---

## Column Legend

- `1轉` to `6轉`: CBT open scope.
- `7轉` to `9轉`: retained data, CBT locked.
- Empty or inferred professions are not allowed.

---

## 遊蕩者 Class Tree

| Branch | 1轉 | 2轉 | 3轉 | 4轉 | 5轉 | 6轉 | 7轉 | 8轉 | 9轉 |
|---|---|---|---|---|---|---|---|---|---|
| 夜行者系 | 遊蕩者 | 流浪客 | 夜行者 | 影行者 | 影刃 | 刺客 | 影縫師 | 噬影者 | 黑夜 |
| 密探系 | 遊蕩者 | 流浪客 | 傳訊者 | 密探 | 夜衛 | 黑羽特務 | 特務隊長 | 暗鴉 | 暗部總長 |
| 歌者 / 吟遊系 | 遊蕩者 | 流浪客 | 傳訊者 | 歌者 | 戲子 | 吟遊詩人 | 旋律使 | 謠傳者 | 絕唱者 |
| 小丑系 | 遊蕩者 | 流浪客 | 傳訊者 | 歌者 | 戲子 | 小丑 | 幻笑師 | 混沌小丑 | 命運嘲弄者 |

Image edge record:

- 遊蕩者 -> 流浪客.
- 流浪客 -> 夜行者.
- 流浪客 -> 傳訊者.
- 夜行者 -> 影行者.
- 影行者 -> 影刃.
- 影刃 -> 刺客.
- 刺客 -> 影縫師.
- 影縫師 -> 噬影者.
- 噬影者 -> 黑夜.
- 傳訊者 -> 密探.
- 密探 -> 夜衛.
- 夜衛 -> 黑羽特務.
- 黑羽特務 -> 特務隊長.
- 特務隊長 -> 暗鴉.
- 暗鴉 -> 暗部總長.
- 傳訊者 -> 歌者.
- 歌者 -> 戲子.
- 戲子 -> 吟遊詩人.
- 吟遊詩人 -> 旋律使.
- 旋律使 -> 謠傳者.
- 謠傳者 -> 絕唱者.
- 戲子 -> 小丑.
- 小丑 -> 幻笑師.
- 幻笑師 -> 混沌小丑.
- 混沌小丑 -> 命運嘲弄者.

---

## 衛兵 Class Tree

| Branch | 1轉 | 2轉 | 3轉 | 4轉 | 5轉 | 6轉 | 7轉 | 8轉 | 9轉 |
|---|---|---|---|---|---|---|---|---|---|
| 騎士系 | 衛兵 | 盾衛兵 | 先鋒 | 騎士 | 聖盾騎士 | 皇家騎士 | 王國近衛 | 白銀統帥 | 獅心王 |
| 大盾系 | 衛兵 | 盾衛兵 | 大盾守衛 | 重盾衛士 | 鐵甲守衛 | 皇家壁壘 | 堡壘 | 王國之盾 | 不滅 |
| 重劍系 | 衛兵 | 盾衛兵 | 雙劍士 | 雙刃鬥士 | 修羅劍士 | 劍豪 | 重劍者 | 斬鐵巨劍者 | 斬岳 |
| 刀鋒系 | 衛兵 | 盾衛兵 | 雙劍士 | 雙刃鬥士 | 修羅劍士 | 劍豪 | 刀鋒劍豪 | 處刑者 | 無雙 |

Image edge record:

- 衛兵 -> 盾衛兵.
- 盾衛兵 -> 先鋒.
- 先鋒 -> 騎士.
- 騎士 -> 聖盾騎士.
- 聖盾騎士 -> 皇家騎士.
- 皇家騎士 -> 王國近衛.
- 王國近衛 -> 白銀統帥.
- 白銀統帥 -> 獅心王.
- 盾衛兵 -> 大盾守衛.
- 大盾守衛 -> 重盾衛士.
- 重盾衛士 -> 鐵甲守衛.
- 鐵甲守衛 -> 皇家壁壘.
- 皇家壁壘 -> 堡壘.
- 堡壘 -> 王國之盾.
- 王國之盾 -> 不滅.
- 盾衛兵 -> 雙劍士.
- 雙劍士 -> 雙刃鬥士.
- 雙刃鬥士 -> 修羅劍士.
- 修羅劍士 -> 劍豪.
- 劍豪 -> 重劍者.
- 重劍者 -> 斬鐵巨劍者.
- 斬鐵巨劍者 -> 斬岳.
- 劍豪 -> 刀鋒劍豪.
- 刀鋒劍豪 -> 處刑者.
- 處刑者 -> 無雙.

---

## 祭司 Class Tree

| Branch | 1轉 | 2轉 | 3轉 | 4轉 | 5轉 | 6轉 | 7轉 | 8轉 | 9轉 |
|---|---|---|---|---|---|---|---|---|---|
| 聖職系 | 見習祭司 | 祭司 | 聖職者 | 聖癒使 | 神官 | 大主教 | 神諭賢者 | 光輝 | 天使 |
| 森林祭司系 | 見習祭司 | 祭司 | 森林祭司 | 樹語者 | 荒野祭司 | 德魯伊 | 大地德魯伊 | 世界樹使徒 | 森靈 |
| 死靈系 | 見習祭司 | 祭司 | 骸骨學徒 | 死靈術士 | 喚靈者 | 屍術師 | 亡魂支配者 | 冥河差役 | 死神 |
| 女巫系 | 見習祭司 | 祭司 | 骸骨學徒 | 死靈術士 | 見習女巫 | 女巫 | 詛咒使 | 魔藥師 | 魔女 |

Image edge record:

- 見習祭司 -> 祭司.
- 祭司 -> 聖職者.
- 聖職者 -> 聖癒使.
- 聖癒使 -> 神官.
- 神官 -> 大主教.
- 大主教 -> 神諭賢者.
- 神諭賢者 -> 光輝.
- 光輝 -> 天使.
- 祭司 -> 森林祭司.
- 森林祭司 -> 樹語者.
- 樹語者 -> 荒野祭司.
- 荒野祭司 -> 德魯伊.
- 德魯伊 -> 大地德魯伊.
- 大地德魯伊 -> 世界樹使徒.
- 世界樹使徒 -> 森靈.
- 祭司 -> 骸骨學徒.
- 骸骨學徒 -> 死靈術士.
- 死靈術士 -> 喚靈者.
- 喚靈者 -> 屍術師.
- 屍術師 -> 亡魂支配者.
- 亡魂支配者 -> 冥河差役.
- 冥河差役 -> 死神.
- 死靈術士 -> 見習女巫.
- 見習女巫 -> 女巫.
- 女巫 -> 詛咒使.
- 詛咒使 -> 魔藥師.
- 魔藥師 -> 魔女.

---

## 法師 Class Tree

| Branch | 1轉 | 2轉 | 3轉 | 4轉 | 5轉 | 6轉 | 7轉 | 8轉 | 9轉 |
|---|---|---|---|---|---|---|---|---|---|
| 火焰系 | 魔法學徒 | 魔法使 | 奧術學徒 | 奧術專家 | 火焰學徒 | 燃靈使 | 焚焰者 | 焚天 | 日冕 |
| 雷電系 | 魔法學徒 | 魔法使 | 奧術學徒 | 奧術專家 | 雷電學徒 | 雷鳴使 | 雷劫者 | 雷刃師 | 蒼雷 |
| 冰霜系 | 魔法學徒 | 魔法使 | 奧術學徒 | 奧術專家 | 冰霜學徒 | 霜信使 | 凍結師 | 冰河祭師 | 絕對零度使 |
| 大地系 | 魔法學徒 | 魔法使 | 奧術學徒 | 奧術專家 | 大地學徒 | 崩壞使 | 裂地師 | 造山者 | 粹鍊者 |
| 學者系 | 魔法學徒 | 魔法使 | 奧術學徒 | 奧術專家 | 學者 | 奧術導師 | 奧術支配者 | 賢者 | 混沌 |

Image edge record:

- 魔法學徒 -> 魔法使.
- 魔法使 -> 奧術學徒.
- 奧術學徒 -> 奧術專家.
- 奧術專家 -> 火焰學徒.
- 火焰學徒 -> 燃靈使.
- 燃靈使 -> 焚焰者.
- 焚焰者 -> 焚天.
- 焚天 -> 日冕.
- 奧術專家 -> 雷電學徒.
- 雷電學徒 -> 雷鳴使.
- 雷鳴使 -> 雷劫者.
- 雷劫者 -> 雷刃師.
- 雷刃師 -> 蒼雷.
- 奧術專家 -> 冰霜學徒.
- 冰霜學徒 -> 霜信使.
- 霜信使 -> 凍結師.
- 凍結師 -> 冰河祭師.
- 冰河祭師 -> 絕對零度使.
- 奧術專家 -> 大地學徒.
- 大地學徒 -> 崩壞使.
- 崩壞使 -> 裂地師.
- 裂地師 -> 造山者.
- 造山者 -> 粹鍊者.
- 奧術專家 -> 學者.
- 學者 -> 奧術導師.
- 奧術導師 -> 奧術支配者.
- 奧術支配者 -> 賢者.
- 賢者 -> 混沌.

---

## 弓箭手 Class Tree

| Branch | 1轉 | 2轉 | 3轉 | 4轉 | 5轉 | 6轉 | 7轉 | 8轉 | 9轉 |
|---|---|---|---|---|---|---|---|---|---|
| 弩手系 | 獵人 | 弓箭手 | 弓箭隊士 | 弩兵 | 皇家弩手 | 金羽衛士 | 破風者 | 貫穿者 | 穿雲 |
| 長弓系 | 獵人 | 弓箭手 | 弓箭隊士 | 長弓手 | 皇家射手 | 銀羽衛士 | 乘風者 | 狙擊 | 鷹眼 |
| 森林守望系 | 獵人 | 弓箭手 | 遊獵者 | 叢林獵手 | 遊俠 | 守望者 | 疾風射手 | 自然編織者 | 森林之母 |
| 匿蹤系 | 獵人 | 弓箭手 | 遊獵者 | 叢林獵手 | 遊俠 | 匿蹤者 | 暗林獵人 | 黑暗妖精 | 暗蝕 |

Image edge record:

- 獵人 -> 弓箭手.
- 弓箭手 -> 遊獵者.
- 弓箭手 -> 弓箭隊士.
- 弓箭隊士 -> 弩兵.
- 弩兵 -> 皇家弩手.
- 皇家弩手 -> 金羽衛士.
- 金羽衛士 -> 破風者.
- 破風者 -> 貫穿者.
- 貫穿者 -> 穿雲.
- 弓箭隊士 -> 長弓手.
- 長弓手 -> 皇家射手.
- 皇家射手 -> 銀羽衛士.
- 銀羽衛士 -> 乘風者.
- 乘風者 -> 狙擊.
- 狙擊 -> 鷹眼.
- 遊獵者 -> 叢林獵手.
- 叢林獵手 -> 遊俠.
- 遊俠 -> 守望者.
- 守望者 -> 疾風射手.
- 疾風射手 -> 自然編織者.
- 自然編織者 -> 森林之母.
- 遊俠 -> 匿蹤者.
- 匿蹤者 -> 暗林獵人.
- 暗林獵人 -> 黑暗妖精.
- 黑暗妖精 -> 暗蝕.

---

## Weapon Culture Scope

From `CBT_CLASS_ADVANCEMENT_AND_SKILL_UNLOCK_SCOPE_V1.md`:

- 衛兵: 劍 -> 劍盾 / 連枷 / 雙劍 / 巨劍.
- 弓箭手: 弓 -> 十字弓 / 長弓 / 精靈弓 / 黑妖弓.
- 遊蕩者: 匕首 -> 雙刃 / 袖劍 / 樂器.
- 術士: 法杖 + 法器.
- 法師: 法杖 + 魔法書.

Do not modify weapon culture without explicit user request.

---

## Prohibited Changes

Without explicit user request:

- Do not add professions.
- Do not add factions.
- Do not rename professions.
- Do not reorder advancement paths.
- Do not adjust weapon culture.
- Do not fill missing advancement nodes.
- If image and document conflict, report the conflict.
- Do not decide conflicts silently.
