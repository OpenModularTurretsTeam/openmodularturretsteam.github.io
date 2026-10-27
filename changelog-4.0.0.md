---
layout: page
title: OMT Changelog 4.0.0
permalink: /changelog/4.0.0/
---

This is the full changelog of **Open Modular Turrets 4.0.0**, merged from all of its alpha and beta releases.
For 1.12.2 it also covers **OMLib** and **Open Modular Passive Defense (OMPD)** 4.0.0, which are part of Open Modular Turrets on 1.20.1, 1.21.1 and 1.21.11.

The current pre-releases are:

| Minecraft | Loaders | Mods | Latest |
| --- | --- | --- | --- |
| 1.12.2 | Forge | OMT, OMLib, OMPD | 4.0.0-beta.5 (2026-10-27) |
| 1.20.1, 1.21.1 and 1.21.11 | Fabric 1.20.1, 1.21.1 and 1.21.11, NeoForge 1.21.1 and 1.21.11, Forge 1.20.1 | OMT (OMPD included, OMLib bundled) | 4.0.0-beta.11 (2026-10-27) |

**How to read this page:**
a line without a prefix is a change in both versions.
**1.12.2 only** or **1.20.1/1.21.1/1.21.11 only** marks a change made in just that version.
That does not always mean the other version lacks the feature: the 1.20.1/1.21.1/1.21.11 version is a port of 1.12.2, and some of its lines only catch up with 1.12.2.
On 1.12.2, _OMLib_ or _OMPD_ after the prefix names the mod that changed; the other lines are OMT.

## Before you update

- **1.12.2 only:** OMT and OMPD 4.0.0-beta.5 require OMLib 4.0.0-beta.5 or newer
- **1.12.2 only:** the 3.x inventory and power expanders, the loot deleter addon and _OMLib_'s network cable disappear from your world, the expanders together with the items in them (new inventory expanders come with 4.0.0-beta.5, see Added); placed 3.x power generators become generators and keep their fuel
- **1.12.2 only:** the Relativistic Turret becomes the Slowing Turret; placed turrets, items and its config section are converted
- **1.20.1/1.21.1/1.21.11 only:** Relativistic Turrets placed with 4.0.0-alpha.1 to 4.0.0-beta.2 disappear (renamed to Slowing Turret in beta.3); resource packs replacing its sound need the new name `openmodularturrets:slowing`

## Added

### Versions and loaders

- **1.20.1/1.21.1/1.21.11 only:** Open Modular Turrets for Fabric 1.20.1 and 1.21.1 (since alpha.1), NeoForge 1.21.1 and Forge 1.20.1 (since beta.6), and Minecraft 1.21.11 for Fabric and NeoForge (since beta.10), with all turrets, projectiles, ammo, upgrades and addons from Open Modular Turrets 3.2 (1.12.2) and turret bases (tiers 1–5) with GUI, trusted players and access levels
- **1.20.1/1.21.1/1.21.11 only:** Open Modular Passive Defense's hardened blocks, walls, fences and the camouflage trap are part of the mod; OMLib is bundled in the mod (since beta.10), so there is nothing to install separately
- **1.20.1/1.21.1/1.21.11 only:** energy via Team Reborn Energy on Fabric and the loader's energy capability on NeoForge and Forge

### Turrets

- The Melee Turret has a model: its blades extend and spin while it is active
- Holding a turret while looking at a block next to a turret base outlines where it would go: cyan if it can be placed there, red with a short reason if not (block in the way, wrong side, base tier too low, base full, too many of this turret)
- Turret tooltips (with shift): what the turret does, the base tier it needs, its ammo and its energy per shot
- **1.12.2 only:** turrets that ignore Scatter Shot upgrades say so in their tooltip without shift
- **1.20.1/1.21.1/1.21.11 only:** crafting recipes for the Melee, Crossbow, Arc and Plasma Turrets
- **1.20.1/1.21.1/1.21.11 only:** the Potato Cannon Turret can also fire poisonous potatoes

### Turret bases, energy and upgrades

