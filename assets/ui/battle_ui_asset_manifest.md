# Battle UI Asset Manifest

Godot target: 3.6.1  
Project resolution: 720 x 1280 portrait  
Style: compact 2D pixel UI, dark fantasy test-build palette

## Naming Rules

- Use lowercase English names.
- Use underscores between words.
- Keep dimensions in the filename when the asset has a fixed UI size.
- Do not use spaces or Chinese characters in imported Godot asset filenames.

## Battle Frames

| File | Size | Use |
|---|---:|---|
| `battle/ui_battle_panel_frame_640x160.png` | 640x160 | General battle message/status frame |
| `battle/ui_battle_log_frame_640x190.png` | 640x190 | Battle log panel frame |
| `battle/ui_battle_unit_frame_player_140x150.png` | 140x150 | Player unit card frame |
| `battle/ui_battle_unit_frame_enemy_140x150.png` | 140x150 | Enemy unit card frame |
| `battle/ui_battle_support_slot_64x64.png` | 64x64 | Support character slot |
| `battle/ui_battle_speed_button_64x64.png` | 64x64 | Battle speed cycle button |

## HP Bar

| File | Size | Use |
|---|---:|---|
| `battle/ui_battle_hp_bar_frame_128x18.png` | 128x18 | HP bar frame |
| `battle/ui_battle_hp_bar_fill_player_124x14.png` | 124x14 | Player HP fill |
| `battle/ui_battle_hp_bar_fill_enemy_124x14.png` | 124x14 | Enemy HP fill |

## Action Buttons

| File | Size | Use |
|---|---:|---|
| `buttons/ui_button_action_normal_120x64.png` | 120x64 | Bottom action button normal state |
| `buttons/ui_button_action_pressed_120x64.png` | 120x64 | Bottom action button pressed state |
| `buttons/ui_button_action_disabled_120x64.png` | 120x64 | Bottom action button disabled state |

## Status Icons

| File | Size | Use |
|---|---:|---|
| `icons/icon_buff_attack_up_32.png` | 32x32 | Attack buff |
| `icons/icon_buff_defense_up_32.png` | 32x32 | Defense buff |
| `icons/icon_buff_speed_up_32.png` | 32x32 | Speed buff |
| `icons/icon_buff_regen_32.png` | 32x32 | Regeneration buff |
| `icons/icon_debuff_poison_32.png` | 32x32 | Poison debuff |
| `icons/icon_debuff_burn_32.png` | 32x32 | Burn debuff |
| `icons/icon_state_dead_32.png` | 32x32 | Dead / revive waiting state |
| `icons/icon_loot_common_32.png` | 32x32 | Common loot event |

## Current Role

These are first-pass production placeholders. They are intended to replace gray UI blocks and confirm spacing, scale, and visual direction before detailed illustrated assets are made.

## Integration Status

The first-pass assets are applied at runtime by `res://scripts/battle_scene.gd`.

Current bindings:

- Top bar, bottom action bar, buff panel, and loot panel use panel frame textures.
- Player and enemy unit frame textures are kept as available assets, but the current battle view uses transparent unit panels so characters and enemies appear to stand in the scene.
- Player and enemy HP bars use separate fill textures.
- Battle log uses the larger log frame texture.
- Support slot and battle speed button use compact square textures.
- Bottom action buttons use normal, pressed, and disabled button textures.
- Left-side status slots now show icon placeholders for passive, aura, summon bonus, and temporary state.
- Unit status icons now display vertically beside units: player icons on the left side, enemy icons on the right side. These icons are display-only and do not accept clicks.
- The temporary status slot switches to the loot icon when a stage drop is generated, then resets on the next stage.
