---
layout: page
title: Roadmap
permalink: /roadmap/
---

Here is the state of our mods and the changes planned for them.

## __OpenModularTurrets__

### _v4.0.x_ (in beta, for _1.12.2_ and _1.20.1+_)

Released as betas: 4.0.0-beta.3 for 1.12.2 (Forge), 4.0.0-beta.9 for 1.20.1+ (Fabric 1.20.1 and 1.21.1, NeoForge 1.21.1, Forge 1.20.1).
See the [full 4.0.0 changelog](/changelog/4.0.0/).

- _Add_: 1.20.1 and 1.21.1 versions (Fabric, NeoForge 1.21.1, Forge 1.20.1), with OMPD's blocks included and without OMLib (**done**)
- _Add_: Generator with Energy Multiplier Upgrades (**done**)
- _Add_: camouflage menu with light settings for bases and camouflage traps (**done**)
- _Add_: memory card for copying base and trap settings (**done**)
- _Add_: trusted players for camouflage traps (**done**)
- _Add_: Turret API for other mods (**done**)
- _Add_: Melee, Crossbow, Arc and Plasma Turrets (**done**)
- _Add_: Jade, Sable and Create compatibility on 1.20.1+ (**done**)
- _Add_: claiming unowned blocks, disowning bases and an Ownership Wand for mapmakers (**done**)
- _Change_: new targeting and aiming system for turrets (**done**)
- _Change_: Relativistic Turret becomes the Slowing Turret (**done**)
- _Remove_: inventory and power expanders, loot deleter addon (**done**)

### Planned earlier, not part of 4.0.0

These were on the old 4.0 roadmap and did not make it into 4.0.0.

- multiblock bases, with turrets and addons that need a certain size or features of the base
- replacing the upgrade system with attachments/blocks for turret bases
- Repelling Turret (Tier 3) (Entity pushing utility turret)
- Tractor Turret (Tier 3) (Entity pulling utility turret)
- Particle Beam Turret (Tier 5) (Very high damage, very low firerate, large AOE offensive turret)
- Securicraft compatibility

### _v3.2.x_ (skipped, replaced by 4.0.x)

### _v3.1.x_ (released, for _1.12.2_)

- _Add_: Turrets honour team settings
- _Add_: base addon that removes loot from kills
- _Add_: Limits for how many turrets at one base
- _Add_: config option to always conceal turrets
- _Add_: light value and light opacity now configurable on tier 3+ bases
- _Add_: customize addons/upgrades per turret
- _Add_: Tier 5 base now has a built-in serial port
- _Change_: Laser rework (more realistic effects/behaviour)
- _Change_: Railgun rework (more realistic rendering/behaviour)
- _Change_: Some small GUI changes and fixes
- _Change_: new expander textures (by Austin5003)
- _Change_: New trusted player GUI (in OMLib)
- _Change_: camo now supports way more blocks
- _Change_: various bugfixes

## __OMLib__ (_1.12.2_ only)

On 1.20.1+, Open Modular Turrets does not need OMLib.

### _v4.0.x_ (in beta)

- _Add_: camouflage menu with disguise slot and light sliders (**done**)
- _Add_: memory card rules shared by turret bases and camouflage traps (**done**)
- _Add_: claiming unowned blocks and the Ownership Wand (**done**)
- _Change_: members of the owner's scoreboard team count as trusted (**done**)
- _Remove_: global trust lists, the unfinished network cable and the unused device network API (**done**)

### _v3.1.x_ (released)

- _Add_: Fluid support for machinery
- _Add_: Custom Effect rendering system
- _Add_: networking cables (for OMTC)
- _Add_: camo system extension
- _Add_: trusted player GUI

## __OpenModularPassiveDefense__

On 1.20.1+, its blocks are part of Open Modular Turrets.

### _v4.0.x_ (in beta, for _1.12.2_)

- _Add_: trusted players for camouflage traps (**done**)
- _Add_: light settings for camouflage traps (**done**)
- _Add_: claiming unowned blocks and disowning camouflage traps (**done**)
- _Change_: fences no longer hurt the owner's team and their pets (**done**)

### _v3.2.x_ (skipped, replaced by 4.0.x)

## __OpenModularLighting__

### _v1.0.x_ (in beta, for _1.12.2_ and _1.20.1+_)

Floodlights, a port of the 1.7.10 _FloodLights_ mod.
Released as betas: 1.0.0-beta.7 for 1.12.2 (Forge, needs OMLib 4.0.0-beta.2 or newer), 1.0.0-beta.8 for 1.20.1+ (Fabric 1.20.1, 1.21.1 and 1.21.11, NeoForge 1.21.1 and 1.21.11, Forge 1.20.1).
See the [full 1.0.0 changelog](/changelog/oml-1.0.0/).

#### Ported from the 1.7.10 _FloodLights_ mod

- _Add_: electric floodlight with straight, narrow cone and wide cone beams, redstone control with invert, dye colours and a battery slot (**done**)
- _Add_: carbon (non-electric) floodlight burning furnace fuel (**done**)
- _Add_: UV floodlight that damages living entities (**done**)
- _Add_: grow light, also with a black-light mode (**done**)
- _Add_: small and square fluorescent lights (**done**)
- _Add_: crafting chain for light bulbs, filaments, mantles and lanterns (**done**)
- _Add_: light debug tool (**done**)
- _Add_: configurable ranges, energy use, fuel time, grow chance, UV damage and a timeout before a light turns on again (**done**)

#### Added since

- _Add_: cube light, a full block that lights all 6 neighbouring blocks (**done**)
- _Add_: lightproof glass that stops light and floodlight beams (**done**)
- _Add_: disguise for the electric, carbon and UV floodlights, so they look like any full block (**done**; on 1.12.2 in OMLib's camouflage menu)
- _Add_: neighbouring fluorescent and grow lights and touching cube lights share their energy (**done**)
- _Add_: hints in the GUI and in chat for the delay before a light turns on again (**done**)
- _Add_: Fabric, NeoForge and Forge versions for 1.20.1 and 1.21.1, NeoForge and Fabric for 1.21.11, and Forge for 1.12.2 (**done**)
- _Add_: Jade (1.20.1+) and Hwyla (1.12.2) tooltips showing a light's mode and invert (**done**)
- _Add_: a documented JSON config that the server sends to the players, and that updates itself to new defaults (**done**)

#### Changed since

- _Change_: floodlights keep their light blocks while off and only switch them, use fewer of them and re-check the beam every 20 seconds (**done**)
- _Change_: lower default energy use: electric floodlight 10 E/t (20 in the cone modes, was 20 and 40), small fluorescent light 1 E/t (was 2), UV floodlight 60 E/t (was 80), grow light 25 E/t (was 40) (**done**)
- _Change_: the grow light gives a growth tick with 10 % chance per second (was 5 %) (**done**)
- _Change_: cube and fluorescent lights turn back on at once, without the 2-second timeout (**done**)
- _Change_: energy through Team Reborn Energy (Fabric) and Forge Energy instead of the 1.7.10 RF API (**done**)
- _Change_: the UV light blocks' visibility is each player's own setting (**done**; on 1.12.2 in the next pre-release)

## __OMTControl (OMT Addon)__

Discontinued. OMT 4.0.0 for 1.12.2 removed the base controller API it used.
