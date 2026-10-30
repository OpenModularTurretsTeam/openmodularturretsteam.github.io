---
layout: page
title: OMT 4.0.0 on 1.20.1/1.21.1/1.21.11
permalink: /changelog/omt/1.20.1-1.21.1-1.21.11/
---

This is the full changelog of **Open Modular Turrets 4.0.0 for Minecraft 1.20.1, 1.21.1 and 1.21.11** (Fabric 1.20.1, 1.21.1 and 1.21.11, NeoForge 1.21.1 and 1.21.11, Forge 1.20.1), merged from all of its alpha and beta releases.
Open Modular Passive Defense's hardened blocks, walls, fences and the camouflage trap are part of the mod, and it bundles OMLib (since 4.0.0-beta.10), so there is nothing else to install.

The latest pre-release is **4.0.0-beta.11** (2026-10-27).

Other changelogs: [OMT on 1.12.2](/changelog/omt/1.12.2/), [OMLib on 1.12.2](/changelog/omlib/1.12.2/), [OMLib on 1.20.1/1.21.1/1.21.11](/changelog/omlib/1.20.1-1.21.1-1.21.11/), [OMPD on 1.12.2](/changelog/ompd/1.12.2/), [Open Modular Lighting 1.0.0](/changelog/oml-1.0.0/).

## Before you update

- Relativistic Turrets placed with 4.0.0-alpha.1 to 4.0.0-beta.2 disappear (renamed to Slowing Turret in beta.3); resource packs replacing its sound need the new name `openmodularturrets:slowing`

## Added

### Versions and loaders

- Open Modular Turrets for Fabric 1.20.1 and 1.21.1 (since alpha.1), NeoForge 1.21.1 and Forge 1.20.1 (since beta.6), and Minecraft 1.21.11 for Fabric and NeoForge (since beta.10), with all turrets, projectiles, ammo, upgrades and addons from Open Modular Turrets 3.2 (1.12.2) and turret bases (tiers 1–5) with GUI, trusted players and access levels
- Open Modular Passive Defense's hardened blocks, walls, fences and the camouflage trap are part of the mod; OMLib is bundled in the mod (since beta.10), so there is nothing to install separately
- Energy via Team Reborn Energy on Fabric and the loader's energy capability on NeoForge and Forge

### Turrets

- The Melee Turret has a model: its blades extend and spin while it is active
- Holding a turret while looking at a block next to a turret base outlines where it would go: cyan if it can be placed there, red with a short reason if not (block in the way, wrong side, base tier too low, base full, too many of this turret)
- Turret tooltips (with shift): what the turret does, the base tier it needs, its ammo and its energy per shot
- Crafting recipes for the Melee, Crossbow, Arc and Plasma Turrets
- The Potato Cannon Turret can also fire poisonous potatoes

### Turret bases, energy and upgrades

- Generator: burns furnace fuel into energy for adjacent turret bases, with 9 fuel slots and an upgrade slot for the new Energy Multiplier Upgrade (up to 4, each doubles energy production and fuel use; the energy per fuel item stays the same)
- The Generator stores 1,000,000 RF, puts out up to 65,536 RF/t and also powers other energy acceptors; config files still on the old defaults (50,000 RF, 200 RF/t) are updated
- Upgrade tooltips show which machine the upgrade fits into (turret base or generator)
- Creative Upgrade: fills the base's energy storage and removes the ammo usage of its turrets (placeholder texture)
- The crank plays its windup sound when it charges a base
- Inventory expanders (tiers 1–3): placed against a turret base or generator, each lets every ammo or fuel slot hold 1, 2 or 3 more stacks (`expanders` config section); counts from four digits on are drawn smaller, and the tooltip shows count and limit
- One expander block per face, which holds two of one tier like slabs; expanders have no inventory of their own
- The tooltip of a turret base shows the max stack size of its ammo slots, and the base GUI the current one (with inventory expanders)
- "Sort Ammo" button in the turret base GUI: merges equal ammo and sorts Minecraft items first, then Open Modular Turrets ammo, each by internal name

### Ownership

- Right-clicking a turret base, turret, camouflage trap or hardened block/wall/fence without an owner claims it and the unowned blocks connected to it (up to `bases.claimSpreadLimit`, default 1024); machines' fake players only claim if `general.fakePlayersCanClaim` is set
- Ownership Wand (creative, operators only) for mapmakers: right-click makes you the owner of an owned block, sneak-right-click removes its owner; it spreads to the connected blocks of the same owner unless switched off with a sneak-right-click into the air
- While you hold the Ownership Wand, turrets still target and fire at you, but their shots, explosions and effects do not affect you
- The owner of a turret base ("Disown" in its configure screen) or camouflage trap (camouflage menu) can disown it after a confirmation; the trust list is cleared and anyone can claim it
- Turret bases, their turrets and hardened blocks/walls/fences without an owner sparkle green
- Jade shows "Owner: nobody (right-click to claim)"; hardened blocks, walls and fences now show their owner in Jade

### Camouflage, trust and memory card