- Generator: burns furnace fuel into energy for adjacent turret bases, with 9 fuel slots and an upgrade slot for the new Energy Multiplier Upgrade (up to 4, each doubles energy production and fuel use; the energy per fuel item stays the same)
- **1.20.1/1.21.1/1.21.11 only:** the Generator stores 1,000,000 RF, puts out up to 65,536 RF/t and also powers other energy acceptors; config files still on the old defaults (50,000 RF, 200 RF/t) are updated
- **1.20.1/1.21.1/1.21.11 only:** upgrade tooltips show which machine the upgrade fits into (turret base or generator)
- **1.20.1/1.21.1/1.21.11 only:** Creative Upgrade: fills the base's energy storage and removes the ammo usage of its turrets (placeholder texture)
- **1.20.1/1.21.1/1.21.11 only:** the crank plays its windup sound when it charges a tier 1 base
- Inventory expanders (tiers 1–3): placed against a turret base or generator, each lets every ammo or fuel slot hold 1, 2 or 3 more stacks (`expanders` config section); counts from four digits on are drawn smaller, and the tooltip shows count and limit
- **1.12.2 only:** two plates of a tier fit into one block space, up to 2 per face
- **1.20.1/1.21.1/1.21.11 only:** one expander block per face, which holds two of one tier like slabs; expanders have no inventory of their own
- The tooltip of a turret base shows the max stack size of its ammo slots, and the base GUI the current one (with inventory expanders)
- **1.20.1/1.21.1/1.21.11 only:** "Sort Ammo" button in the turret base GUI: merges equal ammo and sorts Minecraft items first, then Open Modular Turrets ammo, each by internal name

### Ownership

- Right-clicking a turret base, turret, camouflage trap or hardened block/wall/fence without an owner claims it and the unowned blocks connected to it (up to `claimSpreadLimit`, default 1024); machines' fake players only claim if `fakePlayersCanClaim` is set. On 1.12.2 these options are in _OMLib_'s config, on 1.20.1/1.21.1/1.21.11 they are `bases.claimSpreadLimit` and `general.fakePlayersCanClaim`
- Ownership Wand (creative, operators only) for mapmakers: right-click makes you the owner of an owned block, sneak-right-click removes its owner; it spreads to the connected blocks of the same owner unless switched off with a sneak-right-click into the air (on 1.12.2 part of _OMLib_)
- While you hold the Ownership Wand, turrets still target and fire at you, but their shots, explosions and effects do not affect you
- The owner of a turret base ("Disown" in its configure screen) or camouflage trap (camouflage menu) can disown it after a confirmation; the trust list is cleared and anyone can claim it
- Turret bases, their turrets and hardened blocks/walls/fences without an owner sparkle green
- **1.12.2 only:** WAILA/HWYLA and The One Probe show "Owner: nobody (right-click to claim)"
- **1.20.1/1.21.1/1.21.11 only:** Jade shows "Owner: nobody (right-click to claim)"; hardened blocks, walls and fences now show their owner in Jade

### Camouflage, trust and memory card

