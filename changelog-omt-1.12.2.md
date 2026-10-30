---
layout: page
title: OMT 4.0.0 on 1.12.2
permalink: /changelog/omt/1.12.2/
---

This is the full changelog of **Open Modular Turrets 4.0.0 for Minecraft 1.12.2** (Forge), merged from all of its alpha and beta releases.
**OMLib** and **Open Modular Passive Defense (OMPD)** are mods of their own on 1.12.2 and have their own changelogs; the changes that are theirs are listed there.

The latest pre-release is **4.0.0-beta.6** (2026-10-29), which requires OMLib 4.0.0-beta.6 or newer.

Other changelogs: [OMT on 1.20.1/1.21.1/1.21.11](/changelog/omt/1.20.1-1.21.1-1.21.11/), [OMLib on 1.12.2](/changelog/omlib/1.12.2/), [OMLib on 1.20.1/1.21.1/1.21.11](/changelog/omlib/1.20.1-1.21.1-1.21.11/), [OMPD on 1.12.2](/changelog/ompd/1.12.2/), [Open Modular Lighting 1.0.0](/changelog/oml-1.0.0/).

## Before you update

- OMT and OMPD 4.0.0-beta.6 require OMLib 4.0.0-beta.6 or newer
- The 3.x inventory and power expanders, the loot deleter addon and _OMLib_'s network cable disappear from your world, the expanders together with the items in them (new inventory expanders come with 4.0.0-beta.5, see Added); placed 3.x power generators become generators and keep their fuel
- The Relativistic Turret becomes the Slowing Turret; placed turrets, items and its config section are converted

## Added

### Turrets

- The Melee Turret has a model: its blades extend and spin while it is active
- Holding a turret while looking at a block next to a turret base outlines where it would go: cyan if it can be placed there, red with a short reason if not (block in the way, wrong side, base tier too low, base full, too many of this turret)
- Turret tooltips (with shift): what the turret does, the base tier it needs, its ammo and its energy per shot
- Turrets that ignore Scatter Shot upgrades say so in their tooltip without shift, and the Scatter Shot tooltip names them
- Crafting recipes for the Melee, Crossbow, Arc and Plasma Turrets
- The Arc Turret takes a gold ingot instead of a lightning rod
- The Potato Cannon Turret can also fire poisonous potatoes

### Turret bases, energy and upgrades

- Generator: burns furnace fuel into energy for adjacent turret bases, with 9 fuel slots and an upgrade slot for the new Energy Multiplier Upgrade (up to 4, each doubles energy production and fuel use; the energy per fuel item stays the same)
- Upgrade tooltips show which machine the upgrade fits into (turret base or generator)
- The crank plays its windup sound when it charges a base
- Inventory expanders (tiers 1–3): placed against a turret base or generator, each lets every ammo or fuel slot hold 1, 2 or 3 more stacks (`expanders` config section); counts from four digits on are drawn smaller, and the tooltip shows count and limit
- Two plates of a tier fit into one block space, up to 2 per face
- The tooltip of a turret base shows the max stack size of its ammo slots, and the base GUI the current one (with inventory expanders)
- "Sort Ammo" button in the turret base GUI: merges equal ammo and sorts Minecraft items first, then Open Modular Turrets ammo, then other mods' ammo

### Ownership

- While you hold the Ownership Wand, turrets still target and fire at you, but their shots, explosions and effects do not affect you
- The owner of a turret base ("Disown" in its configure screen) or camouflage trap (camouflage menu) can disown it after a confirmation; the trust list is cleared and anyone can claim it
- Turret bases, their turrets and hardened blocks/walls/fences without an owner sparkle green
- WAILA/HWYLA and The One Probe show "Owner: nobody (right-click to claim)"

### Camouflage, trust and memory card

- The camouflage menu of a turret base is under Configure → Camouflage; admins of a camouflage trap open its menu by right-clicking it (sneaking skips it)
- Memory card: sneak + right-click a turret base or camouflage trap to store its settings, right-click another one to write them; it stores targeting, mode, trust list, disguise and light (traps: trust list, disguise and light), needs admin access for both, and its tooltip lists what it holds
- The memory card is now called OM Memory Card; 3.x cards still work, and sneak-clicking anything else clears it

