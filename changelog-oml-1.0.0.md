---
layout: page
title: OML Changelog 1.0.0
permalink: /changelog/oml-1.0.0/
---

This is the full changelog of **Open Modular Lighting (OML) 1.0.0**, merged from all of its alpha and beta releases.
OML brings floodlights, a port of the 1.7.10 mod _FloodLights_, to 1.12.2, 1.20.1, 1.21.1 and 1.21.11.

The current pre-releases are:

| Minecraft | Loaders | Requires | Latest |
| --- | --- | --- | --- |
| 1.12.2 | Forge | OMLib 4.0.0-beta.4 or newer | 1.0.0-beta.8 (2026-10-27) |
| 1.20.1, 1.21.1 and 1.21.11 | Fabric 1.20.1, 1.21.1 and 1.21.11, NeoForge 1.21.1 and 1.21.11, Forge 1.20.1 | Fabric API on Fabric (OMLib is bundled) | 1.0.0-beta.10 (2026-10-27) |

**How to read this page:**
a line without a prefix applies to both versions.
**1.12.2 only** or **1.20.1/1.21.1/1.21.11 only** marks a change made in just that version.
The 1.12.2 version is a port of the 1.20.1/1.21.1/1.21.11 version and has its lights and features, so most lines apply to both.

## Added

### Versions and loaders

- **1.20.1/1.21.1/1.21.11 only:** Fabric 1.20.1 and 1.21.1 (since alpha.1), NeoForge 1.21.1 (since beta.3), Forge 1.20.1 (since beta.5), and Minecraft 1.21.11 for Fabric and NeoForge (since beta.8)
- **1.12.2 only:** Forge 1.12.2 (since beta.6); it requires OMLib, and OMLib's wrench configures and dismantles lights

### Lights

- Electric floodlight: straight, narrow cone and wide cone beam, battery slot, dye colour
- Non-electric (carbon) floodlight burning furnace fuel; cone modes use up fuel twice as fast as straight light, and the GUI shows the time left in the current mode
- UV floodlight: a beam of UV light that damages living entities
- Small and square fluorescent lights (the small one can be turned with a stick or wrench)
- Grow light: grows the crop two blocks below it, with normal lighting or black light
- Cube light: a full block that lights all 6 neighbouring blocks, takes energy from every side and shares it with touching cube lights; crafted from glass, a light bulb and iron, enabled together with the fluorescent lights
- Fluorescent and grow lights that sit directly next to each other and face the same way share their energy: cables fill the whole group, and a light that runs low takes energy from its neighbours
- Lightproof glass: see-through glass that lets no light through and stops floodlight beams (placeholder texture), crafted from black stained glass and coal; connected textures with an OptiFine-compatible CTM mod (on 1.20.1/1.21.1/1.21.11 e.g. Continuity)
- Disguise for the electric, carbon and UV floodlights: the light looks like a full, opaque block, with only its lamp showing on the front; the disguise stays on the dropped light
- The disguise is set in a camouflage menu, opened with the Camouflage button in the light's GUI: the same screen as for the turret bases of Open Modular Turrets (OMLib's camouflage menu on 1.12.2)
- **1.12.2 only:** disguises from 1.0.0-beta.6, which had a slot in the GUI, are kept

### Items, GUI and config

- Crafting items: raw and glowing filament, light bulb, fuel dissolver, mantle, non-electric lantern, light debug tool
- Recipes for the crafting items and the lights; recipes of blocks disabled in the config are not loaded
- Light debug tool: while held, light blocks are shown as wireframes (yellow phantom lights, magenta UV lights)
- A "?" in the electric and carbon floodlight GUIs explains the delay before a light can turn back on; toggling invert on a light that is still in that delay tells you in chat how many seconds until it turns on
- Config file `config/openmodularlighting.json` with the 1.7.10 settings, documented in the file and synced from the server on join
- **1.20.1/1.21.1/1.21.11 only:** the config file has a version: config files from older versions get the new default energy use and grow chance, unless the value was changed by hand