- Camouflage menu for turret bases and camouflage traps: a disguise slot (click with a block to set it, empty-handed to reset) and, on tier 4 and 5 bases and the camouflage trap, light value and light opacity sliders
- Turret bases and camouflage traps can be camouflaged as any full block, opaque or transparent (glass, ice, leaves)
- The camouflage of the camouflage trap is drawn like a real block (ambient occlusion, transparent blocks, biome-blended grass and leaf colours)
- Camouflage traps have a trusted player list: the owner and trusted players can stand on the trap, its admins open its menus and manage the list (Trusted button in the camouflage menu; levels "trusted" and "admin")
- Memory card: sneak + right-click a turret base or camouflage trap to store its settings, right-click another one to write them; it stores targeting, mode, trust list, disguise and light (traps: trust list, disguise and light), needs admin access for both, and its tooltip lists what it holds
- The Turret Memory Card is craftable

### Mod compatibility

- Jade tooltips for turret bases (mode, active, owner) and turrets (active, owner and, for players who may open the base: ammo, damage boost, accuracy, rate of fire)
- Sable contraptions (1.21.1): turret bases and turrets on a contraption find, aim at and shoot targets in the world around it; projectiles take the contraption's speed with them
- Create contraptions and Create Aeronautics' Physics Assembler (NeoForge 1.21.1) can move turret bases and turrets; config option `bases.allowContraptionMovement` (default true)

### Config

- Config option `turrets.dropTurretsOverMaxSimultaneous` (default false): attached turrets over their type's `maxSimultaneous` drop, e.g. after the limit was lowered
- The config file is documented: every key has a comment with its description, range and default
- Hardness and explosion resistance of the hardened blocks, walls and fences and the fence damage are configurable per tier (`hardness`, `explosionResistance`, `fenceDamage` in the `passiveDefense` section; no restart needed)

## Changed

### Targeting and aiming

- Turrets no longer target entities they would have to aim into their own base for (more than 45° below the mounting side), and no longer see through their own base
- Projectile turrets lead moving targets using the real flight time (air drag) and drop of their projectiles, so slow projectiles no longer hit below the target
- Projectiles scatter by a fifth of the turret's inaccuracy instead of a twentieth, since the better aiming made turrets far too accurate
- Projectile turrets aim at the target's eyes instead of its body when a ledge hides the body
- Turret hits no longer knock their targets back

### Turrets

- The Relativistic Turret is now the Slowing Turret
- The Rail Gun Turret ignores Scatter Shot upgrades (no extra rays, ammo, energy or scatter); with them it dealt a multiple of its damage, since it barely scatters and every ray hit
- The Melee, Slowing and Teleporter Turrets no longer use more energy with Scatter Shot upgrades; they act once per shot
- The Melee Turret strikes everything it may hurt in a 3x2x3 area around itself and its base, without waiting for the base to pick a target
- The Melee Turret only fits on top of or below a turret base
- The Arc Turret chains a bit farther and bounces up to two times
- The Crossbow Turret fires the new Crossbow Bolt ammo (16 from an iron ingot, a stick and a feather) instead of vanilla arrows
- The Crossbow Bolt has a placeholder texture
- The grenade flies for about 1.5 seconds instead of 2 and explodes 4 ticks after hitting a valid enemy

### Turret bases, addons and energy

- Mobs killed by turrets only drop loot if the base has a fake drops addon; each further addon adds one level of Looting
- Only admins of a turret base can attach turrets to it (the placement outline says why otherwise)
- Hoppers and pipes can no longer take ammo out of a turret base, so nobody can disarm someone else's base with them
- Turret bases without an owner (e.g. placed by a machine or a structure) no longer drop themselves; they stay inert until claimed, unless `bases.unownedBasesActive` is set
- Turrets can be attached to a turret base without an owner only by players who may use command blocks (operators, mapmakers)
- The generator GUI labels are black like in the other turret GUIs (they were dark grey on the dark background)
- Turret bases store more energy by default: 5,000 / 500,000 / 1,500,000 / 10,000,000 / 100,000,000 for tiers 1–5 (`baseMaxCharge`); config files that still have the old defaults get the new ones
- Tier 4 and 5 turret bases hold 2 stacks in each ammo slot, which also doubles what inventory expanders add (`baseAmmoStacks` per tier)

### Camouflage and passive defense

- Right-clicking a turret base or camouflage trap with a block no longer camouflages it; the camouflage menu does it now
- Hardened blocks can be used as camouflage (other blocks with a tile/block entity still cannot)
- Admins of a turret base can set and remove its camouflage, not only its owner
- The camouflage menu has a dark grey background like the turret base GUI instead of the vanilla light grey

### Other

- The mod bundles the new library OMLib (jar-in-jar), which holds the code it shares with Open Modular Lighting; nothing to install separately
- License: the source code is now MIT (was GPLv3) and the art CC BY-NC-SA 4.0
- The jar files are named `openmodularturrets-<version>-mc<minecraft version>-<loader>.jar` (`-mc` instead of the `+` before the Minecraft version)
- Releases on CurseForge and Modrinth are titled like the jar file
- German and English (UK) translations completed

