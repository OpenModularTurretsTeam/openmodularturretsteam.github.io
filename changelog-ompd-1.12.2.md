---
layout: page
title: OMPD 4.0.0 on 1.12.2
permalink: /changelog/ompd/1.12.2/
---

This is the full changelog of **Open Modular Passive Defense (OMPD) 4.0.0 for Minecraft 1.12.2** (Forge): hardened blocks, walls, fences and the camouflage trap, merged from all of its alpha and beta releases.
It requires OMLib; on 1.20.1, 1.21.1 and 1.21.11 its blocks are part of [Open Modular Turrets](/changelog/omt/1.20.1-1.21.1-1.21.11/).

The latest pre-release is **4.0.0-beta.6** (2026-10-29), which requires OMLib 4.0.0-beta.6 or newer.

Other changelogs: [OMT on 1.12.2](/changelog/omt/1.12.2/), [OMT on 1.20.1/1.21.1/1.21.11](/changelog/omt/1.20.1-1.21.1-1.21.11/), [OMLib on 1.12.2](/changelog/omlib/1.12.2/), [OMLib on 1.20.1/1.21.1/1.21.11](/changelog/omlib/1.20.1-1.21.1-1.21.11/), [Open Modular Lighting 1.0.0](/changelog/oml-1.0.0/).

## Added

### Camouflage, trust and memory card

- Camouflage traps have a trusted player list: the owner and trusted players can stand on the trap, its admins open its menus and manage the list (Trusted button in the camouflage menu; levels "trusted" and "admin")

### Mod compatibility

- The One Probe shows the owner of hardened blocks, walls and fences, and Hwyla shows the owner too (green for unowned blocks) and shows a camouflage trap as its disguise to players who may not manage it
- Recipe for the camouflage trap (with Open Modular Turrets installed): 4 tier 1 hardened blocks, 4 planks and a tier 1 sensor give 4 traps

### Config

- Hardness and explosion resistance of the hardened blocks, walls and fences and the fence damage are configurable per tier (`hardness`, `explosionResistance`, `fenceDamage` in the `tiers` section)

## Changed

### Camouflage and passive defense

- Hardened blocks can be used as camouflage (other blocks with a tile/block entity still cannot)
- The camouflage trap blocks light like a solid block by default
- Fences spare only their owner (and shared owners); trusted players, team members and pets are hurt

## Fixed

- Fences dealt the same damage on every tier; it now grows from 5 (tier 1) to 9 (tier 5)
- Crash on hardened blocks, walls, fences and camo traps with invalid metadata (damaged chunks, /give)
- Hardened blocks, walls, fences and camo traps placed by something other than a player (e.g. a deployer) crashed the game
- Sneak-right-clicking your own block with an empty hand did not always pick it up
- The creative tab showed its translation key instead of its name
- The camouflage trap broke instantly; it mines like its disguise now
- WAILA/HWYLA showed no owner name for hardened blocks, walls and fences

## Release history

| Version | Released |
| --- | --- |
| 4.0.0-alpha.1 | 2026-10-23 |
| 4.0.0-alpha.2 | 2026-10-23 |
| 4.0.0-beta.1 | 2026-10-24 |
| 4.0.0-beta.2 | 2026-10-26 |
| 4.0.0-beta.3 | 2026-10-26 |
| 4.0.0-beta.4 | 2026-10-27 |
| 4.0.0-beta.5 | 2026-10-27 |
| 4.0.0-beta.6 | 2026-10-29 |

The changelogs of the single releases are in the mod's repository: [OpenModularPassiveDefense 1.12.2](https://github.com/OpenModularTurretsTeam/OpenModularPassiveDefense/blob/1.12/CHANGELOG.md).
