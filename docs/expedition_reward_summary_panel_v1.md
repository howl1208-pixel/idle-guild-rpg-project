# Expedition Reward Summary Panel v1

## Purpose

`ExpeditionRewardSummaryPanel` completes the first retreat return loop:

```text
BattleScene
-> Retreat
-> Expedition Reward Summary
-> Confirm
-> TavernMainScene
```

It is a quiet travel report, not an item shower or economy settlement screen.

## Scene Integration

- Source action: `res://scenes/ExpeditionHUD.tscn` retreat button
- Summary scene: `res://scenes/ExpeditionRewardSummaryPanel.tscn`
- Summary controller: `res://scripts/expedition_reward_summary_panel.gd`
- Return destination: `res://scenes/TavernMainScene.tscn`

## Displayed Report

- Selected route name, resolved from `selected_expedition_route`.
- Expedition duration, received from `expedition_duration_seconds`.
- Mock gold and EXP totals.
- Mock material list.
- Mock enemies, elite, and Boss encounter counts.
- Mock capacity result.

If no known selected route is available, the report displays `未知路線`.

## Interaction

- Retreat from battle opens the portrait report scene first.
- `確認並返回酒館` returns to `TavernMainScene` in landscape layout.
- The close button and Escape perform the same return action.

## Guardrails

- Values are placeholder presentation only.
- No real economy, loot settlement, EXP award, or capacity mutation is performed.
- Battle and tavern layout are not redesigned.
- Presentation remains a dark parchment-style journal with one primary action.

## Known Limits

- Report values are fixed mocked results.
- Duration covers the active battle visit only.
- Route selection does not influence the mocked reward list yet.