### Mod compatibility

- Hwyla and The One Probe show a turret's inaccuracy (higher is less accurate), damage boost, rate of fire and ammo ("Unlimited" without ammo use), only to players who may open the base; a camouflaged base shows its disguise to everyone else; The One Probe no longer shows a turret's base damage

### Config

- Config option `turrets.dropTurretsOverMaxSimultaneous` (default false): attached turrets over their type's `maxSimultaneous` drop, e.g. after the limit was lowered
- The server sends its config values (OMT's `openmodularturrets.cfg` and `openmodularturrets_addon_turrets.cfg`, _OMLib_'s `omlib.cfg`) to clients when they join, so tooltips, ammo slots, the turret placement outline and GUIs follow the server's rules; after leaving, the client uses its own config again
- The disposable ammo list accepts `ore:oreName[,damage]` entries (e.g. `ore:cobblestone`, `ore:plankWood`) for every item of an ore dictionary entry; the default list allows the planks of every mod (`ore:plankWood`), and configs still listing `minecraft:planks,1` are updated

## Changed

### Targeting and aiming

- Turrets no longer target entities they would have to aim into their own base for (more than 45° below the mounting side), and no longer see through their own base
- Projectile turrets lead moving targets using the real flight time (air drag) and drop of their projectiles, so slow projectiles no longer hit below the target
- Projectiles scatter by a fifth of the turret's inaccuracy instead of a twentieth, since the better aiming made turrets far too accurate
- Turret bases pick the targets of their turrets and drop a target as soon as it is no longer valid (out of range or sight, trusted, settings changed)
- Targeting priorities are added up instead of multiplied and use the real distance, so turrets prefer the targets their priorities describe
- The mob block list config is honoured, and an entity on both force lists is ignored on both (with an error in the log)
- Only blocks with a collision box block the view of turrets
- Turrets aim relative to the side of the base they sit on, the same way on server and client, and turn smoothly
- Pets of players in the owner's scoreboard team are no longer targeted, and team members no longer get turret warnings
- Pets are protected by the trust list of their owner also while the owner is offline
- Turret hits no longer knock their targets back

### Turrets

- The Relativistic Turret is now the Slowing Turret
- The Rail Gun Turret ignores Scatter Shot upgrades (no extra rays, ammo, energy or scatter); with them it dealt a multiple of its damage, since it barely scatters and every ray hit
- The Melee, Slowing and Teleporter Turrets no longer use more energy with Scatter Shot upgrades; they act once per shot
- The Melee Turret strikes everything it may hurt in a 3x2x3 area around itself and its base, without waiting for the base to pick a target
- The Melee Turret only fits on top of or below a turret base
- Melee turrets on the sides of a base drop as items
- The Arc Turret can be placed on every side of a base, not only on top
- The particles of the Teleporter Turret are shown in multiplayer too
- Grenade and rocket explosions only break blocks with `canGrenadesDestroyBlocks` / `canRocketsDestroyBlocks`, and their blast deals turret damage (kill counting, loot rules)
- The arc turret's lightning is light blue
- The Crossbow Turret fires the new Crossbow Bolt ammo (16 from an iron ingot, a stick and a feather) instead of vanilla arrows
- The grenade flies for 29 ticks instead of 2 seconds and explodes 4 ticks after hitting a valid enemy

### Turret bases, addons and energy

- Mobs killed by turrets only drop loot if the base has a fake drops addon; each further addon adds one level of Looting
- Only admins of a turret base can attach turrets to it (the placement outline says why otherwise)
- Hoppers and pipes can no longer take ammo out of a turret base, so nobody can disarm someone else's base with them
- Turret bases without an owner (e.g. placed by a machine or a structure) no longer drop themselves; they stay inert until claimed, unless `bases.unownedBasesActive` is set
- Turrets can be attached to a turret base without an owner only by players who may use command blocks (operators in creative mode, mapmakers)
- A broken turret base scatters its items like a chest
- The Recycler addon saves ammo with the configured chance (it saved about 1 % of shots whatever the config said)
- The Solar Panel addon charges a base once per tick instead of once per tick for every turret on it
- Turret bases no longer give their energy to other blocks
- The generator GUI labels are black like in the other turret GUIs (they were dark grey on the dark background)
- New generator textures: every side has its own texture, and the tubes on the sides of a running generator are animated
- Turret bases store more energy by default: 5,000 / 500,000 / 1,500,000 / 10,000,000 / 100,000,000 for tiers 1–5; config files that still have the old defaults get the new ones
- Tier 4 and 5 turret bases hold 2 stacks in each ammo slot, which also doubles what inventory expanders add (`baseAmmoStacks` per tier)