- Camouflage menu for turret bases and camouflage traps: a disguise slot (click with a block to set it, empty-handed to reset) and, on tier 4 and 5 bases and the camouflage trap, light value and light opacity sliders
- **1.12.2 only:** the camouflage menu of a turret base is under Configure → Camouflage; admins of a camouflage trap open its menu by right-clicking it (sneaking skips it)
- Turret bases and camouflage traps can be camouflaged as any full block, opaque or transparent (glass, ice, leaves)
- **1.12.2 only:** the config option `allowTransparentDisguises` turns transparent disguises off (turret bases in OMT, the camouflage trap in OMPD's `camo trap` section)
- **1.20.1/1.21.1/1.21.11 only:** the camouflage of the camouflage trap is drawn like a real block (ambient occlusion, transparent blocks, biome-blended grass and leaf colours)
- **1.12.2 only** · _OMLib_: the Trusted button of the camouflage trap menu reads "Trusted" and fits its label
- Camouflage traps have a trusted player list: the owner and trusted players can stand on the trap, its admins open its menus and manage the list (Trusted button in the camouflage menu; levels "trusted" and "admin")
- Memory card: sneak + right-click a turret base or camouflage trap to store its settings, right-click another one to write them; it stores targeting, mode, trust list, disguise and light (traps: trust list, disguise and light), needs admin access for both, and its tooltip lists what it holds
- **1.12.2 only:** the memory card is now called OM Memory Card; 3.x cards still work, and sneak-clicking anything else clears it
- **1.20.1/1.21.1/1.21.11 only:** the Turret Memory Card is craftable

### Mod compatibility

- **1.20.1/1.21.1/1.21.11 only:** Jade tooltips for turret bases (mode, active, owner) and turrets (active, owner and, for players who may open the base: ammo, damage boost, accuracy, rate of fire)
- **1.20.1/1.21.1/1.21.11 only:** Sable contraptions (1.21.1): turret bases and turrets on a contraption find, aim at and shoot targets in the world around it; projectiles take the contraption's speed with them
- **1.20.1/1.21.1/1.21.11 only:** Create contraptions and Create Aeronautics' Physics Assembler (NeoForge 1.21.1) can move turret bases and turrets; config option `bases.allowContraptionMovement` (default true)

### Config

- Config option `turrets.dropTurretsOverMaxSimultaneous` (default false): attached turrets over their type's `maxSimultaneous` drop, e.g. after the limit was lowered
- **1.12.2 only:** the server sends its config values (OMT's `openmodularturrets.cfg` and `openmodularturrets_addon_turrets.cfg`, _OMLib_'s `omlib.cfg`) to clients when they join, so tooltips, ammo slots, the turret placement outline and GUIs follow the server's rules; after leaving, the client uses its own config again
- **1.20.1/1.21.1/1.21.11 only:** the config file is documented: every key has a comment with its description, range and default
- **1.12.2 only:** the disposable ammo list accepts `ore:oreName[,damage]` entries (e.g. `ore:cobblestone`, `ore:plankWood`) for every item of an ore dictionary entry
- Hardness and explosion resistance of the hardened blocks, walls and fences and the fence damage are configurable per tier (`hardness`, `explosionResistance`, `fenceDamage`; in the `tiers` section on 1.12.2 and the `passiveDefense` section on 1.20.1/1.21.1/1.21.11, where no restart is needed)

## Changed

### Targeting and aiming

- Turrets no longer target entities they would have to aim into their own base for (more than 45° below the mounting side), and no longer see through their own base
- Projectile turrets lead moving targets using the real flight time (air drag) and drop of their projectiles, so slow projectiles no longer hit below the target
- Projectiles scatter by a fifth of the turret's inaccuracy instead of a twentieth, since the better aiming made turrets far too accurate
- **1.12.2 only:** turret bases pick the targets of their turrets and drop a target as soon as it is no longer valid (out of range or sight, trusted, settings changed)
- **1.12.2 only:** targeting priorities are added up instead of multiplied and use the real distance, so turrets prefer the targets their priorities describe
- **1.12.2 only:** the mob block list config is honoured, and the neutral force list wins over the mob force list
- **1.12.2 only:** only blocks with a collision box block the view of turrets
- **1.12.2 only:** turrets aim relative to the side of the base they sit on, the same way on server and client, and turn smoothly
- **1.12.2 only:** pets of players in the owner's scoreboard team are no longer targeted, and team members no longer get turret warnings
- **1.12.2 only:** pets are protected by the trust list of their owner also while the owner is offline
- **1.12.2 only** · _OMLib_: members of the owner's scoreboard team count as trusted (lowest access level) for owned blocks
- **1.20.1/1.21.1/1.21.11 only:** projectile turrets aim at the target's eyes instead of its body when a ledge hides the body
- **1.20.1/1.21.1/1.21.11 only:** turret hits no longer knock their targets back

### Turrets

- The Relativistic Turret is now the Slowing Turret
- The Rail Gun Turret ignores Scatter Shot upgrades (no extra rays, ammo, energy or scatter); with them it dealt a multiple of its damage, since it barely scatters and every ray hit
- The Melee, Slowing and Teleporter Turrets no longer use more energy with Scatter Shot upgrades; they act once per shot
- The Melee Turret strikes everything it may hurt in a 3x2x3 area around itself and its base, without waiting for the base to pick a target
- The Melee Turret only fits on top of or below a turret base
- **1.12.2 only:** melee turrets on the sides of a base drop as items
- **1.12.2 only:** the Arc Turret can be placed on every side of a base, not only on top
- **1.12.2 only:** the particles of the Teleporter Turret are shown in multiplayer too
- **1.20.1/1.21.1/1.21.11 only:** the Arc Turret chains a bit farther and bounces up to two times
- **1.20.1/1.21.1/1.21.11 only:** the Crossbow Turret fires the new Crossbow Bolt ammo (iron ingot, stick, feather) instead of vanilla arrows (placeholder texture)
- **1.20.1/1.21.1/1.21.11 only:** the grenade flies for 1.5 seconds instead of 2 and explodes 4 ticks after hitting a valid enemy

### Turret bases, addons and energy

- Mobs killed by turrets only drop loot if the base has a fake drops addon; each further addon adds one level of Looting
- Only admins of a turret base can attach turrets to it (the placement outline says why otherwise)
- Hoppers and pipes can no longer take ammo out of a turret base, so nobody can disarm someone else's base with them
- Turret bases without an owner (e.g. placed by a machine or a structure) no longer drop themselves; they stay inert until claimed, unless `bases.unownedBasesActive` is set
- Turrets can be attached to a turret base without an owner only by players who may use command blocks (operators, mapmakers; on 1.12.2 operators in creative mode)
- **1.12.2 only:** a broken turret base scatters its items like a chest
- **1.12.2 only:** the Recycler addon saves ammo with the configured chance (it saved about 1 % of shots whatever the config said)
- **1.12.2 only:** the Solar Panel addon charges a base once per tick instead of once per tick for every turret on it
- **1.12.2 only:** turret bases no longer give their energy to other blocks
- The generator GUI labels are black like in the other turret GUIs (they were dark grey on the dark background)
- **1.12.2 only** · _OMLib_: stored energy above a lowered capacity is cut off
- **1.12.2 only** · _OMLib_: owned blocks without an owner no longer count as owned by a placeholder player; they stay unowned until someone claims them
- Turret bases store more energy by default: 5,000 / 500,000 / 1,500,000 / 10,000,000 / 100,000,000 for tiers 1–5 (`baseMaxCharge` on 1.20.1+); config files that still have the old defaults get the new ones
- Tier 4 and 5 turret bases hold 2 stacks in each ammo slot, which also doubles what inventory expanders add (`baseAmmoStacks` per tier)

### Camouflage and passive defense

- Right-clicking a turret base or camouflage trap with a block no longer camouflages it; the camouflage menu does it now
- Hardened blocks can be used as camouflage (other blocks with a tile/block entity still cannot)
- Admins of a turret base can set and remove its camouflage, not only its owner
- The camouflage menu has a dark grey background like the turret base GUI instead of the vanilla light grey
- **1.12.2 only** · _OMPD_: the camouflage trap blocks light like a solid block by default
- **1.12.2 only** · _OMPD_: fences no longer hurt the owner's team and their pets

### Other

- **1.20.1/1.21.1/1.21.11 only:** the mod bundles the new library OMLib (jar-in-jar), which holds the code it shares with Open Modular Lighting; nothing to install separately
- License: the source code is now MIT (was GPLv3) and the art CC BY-NC-SA 4.0
- **1.12.2 only:** `turretBreakable` makes turrets mineable with a pickaxe (hardness 3, needs a restart)
- The jar files are named `<mod>-<version>-mc<minecraft version>-<loader>.jar` (`openmodularturrets`; on 1.12.2 also `omlib` and `ompd`)
- **1.20.1/1.21.1/1.21.11 only:** releases on CurseForge and Modrinth are titled like the jar file
- **1.20.1/1.21.1/1.21.11 only:** German and English (UK) translations completed

## Removed

- **1.12.2 only:** the 3.x inventory and power expanders: they disappear from worlds, together with the items in them; power expanders stay removed, and the inventory expanders come back as new ones (see Added); the 3.x expanders were not ported to 1.20.1, 1.21.1 and 1.21.11
- **1.12.2 only:** the loot deleter base addon (turret kills drop nothing without a fake drops addon now); placed loot deleters disappear
- **1.12.2 only:** the power generator attachment (it had no function); the Generator replaces it
- **1.12.2 only:** the config options `doTurretsKillsDropMobLoot` and `doLootAddonsOverrideMobLootSetting`
- **1.12.2 only** · _OMLib_: global trust lists (they could not be turned on in game)
- **1.12.2 only** · _OMLib_: the unfinished network cable block (it crashed the client with missing model variants); placed cables disappear
- **1.12.2 only** · _OMLib_: the IC2 config options `EUSupport` and `EUtoRFRatio` (they had no effect since IC2 support was removed)

## Fixed

- The `turretBreakable` config option did nothing; turrets can now be broken with a pickaxe when it is enabled
- Cranks and generators did not turn with rotated or mirrored structures
- Fences dealt the same damage on every tier; it now grows from 5 (tier 1) to 9 (tier 5)
- **1.12.2 only:** the Melee, Relativistic and Teleporter Turrets crashed the game when they were saved (3.2.0 alpha)
- **1.12.2 only:** player kills of a base are counted and saved (they were loaded into the kill counter and never saved)
- **1.12.2 only:** the neutral force list config was read into the mob block list
- **1.12.2 only:** turrets on auto fire took the ammo of a shot twice
- **1.12.2 only:** forced shots of Laser, Arc and Railgun Turrets crashed the game without a target and ignored missing energy
- **1.12.2 only:** the Grenade Turret was only available while the Laser Turret was enabled in the config
- **1.12.2 only:** the Crossbow Turret's config section had the name of the Potato Cannon Turret's; it is "Crossbow Turret" now
- **1.12.2 only:** rays of Laser, Railgun and Arc Turrets could hit entities next to the ray
- **1.12.2 only:** the Plasma Turret tooltip showed tier 3, although the turret needs a tier 5 base
- **1.12.2 only:** disposable ammo projectiles were invisible
- **1.12.2 only:** disposable ammo list entries with a damage bonus (`minecraft:cobblestone,2`, the defaults) were not parsed, so no item was valid disposable ammo
- **1.12.2 only:** the Melee and Crossbow Turrets had no name (and the Arc Turret none in German, Portuguese, Russian and Chinese)
- **1.12.2 only:** the configure GUI no longer draws its buttons below its background
- **1.12.2 only:** the info panel of the turret base GUI no longer covers the GUI when its lines are long (e.g. long player names)
- **1.12.2 only:** ComputerCraft: `getTrustedPlayer` added the queried player to the trust list when they were not on it
- **1.12.2 only:** ComputerCraft: `setTurretAutoForceFire` and `forceShootTurret` rejected every valid side
- **1.12.2 only:** ComputerCraft: number arguments (access levels, modes, sides) were rejected because Lua numbers arrive as decimals; missing arguments now answer "Wrong parameters!"
- **1.12.2 only:** WAILA/HWYLA crashed the server on a turret whose base was not loaded, and showed the accuracy deviation instead of the accuracy
- **1.12.2 only:** turrets added by other mods could not fire slower than every 20 ticks (their config clamped `baseFireRate` to 20)
- **1.12.2 only:** decimal settings of turrets added by other mods (damage amp, upgrades, recycler chances, accuracy deviation) were not limited to their range
- **1.12.2 only:** the config ranges of `baseFireRate` (now 1–200 ticks) and `baseAccuracyDeviation` (0–100 %) did not include the turrets' default values
- **1.12.2 only:** computers (ComputerCraft, OpenComputers) could not change access levels: `changeAccessLevel` / `changeTrustedPlayerAccess` and `addTrustedPlayer` with a level reported success but changed nothing
- **1.12.2 only:** OpenComputers: `setTurretYawPitch` rejected valid angles and used the side as yaw, `forceShootTurret` did not check the side, side 6 counted as the bottom, `addTrustedPlayer` without an access level failed, `getTrustedPlayer` returned nothing for unknown players
- **1.12.2 only:** turret base GUI actions (range, mode, targeting, dropping) were handled for unloaded or far-away bases, which could load chunks; they now need the base loaded and the player within reach
- **1.12.2 only:** other mods asking a turret without base (or with its base in an unloaded chunk) for its stats crashed; such a turret now reports its configured values and targets nothing
- **1.12.2 only:** the maximum range shown in the turret base GUI also counted turrets mounted on a neighbouring base
- **1.12.2 only:** turret bases, _OMLib_'s camouflaged blocks and _OMPD_'s camo traps could create their tile entity on the chunk render thread, which can crash or corrupt the world
- A turret base placed without saved data (e.g. by `/setblock` or a structure) with turrets already attached no longer starts with range 0; it starts at the range of its shortest reaching turret
- **1.12.2 only:** boxes in the turret logic compared `0.0` and `-0.0` as equal while hashing them differently
- **1.12.2 only:** tooltips and the turret placement outline used the client's own config instead of the server's
- **1.12.2 only** · _OMLib_: machines answered other mods' Redstone Flux (RF) capability requests with nothing, and crashed with Redstone Flux installed but not Tesla
- **1.12.2 only** · _OMLib_: camouflaged blocks could render as grass while their tile entity was missing
- **1.12.2 only** · _OMLib_: the trusted players GUI crashed on the remove and permission buttons when no player was selected
- **1.12.2 only** · _OMLib_: the target settings GUI crashed when closed for machines without client sync
- **1.12.2 only** · _OMLib_: very old trust lists (saved as a plain list of names) are read again
- **1.12.2 only** · _OMLib_: camouflaged blocks with a see-through disguise such as leaves no longer make the neighbouring blocks look transparent
- **1.12.2 only** · _OMLib_: the disguise slot of the camouflage menu shows a new disguise at once instead of after reopening the menu
- **1.12.2 only** · _OMLib_: clients could make the server load or generate chunks anywhere by sending trust list, camouflage or GUI messages for far-away positions; these messages now need the block loaded and the player within reach
- **1.12.2 only** · _OMLib_: players without access to a block could receive its updates (trust list, settings) by sending its GUI-open message
- **1.12.2 only** · _OMLib_: loading a world kept the owner share lists (`/omlib share`) of the world opened before it in the same game
- **1.12.2 only** · _OMLib_: a renamed player (or, in offline mode, a player with another UUID) could be missed in lookups of players and trusted players
- **1.12.2 only** · _OMLib_: changes in OMLib's config GUI were only applied after a restart
- **1.12.2 only** · _OMLib_: the debug tool crashed a dedicated server when used on a turret base
- **1.12.2 only** · _OMLib_: items dropped from a broken machine lost data other mods keep on the item stack (capabilities)
- **1.12.2 only** · _OMPD_: crash on hardened blocks, walls, fences and camo traps with invalid metadata (damaged chunks, /give)
- **1.12.2 only** · _OMPD_: hardened blocks, walls, fences and camo traps placed by something other than a player (e.g. a deployer) crashed the game
- **1.12.2 only** · _OMPD_: sneak-right-clicking your own block with an empty hand did not always pick it up
- **1.12.2 only** · _OMPD_: the creative tab showed its translation key instead of its name
- **1.12.2 only** · _OMPD_: WAILA/HWYLA showed no owner name for hardened blocks, walls and fences
- **1.20.1/1.21.1/1.21.11 only:** shift-clicking addons and upgrades into a turret base no longer ignores their slot stack limit
- **1.20.1/1.21.1/1.21.11 only:** projectiles now properly apply on-hit effects on their motion, and grenades no longer hurl away when they hit entities
- **1.20.1/1.21.1/1.21.11 only:** Potato Cannon and Disposable Turret projectiles are visible right at the turret instead of a few blocks away, and show a potato or cobblestone when fired without ammo (Creative Upgrade)
- **1.20.1/1.21.1/1.21.11 only:** turret projectiles that flew into a chunk without entity ticking froze there; they remove themselves now, as in 1.12.2
- **1.20.1/1.21.1/1.21.11 only:** on the very first start (no config file yet), the disposable ammo list and the entity black and force lists were ignored until the next restart
- **1.20.1/1.21.1/1.21.11 only:** the Redstone Reactor addon burns a redstone block or dust when its energy fits the free storage exactly; before, it needed more room than that
- **1.20.1/1.21.1/1.21.11 only:** the English (UK) Turret Limit label was broken
- **1.20.1/1.21.1/1.21.11 only:** the mod metadata named the wrong license (GPL-3.0); the jar now contains all three license files
- **1.20.1/1.21.1/1.21.11 only:** turret bases and generators no longer drop a second copy of their items when they are moved or replaced without breaking (`/setblock`, mods that move blocks)
- **1.20.1/1.21.1/1.21.11 only:** turrets also turn with rotated or mirrored structures, and turrets, cranks and generators with moved blocks, so turrets and cranks stay attached to their base
- **1.20.1/1.21.1/1.21.11 only:** adding a trusted player by a name the server does not know no longer freezes the server while the name is looked up at Mojang
- **1.20.1/1.21.1/1.21.11 only:** "Drop turrets" only breaks blocks that are still turrets
- **1.20.1/1.21.1/1.21.11 only:** camouflaged turret bases and traps no longer crash the client on Fabric 1.20.1 when no Fabric Renderer API implementation is installed (Sodium without Indium); they show their own look then
- **1.20.1/1.21.1/1.21.11 only:** the base configure screen dims the world behind it like the base and camouflage GUIs (it was blurred before on 1.21 and later)
- **1.20.1/1.21.1/1.21.11 only:** the info panel left of the base GUI no longer disappears while a button tooltip is shown (Minecraft 1.21.11)
- **1.20.1/1.21.1/1.21.11 only:** the mouse stays where it was when you move between the base, configure, trusted players and camouflage GUIs instead of jumping to the screen centre
- **1.20.1/1.21.1/1.21.11 only:** the grenade turret's grenades properly fall down after hitting a target again
- **1.20.1/1.21.1/1.21.11 only:** dedicated servers with Jade no longer fail to load the turret tooltip plugin (an error in the log; on Minecraft 1.21.11 the server crashed)
- **1.20.1/1.21.1/1.21.11 only:** on Forge 1.20.1, recipes that take iron, gold, redstone, quartz, diamonds or glass panes can be crafted (their common tags were empty on Forge)

## For mod and addon developers

- Turret API: other mods can add turrets with their own weapons, ammo and models, and custom logic: self-targeting weapons find their own targets, projectile and ray weapons can run code when they hit an entity, and `OMTApi.canDamage` / `OMTApi.hurt` apply the base's trust and damage rules; plugins are marked with `@OMTPlugin.Register` / `@OMTClientPlugin.Register`. See `docs/turret-api.md` in the mod's repository
- **1.12.2 only:** added turrets get their config in `config/openmodularturrets_addon_turrets.cfg`
- **1.20.1/1.21.1/1.21.11 only:** added turrets get their config entries under `turrets.addon_turrets`; on Fabric, plugins use the `openmodularturrets` entrypoint instead of the annotations
- **1.12.2 only:** removed the base controller API (`IBaseController`, `ILaserController`) of the discontinued OMTControl addon
- **1.12.2 only:** removed the entity and ammo lists of the 3.x API (`api.lists`); they no longer affected targeting (the config lists and the disposable ammo allow list stay)
- **1.12.2 only** · _OMLib_: the client-only GUI and render helpers moved from `omtteam.omlib.api.gui` / `api.render` to `omtteam.omlib.client.gui` / `client.render` (`ColorOM`, `ICamoSupport` and `RenderBlockStateContainer` stay)
- **1.12.2 only** · _OMLib_: `ICamoSupport` has four new methods (`isCamoEnabled`, `supportsLight`, `canSetCamo`, `canChangeLight`), and `getOwnedBlock()` is now `getCamoTileEntity()`, returning any `TileEntity`, so camouflage hosts no longer need to be owned blocks
- **1.12.2 only** · _OMLib_: inventories whose slots hold more than one stack (`LargeStackHandler` / `LargeStackItemHandler`, with container slots, container and GUI): saved, synced and filled by hoppers and pipes up to the slot limit
- **1.20.1/1.21.1/1.21.11 only** · _OMLib_: containers whose slots hold more than one stack (`LargeStackContainer`, with menu slots, menu and screen): saved, synced and moved by hoppers and pipes on all loaders
- **1.12.2 only** · _OMLib_: camouflage hosts can accept transparent blocks (glass, ice, leaves) as a disguise (`ICamoSupport.acceptsTransparentDisguises`)
- **1.12.2 only** · _OMLib_: memory card rules (`core.card`: card data, who may copy and write, trust list copying) shared by turret bases and camouflage traps
- **1.12.2 only** · _OMLib_: tile entity base `tileentity.TileEntitySynced` (data hooks `readData` / `writeData`, separate client data `writeClientData`, `syncToClient`, `remesh`); `TileEntityBase` now builds on it and behaves as before
- **1.12.2 only** · _OMLib_: `container.WindowValues` syncs int values of a container to its GUI as window properties (two 16-bit halves each)
- **1.12.2 only** · _OMLib_: `util.inventory.InvUtil.dropItems` spills an inventory when its block breaks, `inventory.AutomationItemHandler` is the hopper/pipe view of a machine's slots
- **1.12.2 only** · _OMLib_: `WorldUtil.getTileEntity(IBlockAccess, BlockPos)` looks up a tile entity without creating it
- **1.12.2 only** · _OMLib_: `api.permission.IOwnedHost` (owner, claim, clear; implemented by `TileEntityOwnedBlock`), `handler.ClaimSpread`, `block.UnownedMarker` (green sparkle on unowned blocks), `api.block.IPlainLookingBlock` (blocks with a tile entity that may still be a disguise) and `IDrawOutline.canPlace` with the player
- **1.12.2 only** · _OMLib_: removed the tile entity base classes `TileEntityElectric`, `TileEntityContainerElectric`, `TileEntityMachine`, `TileEntityTrustedMachine` and `TileEntityContainer`; tile entities hold the helpers `power.EnergyCapabilities` and `tileentity.InventoryNbt` instead (same NBT keys)
- **1.12.2 only** · _OMLib_: removed the unused device network API (`api.network.OMLibNetwork`, `INetworkTile`, `IPowerExchangeTile`, `IController`, `INameController`) and helpers (`Tuple3`, `EntityUtil`, `ItemUtil`, `ItemStackList`, `PropertyTools`, `BlockingAbstractGui`)

## Release history

| Version | 1.12.2 (OMT, OMLib, OMPD) | 1.20.1/1.21.1/1.21.11 |
| --- | --- | --- |
| 4.0.0-alpha.1 | 2026-10-23 | 2026-10-12 |
| 4.0.0-alpha.2 | 2026-10-23 | 2026-10-13 |
| 4.0.0-alpha.3 | | 2026-10-13 |
| 4.0.0-alpha.4 | | 2026-10-13 |
| 4.0.0-beta.1 | 2026-10-24 | 2026-10-14 |
| 4.0.0-beta.2 | 2026-10-26 | 2026-10-15 |
| 4.0.0-beta.3 | 2026-10-26 | 2026-10-15 |
| 4.0.0-beta.4 | 2026-10-27 | 2026-10-17 |
| 4.0.0-beta.5 | 2026-10-27 | 2026-10-21 |
| 4.0.0-beta.6 | | 2026-10-24 |
| 4.0.0-beta.7 | | 2026-10-24 |
| 4.0.0-beta.8 | | 2026-10-25 |
| 4.0.0-beta.9 | | 2026-10-25 |
| 4.0.0-beta.10 | | 2026-10-27 |
| 4.0.0-beta.11 | | 2026-10-27 |

The changelogs of the single releases are in the mods' repositories:
[OpenModularTurrets 1.20.1/1.21.1/1.21.11](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/blob/1.20.1%2B/CHANGELOG.md),
[OpenModularTurrets 1.12.2](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/blob/1.12/CHANGELOG.md),
[OMLib 1.12.2](https://github.com/OpenModularTurretsTeam/OMLib/blob/1.12/CHANGELOG.md),
[OpenModularPassiveDefense 1.12.2](https://github.com/OpenModularTurretsTeam/OpenModularPassiveDefense/blob/1.12/CHANGELOG.md).
