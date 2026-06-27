# Tavern Main Scene v3

## Purpose

`TavernMainScene` is the formal tavern main-base scene for the civilization caravan world-expedition RPG direction.

The tavern is a low-pressure world interaction space. It should read as a living caravan base, not as a free-movement map, a gacha page, or a normal menu screen.

## Layout

- Scene: `res://scenes/TavernMainScene.tscn`
- Main controller: `res://scripts/tavern_main_scene.gd`
- Target orientation: landscape
- Target size: 1280 x 720

## Split Controllers

- `TavernBackground`: far/middle/foreground layers and micro atmosphere.
- `TavernInteractionPoints`: scene interaction hotspots.
- `TavernEventBoard`: low-interference world rumor board.
- `TavernTravelGate`: expedition gate interaction.
- `TavernNPCController`: small traveler idle performance.
- `TavernLightController`: Lighting Pass v1 source hierarchy and low-frequency light motion.
- `TavernParticleLayer`: low-cost dust, smoke, and ale vapor motion.
- `TavernAmbientEffects`: cold gate mist, wind strip, foreground shadows, and corner darkening.

## Included Elements

- Horizontal tavern main-base composition.
- Far layer:
  - night village
  - moonlight
  - weak outside lights
  - tavern street view
- Middle layer:
  - bar counter
  - wall rumor board
  - central map table
  - expedition gate
  - workshop corner
  - black market corner
  - bard corner
  - tavern travelers
- Foreground layer:
  - candle glow
  - light dust
  - blurred table corner
  - foreground shadow
- Low-frequency micro motion.
- Invisible scene interaction hotspots for all major tavern functions.
- Tooltip appears only on hover or click.
- Tavern life fragments:
  - barrels
  - mugs
  - small tables and chairs
  - rug
  - candles
  - bard corner
  - travel pack
  - wall weapons
  - ale haze
  - light dust

## Lighting Pass v1

Goal: make the tavern feel like a deep-night traveler rest place rather than a UI page.

Lighting focus:

- Map table is the primary warm focus.
- Bar counter is a secondary warm living area.
- Black market corner stays dark with weak green light.
- Travel gate uses colder moonlight and mist to imply the outside world.
- Rumor board receives only low warm readability light.

Atmosphere:

- Low-frequency dust.
- Subtle smoke wisps.
- Ale vapor near the table.
- Foreground dark shadow.
- Corner vignette darkening.

Guardrails:

- No neon.
- No full-screen glow.
- No high-frequency particles.
- No MMO-style visual noise.
- Lighting should guide the eye, not become UI.

## Guardrails

- No free movement.
- No manual combat controls.
- No gacha presentation.
- No large popup event UI.
- UI should remain calm, readable, and low-interference.
- Expedition entry should feel like a place in the tavern, not a detached menu.
- Interaction points are scene objects, not full-screen menu buttons.
- No persistent function labels.
- No visible debug boxes.
- No functional UI blocks over the tavern.

## World Map / Expedition Route Select Pass v1

- Clicking the map table opens `res://scenes/ExpeditionRoutePanel.tscn`.
- The route panel is an overlay; the tavern remains visible behind a dim background.
- Chapter 1 currently offers three fixed Kingdom Border routes.
- Starting an expedition passes the selected route ID and transitions to portrait battle.
- Full route rules are recorded in `docs/expedition_route_panel_v1.md`.

## Current Known Limits

- Uses placeholder Godot UI shapes instead of final pixel art.
- Interaction points currently update status text and event text only.
- Route selection, traveler management, recruitment, crafting, and shop flows are reserved for future scenes.
- Tavern travelers are placeholder pixel blocks and do not yet bind to party data.
- Tooltip text currently uses stable English labels until final Chinese font/text handling is locked.