## Fixed

- The `turretBreakable` config option did nothing; turrets can now be broken with a pickaxe when it is enabled
- Cranks and generators did not turn with rotated or mirrored structures
- Fences dealt the same damage on every tier; it now grows from 5 (tier 1) to 9 (tier 5)
- A turret base placed without saved data (e.g. by `/setblock` or a structure) with turrets already attached no longer starts with range 0; it starts at the range of its shortest reaching turret
- Shift-clicking addons and upgrades into a turret base no longer ignores their slot stack limit
- Projectiles now properly apply on-hit effects on their motion, and grenades no longer hurl away when they hit entities
- Potato Cannon and Disposable Turret projectiles are visible right at the turret instead of a few blocks away, and show a potato or cobblestone when fired without ammo (Creative Upgrade)
- Turret projectiles that flew into a chunk without entity ticking froze there; they remove themselves now
- On the very first start (no config file yet), the disposable ammo list and the entity black and force lists were ignored until the next restart
- The Redstone Reactor addon burns a redstone block or dust when its energy fits the free storage exactly; before, it needed more room than that
- The English (UK) Turret Limit label was broken
- The mod metadata named the wrong license (GPL-3.0); the jar now contains all three license files
- Turret bases and generators no longer drop a second copy of their items when they are moved or replaced without breaking (`/setblock`, mods that move blocks)
- Turrets also turn with rotated or mirrored structures, and turrets, cranks and generators with moved blocks, so turrets and cranks stay attached to their base
- Adding a trusted player by a name the server does not know no longer freezes the server while the name is looked up at Mojang
- "Drop turrets" only breaks blocks that are still turrets
- Camouflaged turret bases and traps no longer crash the client on Fabric 1.20.1 when no Fabric Renderer API implementation is installed (Sodium without Indium); they show their own look then
- The base configure screen dims the world behind it like the base and camouflage GUIs (it was blurred before on 1.21 and later)
- The info panel left of the base GUI no longer disappears while a button tooltip is shown (Minecraft 1.21.11)
- The mouse stays where it was when you move between the base, configure, trusted players and camouflage GUIs instead of jumping to the screen centre
- The grenade turret's grenades properly fall down after hitting a target again
- Dedicated servers with Jade no longer fail to load the turret tooltip plugin (an error in the log; on Minecraft 1.21.11 the server crashed)
- On Forge 1.20.1, recipes that take iron, gold, redstone, quartz, diamonds or glass panes can be crafted (their common tags were empty on Forge)

## For mod and addon developers

- Turret API: other mods can add turrets with their own weapons, ammo and models, and custom logic: self-targeting weapons find their own targets, projectile and ray weapons can run code when they hit an entity, and `OMTApi.canDamage` / `OMTApi.hurt` apply the base's trust and damage rules; plugins are marked with `@OMTPlugin.Register` / `@OMTClientPlugin.Register`. See `docs/turret-api.md` in the mod's repository
- Added turrets get their config entries under `turrets.addon_turrets`; on Fabric, plugins use the `openmodularturrets` entrypoint instead of the annotations

## Coming in the next pre-release

These changes are done but not released yet.

### Added

- Config sections `upgrades` and `addons` switch each upgrade and addon off: it loses its recipe and does nothing in a machine, which shows it with a red slot frame, a "no" symbol over the icon and a red tooltip line
- The slowing and railgun turrets show ambient dust particles again (light grey; blue while the railgun is deployed)
- Turret API: `TurretDefinition.builder(...).ambientEffect(...)` adds client particles to a placed turret

### Changed

- New generator textures: every side has its own texture, and the tubes on the sides of a running generator are animated

### Fixed

- The Jade tooltip of a turret showed its inaccuracy labelled as "Accuracy"; it is labelled "Inaccuracy" now
- The memory card tooltip showed raw translation keys instead of the access levels of the trusted players

## Release history

| Version | Released |
| --- | --- |
| 4.0.0-alpha.1 | 2026-10-12 |
| 4.0.0-alpha.2 | 2026-10-13 |
| 4.0.0-alpha.3 | 2026-10-13 |
| 4.0.0-alpha.4 | 2026-10-13 |
| 4.0.0-beta.1 | 2026-10-14 |
| 4.0.0-beta.2 | 2026-10-15 |
| 4.0.0-beta.3 | 2026-10-15 |
| 4.0.0-beta.4 | 2026-10-17 |
| 4.0.0-beta.5 | 2026-10-21 |
| 4.0.0-beta.6 | 2026-10-24 |
| 4.0.0-beta.7 | 2026-10-24 |
| 4.0.0-beta.8 | 2026-10-25 |
| 4.0.0-beta.9 | 2026-10-25 |
| 4.0.0-beta.10 | 2026-10-27 |
| 4.0.0-beta.11 | 2026-10-27 |

The changelogs of the single releases are in the mod's repository: [OpenModularTurrets 1.20.1/1.21.1/1.21.11](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/blob/1.20.1%2B/CHANGELOG.md).
