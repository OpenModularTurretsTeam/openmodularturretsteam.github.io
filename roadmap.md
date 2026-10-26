---
layout: page
title: Roadmap
permalink: /roadmap/
---

Here is the state of our mods and the changes planned for them.

## __OpenModularTurrets__

### _v4.2.x_ (planned)

The targets of 4.1.x and 4.2.x are the issues of the matching milestones in the [issue tracker](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues).
Which Minecraft versions get 4.1.x and 4.2.x is not decided yet.

- _Add_: multiblock bases and their blocks, which replace the upgrades ([#493](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/493)):
  - basic blocks without a function (maybe basic and advanced)
  - cooling block (air/fluid cooling) that replaces the fire rate upgrade, and vents as an attachment
  - power converter block that replaces the efficiency upgrade
  - targeting systems that replace the accuracy and range upgrades
  - ammo compressor block that replaces the scattershot upgrade
  - energy generating blocks, with a rework of the energy generation in bases
- _Change_: some turrets and addons need a certain size or features of their multiblock base
- _Add_: a way for mobs to fight turrets, by destroying or deactivating them; only hostile mobs would attack ([#531](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/531))
- _Change_: concealing a turret without the addon becomes a per-turret setting, e.g. with a GUI button or OMLib's wrench, instead of a global config option ([#458](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/458))

### _v4.1.x_ (planned)

A visual rework of the mod with a clear material and engineering progression, and some changes to addons and blocks.

- _Change_: turret models and textures follow the material progression wood → copper → brass → iron → steel, the swivel holders are remodelled to fit, and every turret gets visual indicators that make it easy to identify at night ([#586](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/586))
- _Change_: Gun Turret: less military, brass tier, new model ([#579](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/579))
- _Change_: Grenade Turret: new texture ([#580](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/580))
- _Change_: Slowing Turret (the former Relativistic Turret): new model and texture ([#581](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/581))
- _Change_: Rocket Launcher Turret: new model and texture ([#582](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/582))
- _Change_: Laser Turret: new model and textures, a crystal laser with a big cooling system ([#583](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/583))
- _Change_: Plasma Turret: fix the coil rendering, new model and texture ([#584](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/584))
- _Change_: Potato Cannon Turret: a hole in front of the barrel ([#585](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/585))
- _Change_: the Damage Amp addon is shown as a glowing wavy ring on top of the base plate of the turret ([#587](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/587), with a pull request open: [#591](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/591))
- _Add_: heat system ([#590](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/590)):
  - turrets produce heat, some none or only a little, some a lot
  - bases store heat and turrets cannot shoot while the storage is full
  - bases lose heat through every free side, and a cooling fan on one side dramatically increases that (the block two blocks from the base on that side must be air)
  - heat generation of turrets, storage and dissipation of bases and an on/off switch are in the config
- _Change_: the Solar addon becomes a block with a higher energy output ([#578](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/578))
- _Change_: more realistic turrets: a configurable range damage falloff (optimal range plus falloff) and tracking limits, so fast spinning railguns no longer make sense ([#539](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/539))
- _Change_: recipe rework: new intermediate items, the previous tier is removed from the recipes, the cost stays the same and the crafting needs fewer steps ([#595](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/595))
- _Add_: Repelling Turret (Tier 3) (Entity pushing utility turret) ([#324](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/324))
- _Add_: Tractor Turret (Tier 3) (Entity pulling utility turret) ([#324](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/324))
- _Add_: Energy Drain Turret (Tier 5) (Drains energy from the items of its targets) ([#324](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/324))
- To consider: Particle Beam Turret (Tier 5) (Very high damage, very low firerate, large AOE offensive turret) ([#324](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/324))

### _v4.0.x_ (in beta, for _1.12.2_, _1.20.1_ and _1.21.1_)

Released as betas: 4.0.0-beta.3 for 1.12.2 (Forge), 4.0.0-beta.9 for 1.20.1 and 1.21.1 (Fabric 1.20.1 and 1.21.1, NeoForge 1.21.1, Forge 1.20.1).
See the [full 4.0.0 changelog](/changelog/4.0.0/).

- _Add_: 1.20.1 and 1.21.1 versions (Fabric, NeoForge 1.21.1, Forge 1.20.1), with OMPD's blocks included and without OMLib (__done__)
- _Add_: Generator with Energy Multiplier Upgrades (__done__)
- _Add_: camouflage menu with light settings for bases and camouflage traps (__done__)
- _Add_: memory card for copying base and trap settings (__done__)
- _Add_: trusted players for camouflage traps (__done__)
- _Add_: Turret API for other mods (__done__)
- _Add_: Melee, Crossbow, Arc and Plasma Turrets (__done__)
- _Add_: Jade, Sable and Create compatibility on 1.20.1 and 1.21.1 (__done__)
- _Add_: claiming unowned blocks, disowning bases and an Ownership Wand for mapmakers (__done__)
- _Change_: new targeting and aiming system for turrets (__done__)
- _Change_: Relativistic Turret becomes the Slowing Turret (__done__)
- _Remove_: inventory and power expanders, loot deleter addon (__done__)
- _Change_: new texture for the Generator, the current one is a placeholder ([#588](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/issues/588))

### Not scheduled

- Securicraft compatibility

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

On 1.20.1 and 1.21.1, Open Modular Turrets does not need OMLib.

### _v4.0.x_ (in beta)

- _Add_: camouflage menu with disguise slot and light sliders (__done__)
- _Add_: memory card rules shared by turret bases and camouflage traps (__done__)
- _Add_: claiming unowned blocks and the Ownership Wand (__done__)
- _Change_: members of the owner's scoreboard team count as trusted (__done__)
- _Remove_: global trust lists, the unfinished network cable and the unused device network API (__done__)

### _v3.1.x_ (released)

- _Add_: Fluid support for machinery
- _Add_: Custom Effect rendering system
- _Add_: networking cables (for OMTC)
- _Add_: camo system extension
- _Add_: trusted player GUI

## __OpenModularPassiveDefense__

On 1.20.1 and 1.21.1, its blocks are part of Open Modular Turrets.

### _v4.0.x_ (in beta, for _1.12.2_)

- _Add_: trusted players for camouflage traps (__done__)
- _Add_: light settings for camouflage traps (__done__)
- _Add_: claiming unowned blocks and disowning camouflage traps (__done__)
- _Change_: fences no longer hurt the owner's team and their pets (__done__)

## __OpenModularLighting__

### _v1.0.x_ (in beta, for _1.12.2_, _1.20.1_, _1.21.1_ and _1.21.11_)

Floodlights, a port of the 1.7.10 _FloodLights_ mod.
Released as betas: 1.0.0-beta.7 for 1.12.2 (Forge, needs OMLib 4.0.0-beta.2 or newer), 1.0.0-beta.8 for 1.20.1, 1.21.1 and 1.21.11 (Fabric 1.20.1, 1.21.1 and 1.21.11, NeoForge 1.21.1 and 1.21.11, Forge 1.20.1).
See the [full 1.0.0 changelog](/changelog/oml-1.0.0/).

#### Ported from the 1.7.10 _FloodLights_ mod

- _Add_: electric floodlight with straight, narrow cone and wide cone beams, redstone control with invert, dye colours and a battery slot (__done__)
- _Add_: carbon (non-electric) floodlight burning furnace fuel (__done__)
- _Add_: UV floodlight that damages living entities (__done__)
- _Add_: grow light, also with a black-light mode (__done__)
- _Add_: small and square fluorescent lights (__done__)
- _Add_: crafting chain for light bulbs, filaments, mantles and lanterns (__done__)
- _Add_: light debug tool (__done__)
- _Add_: configurable ranges, energy use, fuel time, grow chance, UV damage and a timeout before a light turns on again (__done__)

#### Added since

- _Add_: cube light, a full block that lights all 6 neighbouring blocks (__done__)
- _Add_: lightproof glass that stops light and floodlight beams (__done__)
- _Add_: disguise for the electric, carbon and UV floodlights, so they look like any full block (__done__; on 1.12.2 in OMLib's camouflage menu)
- _Add_: neighbouring fluorescent and grow lights and touching cube lights share their energy (__done__)
- _Add_: hints in the GUI and in chat for the delay before a light turns on again (__done__)
- _Add_: Fabric, NeoForge and Forge versions for 1.20.1 and 1.21.1, and a Forge version for 1.12.2 (__done__)
- _Add_: port to Minecraft 1.21.11, for both Fabric and NeoForge (__done__)
- _Add_: Jade (1.20.1, 1.21.1 and 1.21.11) and Hwyla (1.12.2) tooltips showing a light's mode and invert (__done__)
- _Add_: a documented JSON config that the server sends to the players, and that updates itself to new defaults (__done__)

#### Changed since

- _Change_: floodlights keep their light blocks while off and only switch them, use fewer of them and re-check the beam every 20 seconds (__done__)
- _Change_: lower default energy use: electric floodlight 10 E/t (20 in the cone modes, was 20 and 40), small fluorescent light 1 E/t (was 2), UV floodlight 60 E/t (was 80), grow light 25 E/t (was 40) (__done__)
- _Change_: the grow light gives a growth tick with 10 % chance per second (was 5 %) (__done__)
- _Change_: cube and fluorescent lights turn back on at once, without the 2-second timeout (__done__)
- _Change_: energy through Team Reborn Energy (Fabric) and Forge Energy instead of the 1.7.10 RF API (__done__)
- _Change_: the UV light blocks' visibility is each player's own setting (__done__; on 1.12.2 in the next pre-release)

## __OMTControl (OMT Addon)__

Discontinued. OMT 4.0.0 for 1.12.2 removed the base controller API it used.
