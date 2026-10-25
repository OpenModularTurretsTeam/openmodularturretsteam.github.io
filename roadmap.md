---
layout: page
title: Roadmap
permalink: /roadmap/
---

Here is the state of our mods and the changes planned for them.

## __OpenModularTurrets__

### _v4.0.x_ (in beta, for _1.12.2_ and _1.20.1+_)

Released as betas: 4.0.0-beta.1 for 1.12.2 (Forge), 4.0.0-beta.8 for 1.20.1+ (Fabric 1.20.1 and 1.21.1, NeoForge 1.21.1, Forge 1.20.1).
See the [full 4.0.0 changelog](/changelog/4.0.0/).

- _Add_: 1.20.1 and 1.21.1 versions (Fabric, NeoForge 1.21.1, Forge 1.20.1), with OMPD's blocks included and without OMLib (**done**)
- _Add_: Generator with Energy Multiplier Upgrades (**done**)
- _Add_: camouflage menu with light settings for bases and camouflage traps (**done**)
- _Add_: memory card for copying base and trap settings (**done**)
- _Add_: trusted players for camouflage traps (**done**)
- _Add_: Turret API for other mods (**done**)
- _Add_: Melee, Crossbow, Arc and Plasma Turrets (**done**)
- _Add_: Jade, Sable and Create compatibility on 1.20.1+ (**done**)
- _Add_: claiming unowned blocks and an Ownership Wand for mapmakers on 1.20.1+ (**done**, next pre-release)
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
- _Change_: fences no longer hurt the owner's team and their pets (**done**)

### _v3.2.x_ (skipped, replaced by 4.0.x)

### _v3.1.x_ (skipped, beta released)

## __OpenModularLighting__

### _v1.0.x_ (in beta, for _1.12.2_ and _1.20.1+_)

Floodlights, a port of the 1.7.10 _FloodLights_ mod, for Fabric 1.20.1 and 1.21.1, NeoForge 1.21.1, Forge 1.20.1 and Forge 1.12.2 (with OMLib).

## __OMTControl (OMT Addon)__

Discontinued. OMT 4.0.0 for 1.12.2 removed the base controller API it used.