### Camouflage and passive defense

- Admins of a turret base can set and remove its camouflage, not only its owner
- The camouflage menu has a dark grey background like the turret base GUI instead of the vanilla light grey

### Other

- The info panel of the turret base GUI sits at a fixed place left of the GUI and shows "none" as the owner of an unowned base; the configure screen is laid out as on 1.20.1/1.21.1/1.21.11 (the Camouflage button lower, without its "Camouflage:" label)
- The Fake Drops addon tooltip is worded as on 1.20.1/1.21.1/1.21.11, the generator tooltip shows its description only while Shift is held, the Disposable Item Turret tooltip names its ammo as "Cobblestone, planks and more (see config)", and the memory card tooltip shows section headings, target mode and the trusted players with their access levels
- `baseFireRate` has no maximum any more and `turretWarningDistance` cannot be negative; the base energy capacity, energy input and turret count settings apply without a restart
- The bullet recipe has the shape it has on 1.20.1/1.21.1/1.21.11, and the Ownership Wand is in the Open Modular Turrets creative tab
- License: the source code is now MIT (was GPLv3) and the art CC BY-NC-SA 4.0
- `turretBreakable` makes turrets mineable with a pickaxe (hardness 3, needs a restart), and breakable turrets need a pickaxe to drop
- The jar files are named `openmodularturrets-<version>-mc1.12.2-forge.jar` (Minecraft version with `mc`)

## Removed

- The 3.x inventory and power expanders: they disappear from worlds, together with the items in them; power expanders stay removed, and the inventory expanders come back as new ones (see Added); the 3.x expanders were not ported to 1.20.1, 1.21.1 and 1.21.11
- The loot deleter base addon (turret kills drop nothing without a fake drops addon now); placed loot deleters disappear
- The power generator attachment (it had no function); the Generator replaces it
- The config options `doTurretsKillsDropMobLoot` and `doLootAddonsOverrideMobLootSetting`
- Vanilla arrows are no longer turret ammo (arrows already in a base stay in its slots but are not used), and tipped arrows no longer give the crossbow turret's shots potion effects

## Fixed