### Energy and mod compatibility

- **1.12.2 only:** Forge Energy and item pipes
- **1.12.2 only:** Hwyla shows invert and mode of a light (switchable in Hwyla's config)
- **1.20.1/1.21.1/1.21.11 only:** Team Reborn Energy on Fabric, the loader's energy capability (FE) and item handlers on NeoForge and Forge
- **1.20.1/1.21.1/1.21.11 only:** Jade shows invert and mode of a light (optional, Jade is not required)

## Changed

Compared with the 1.7.10 _FloodLights_ mod:

- Floodlights keep their light blocks while off and only switch them, instead of placing and removing them
- Floodlight beams use fewer phantom lights: the straight beam skips every second block (starting with the second); cones thin out too: the centre line like the straight beam, the rest of the cone offset by one from it
- Lights re-check their beam every 20 seconds on average (random), so it follows world changes that sent no block update
- Cube and fluorescent lights turn back on at once, without the 2-second timeout after turning off

### Compared with earlier betas

- The jar files are named `openmodularlighting-<version>-mc<minecraft version>-<loader>.jar` (`-mc` instead of the `+` before the Minecraft version), as in the other OpenModularTurretsTeam mods
- **1.20.1/1.21.1/1.21.11 only:** releases on CurseForge and Modrinth are titled like the jar file
- **1.20.1/1.21.1/1.21.11 only:** the mod bundles the new library OMLib (jar-in-jar), which holds the code it shares with Open Modular Turrets; nothing to install separately
- `uvLightRendered` is now each player's own setting: on a server, the client's config decides whether UV light blocks are visible
- The floodlight GUIs have a dark grey background like the turret GUIs instead of the vanilla light grey

## Fixed

- Light bulbs can be crafted when only the grow light is enabled
- Players in adventure mode can no longer dismantle lights with a wrench
- Fuels with a huge burn time (modded) no longer get stuck in the carbon floodlight's slot
- **1.20.1/1.21.1/1.21.11 only:** no crash when rendering a disguised floodlight on Fabric without a renderer implementation (e.g. Sodium without Indium on 1.20.1)
- No stray black line below the left corner of the floodlight GUIs
- **1.12.2 only:** light blocks are only saved when their light sources changed
- **1.20.1/1.21.1/1.21.11 only:** dedicated servers with Jade no longer fail to load the floodlight tooltip plugin (an error in the log; on Minecraft 1.21.11 the server crashed)
- **1.20.1/1.21.1/1.21.11 only:** on Forge 1.20.1, recipes that take iron, gold, redstone or glass panes can be crafted (their common tags were empty on Forge)

## Release history

| Version | 1.12.2 | 1.20.1/1.21.1/1.21.11 |
| --- | --- | --- |
| 1.0.0-alpha.1 | | 2026-10-16 |
| 1.0.0-beta.1 | | 2026-10-17 |
| 1.0.0-beta.2 | | 2026-10-17 |
| 1.0.0-beta.3 | | 2026-10-19 |
| 1.0.0-beta.4 | | 2026-10-21 |
| 1.0.0-beta.5 | | 2026-10-24 |
| 1.0.0-beta.6 | 2026-10-24 | |
| 1.0.0-beta.7 | 2026-10-26 | |
| 1.0.0-beta.8 | 2026-10-27 | 2026-10-26 |
| 1.0.0-beta.9 | | 2026-10-27 |
| 1.0.0-beta.10 | | 2026-10-27 |

The changelogs of the single releases are in the mod's repository:
[OpenModularLighting 1.20.1/1.21.1/1.21.11](https://github.com/OpenModularTurretsTeam/OpenModularLighting/blob/1.20.1%2B/CHANGELOG.md),
[OpenModularLighting 1.12.2](https://github.com/OpenModularTurretsTeam/OpenModularLighting/blob/1.12/CHANGELOG.md).