- The `turretBreakable` config option did nothing; turrets can now be broken with a pickaxe when it is enabled
- Cranks and generators did not turn with rotated or mirrored structures
- The Melee, Relativistic and Teleporter Turrets crashed the game when they were saved (3.2.0 alpha)
- Player kills of a base are counted and saved (they were loaded into the kill counter and never saved)
- The neutral force list config was read into the mob block list
- Turrets on auto fire took the ammo of a shot twice
- Forced shots of Laser, Arc and Railgun Turrets crashed the game without a target and ignored missing energy
- The Grenade Turret was only available while the Laser Turret was enabled in the config
- The Crossbow Turret's config section had the name of the Potato Cannon Turret's; it is "Crossbow Turret" now
- Rays of Laser, Railgun and Arc Turrets could hit entities next to the ray
- The Plasma Turret tooltip showed tier 3, although the turret needs a tier 5 base
- Disposable ammo projectiles were invisible
- Disposable ammo list entries with a damage bonus (`minecraft:cobblestone,2`, the defaults) were not parsed, so no item was valid disposable ammo
- Unbreakable turret bases (`baseBreakable=false`) were destroyed by explosions
- The tier 3 turret base tooltip showed a raw translation key instead of "Energy"
- Memory cards stacked; they stack to 1 now
- The functionless Throwable Bullet, Throwable Grenade and fake disposable ammo items are no longer in the creative tab
- Tipped arrows were accepted as ammo but never fired
- The Redstone Reactor addon counted fuel it could not take out of a slot, and had no tooltip; the Recycler addon tooltip had an extra blank line
- Turrets with a fake drops addon knocked their targets back towards the world origin and could not hurt players on servers with PvP turned off
- Melee turret hits did not reset the hurt cooldown or mark the victim for the loot rules
- The disposable turret with ammo disabled fired an invisible projectile without cobblestone's damage bonus, and showed the whole drawn stack instead of one item
- Everyone nearby heard the turret alarm instead of only the warned player
- Arrows fired by crossbow turrets could show up as plasma on clients (two projectiles shared a network id), and crossbow turret shots crashed the client when they were rendered
- The slowing and railgun turrets' ambient dust has its intended light grey and blue colours
- Breaking or hitting a turret showed missing-texture particles; they come from the turret's texture now
- The Melee and Crossbow Turrets had no name (and the Arc Turret none in German, Portuguese, Russian and Chinese)
- The configure GUI no longer draws its buttons below its background
- The info panel of the turret base GUI no longer covers the GUI when its lines are long (e.g. long player names)
- ComputerCraft: `getTrustedPlayer` added the queried player to the trust list when they were not on it
- ComputerCraft: `setTurretAutoForceFire` and `forceShootTurret` rejected every valid side
- ComputerCraft: number arguments (access levels, modes, sides) were rejected because Lua numbers arrive as decimals; missing arguments now answer "Wrong parameters!"
- WAILA/HWYLA crashed the server on a turret whose base was not loaded
- Turrets added by other mods could not fire slower than every 20 ticks (their config clamped `baseFireRate` to 20)
- Decimal settings of turrets added by other mods (damage amp, upgrades, recycler chances, accuracy deviation) were not limited to their range
- The config ranges of `baseFireRate` (now from 1 tick, no maximum) and `baseAccuracyDeviation` (0–100 %) did not include the turrets' default values
- Computers (ComputerCraft, OpenComputers) could not change access levels: `changeAccessLevel` / `changeTrustedPlayerAccess` and `addTrustedPlayer` with a level reported success but changed nothing
- OpenComputers: `setTurretYawPitch` rejected valid angles and used the side as yaw, `forceShootTurret` did not check the side, side 6 counted as the bottom, `addTrustedPlayer` without an access level failed, `getTrustedPlayer` returned nothing for unknown players
- Turret base GUI actions (range, mode, targeting, dropping) were handled for unloaded or far-away bases, which could load chunks; they now need the base loaded and the player within reach
- Other mods asking a turret without base (or with its base in an unloaded chunk) for its stats crashed; such a turret now reports its configured values and targets nothing
- The maximum range shown in the turret base GUI also counted turrets mounted on a neighbouring base
- Turret bases, _OMLib_'s camouflaged blocks and _OMPD_'s camo traps could create their tile entity on the chunk render thread, which can crash or corrupt the world
- A turret base placed without saved data (e.g. by `/setblock` or a structure) with turrets already attached no longer starts with range 0; it starts at the range of its shortest reaching turret
- Boxes in the turret logic compared `0.0` and `-0.0` as equal while hashing them differently
- Tooltips and the turret placement outline used the client's own config instead of the server's

## For mod and addon developers

- Turret API: other mods can add turrets with their own weapons, ammo and models, and custom logic: self-targeting weapons find their own targets, projectile and ray weapons can run code when they hit an entity, and `OMTApi.canDamage` / `OMTApi.hurt` apply the base's trust and damage rules; plugins are marked with `@OMTPlugin.Register` / `@OMTClientPlugin.Register`. See `docs/turret-api.md` in the mod's repository
- Added turrets get their config in `config/openmodularturrets_addon_turrets.cfg`
- Removed the base controller API (`IBaseController`, `ILaserController`) of the discontinued OMTControl addon
- Removed the entity and ammo lists of the 3.x API (`api.lists`); they no longer affected targeting (the config lists and the disposable ammo allow list stay)

## Coming in the next pre-release

These changes are done but not released yet.

### Added

- Config sections `upgrades` and `addons` switch each upgrade and addon off: it loses its recipe and does nothing in a machine, which shows it with a red slot frame, a "no" symbol over the icon and a red tooltip line

### Changed

- The potentia converter addon is no longer in the creative tab and JEI: it does nothing and has no recipe

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

The changelogs of the single releases are in the mod's repository: [OpenModularTurrets 1.12.2](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/blob/1.12/CHANGELOG.md).
