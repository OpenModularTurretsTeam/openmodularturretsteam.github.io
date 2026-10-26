---
layout: page
title: OMT Changelog 4.0.0
permalink: /changelog/4.0.0/
---

This is the full changelog of __Open Modular Turrets 4.0.0__, merged from all of its alpha and beta releases.
For 1.12.2 it also covers __OMLib__ and __Open Modular Passive Defense (OMPD)__ 4.0.0, which are part of Open Modular Turrets on 1.20.1 and 1.21.1.

The current pre-releases are:

| Minecraft | Loaders | Mods | Latest |
| --- | --- | --- | --- |
| 1.12.2 | Forge | OMT, OMLib, OMPD | 4.0.0-beta.3 (2026-10-26) |
| 1.20.1 and 1.21.1 | Fabric 1.20.1 and 1.21.1, NeoForge 1.21.1, Forge 1.20.1 | OMT (OMPD and OMLib included) | 4.0.0-beta.9 (2026-10-25) |

__How to read this page:__
a line without a prefix is a change in both versions.
__1.12.2 only__ or __1.20.1/1.21.1 only__ marks a change made in just that version.
That does not always mean the other version lacks the feature: the 1.20.1/1.21.1 version is a port of 1.12.2, and some of its lines only catch up with 1.12.2.
On 1.12.2, _OMLib_ or _OMPD_ after the prefix names the mod that changed; the other lines are OMT.

## Before you update

- __1.12.2 only:__ OMT and OMPD 4.0.0-beta.3 require OMLib 4.0.0-beta.3 or newer
- __1.12.2 only:__ inventory and power expanders, the loot deleter addon and _OMLib_'s network cable disappear from your world, the expanders together with the items in them; placed 3.x power generators become generators and keep their fuel
- __1.12.2 only:__ the Relativistic Turret becomes the Slowing Turret; placed turrets, items and its config section are converted
- __1.20.1/1.21.1 only:__ Relativistic Turrets placed with 4.0.0-alpha.1 to 4.0.0-beta.2 disappear (renamed to Slowing Turret in beta.3); resource packs replacing its sound need the new name `openmodularturrets:slowing`

## Added

### Versions and loaders

- __1.20.1/1.21.1 only:__ Open Modular Turrets for Fabric 1.20.1 and 1.21.1 (since alpha.1), NeoForge 1.21.1 and Forge 1.20.1 (since beta.6), with all turrets, projectiles, ammo, upgrades and addons from Open Modular Turrets 3.2 (1.12.2) and turret bases (tiers 1–5) with GUI, trusted players and access levels
- __1.20.1/1.21.1 only:__ Open Modular Passive Defense's hardened blocks, walls, fences and the camouflage trap are part of the mod; OMLib is not needed
- __1.20.1/1.21.1 only:__ energy via Team Reborn Energy on Fabric and the loader's energy capability on NeoForge and Forge

### Turrets

- The Melee Turret has a model: its blades extend and spin while it is active
- Holding a turret while looking at a block next to a turret base outlines where it would go: cyan if it can be placed there, red with a short reason if not (block in the way, wrong side, base tier too low, base full, too many of this turret)
- Turret tooltips (with shift): what the turret does, the base tier it needs, its ammo and its energy per shot
- __1.12.2 only:__ turrets that ignore Scatter Shot upgrades say so in their tooltip without shift
- __1.20.1/1.21.1 only:__ crafting recipes for the Melee, Crossbow, Arc and Plasma Turrets
- __1.20.1/1.21.1 only:__ the Potato Cannon Turret can also fire poisonous potatoes

### Turret bases, energy and upgrades

- Generator: burns furnace fuel into energy for adjacent turret bases, with 9 fuel slots and an upgrade slot for the new Energy Multiplier Upgrade (up to 4, each doubles energy production and fuel use; the energy per fuel item stays the same)
- __1.20.1/1.21.1 only:__ the Generator stores 1,000,000 RF, puts out up to 65,536 RF/t and also powers other energy acceptors; config files still on the old defaults (50,000 RF, 200 RF/t) are updated
- __1.20.1/1.21.1 only:__ upgrade tooltips show which machine the upgrade fits into (turret base or generator)
- __1.20.1/1.21.1 only:__ Creative Upgrade: fills the base's energy storage and removes the ammo usage of its turrets (placeholder texture)
- __1.20.1/1.21.1 only:__ the crank plays its windup sound when it charges a tier 1 base

### Ownership

- Right-clicking a turret base, turret, camouflage trap or hardened block/wall/fence without an owner claims it and the unowned blocks connected to it (up to `claimSpreadLimit`, default 1024); machines' fake players only claim if `fakePlayersCanClaim` is set. On 1.12.2 these options are in _OMLib_'s config, on 1.20.1/1.21.1 they are `bases.claimSpreadLimit` and `general.fakePlayersCanClaim`
- Ownership Wand (creative, operators only) for mapmakers: right-click makes you the owner of an owned block, sneak-right-click removes its owner; it spreads to the connected blocks of the same owner unless switched off with a sneak-right-click into the air (on 1.12.2 part of _OMLib_)
- While you hold the Ownership Wand, turrets still target and fire at you, but their shots, explosions and effects do not affect you
- The owner of a turret base ("Disown" in its configure screen) or camouflage trap (camouflage menu) can disown it after a confirmation; the trust list is cleared and anyone can claim it
- Turret bases, their turrets and hardened blocks/walls/fences without an owner sparkle green
- __1.12.2 only:__ WAILA/HWYLA and The One Probe show "Owner: nobody (right-click to claim)"
- __1.20.1/1.21.1 only:__ Jade shows "Owner: nobody (right-click to claim)"; hardened blocks, walls and fences now show their owner in Jade

### Camouflage, trust and memory card

- Camouflage menu for turret bases and camouflage traps: a disguise slot (click with a block to set it, empty-handed to reset) and, on tier 4 and 5 bases and the camouflage trap, light value and light opacity sliders
- __1.12.2 only:__ the camouflage menu of a turret base is under Configure → Camouflage; admins of a camouflage trap open its menu by right-clicking it (sneaking skips it)
- __1.20.1/1.21.1 only:__ turret bases and camouflage traps can be camouflaged as any full block, opaque or transparent; the camouflage of the camouflage trap is drawn like a real block (ambient occlusion, transparent blocks, biome-blended grass and leaf colours)
- Camouflage traps have a trusted player list: the owner and trusted players can stand on the trap, its admins open its menus and manage the list (Trusted button in the camouflage menu; levels "trusted" and "admin")
- Memory card: sneak + right-click a turret base or camouflage trap to store its settings, right-click another one to write them; it stores targeting, mode, trust list, disguise and light (traps: trust list, disguise and light), needs admin access for both, and its tooltip lists what it holds
- __1.12.2 only:__ the memory card is now called OM Memory Card; 3.x cards still work, and sneak-clicking anything else clears it
- __1.20.1/1.21.1 only:__ the Turret Memory Card is craftable

### Mod compatibility

- __1.20.1/1.21.1 only:__ Jade tooltips for turret bases (mode, active, owner) and turrets (active, owner and, for players who may open the base: ammo, damage boost, accuracy, rate of fire)
- __1.20.1/1.21.1 only:__ Sable contraptions (1.21.1): turret bases and turrets on a contraption find, aim at and shoot targets in the world around it; projectiles take the contraption's speed with them
- __1.20.1/1.21.1 only:__ Create contraptions and Create Aeronautics' Physics Assembler (NeoForge 1.21.1) can move turret bases and turrets; config option `bases.allowContraptionMovement` (default true)

### Config

- Config option `turrets.dropTurretsOverMaxSimultaneous` (default false): attached turrets over their type's `maxSimultaneous` drop, e.g. after the limit was lowered
- __1.12.2 only:__ the server sends its config values (OMT's `openmodularturrets.cfg` and `openmodularturrets_addon_turrets.cfg`, _OMLib_'s `omlib.cfg`) to clients when they join, so tooltips, ammo slots, the turret placement outline and GUIs follow the server's rules; after leaving, the client uses its own config again
- __1.20.1/1.21.1 only:__ the config file is documented: every key has a comment with its description, range and default

## Changed

### Targeting and aiming

- Turrets no longer target entities they would have to aim into their own base for (more than 45° below the mounting side), and no longer see through their own base
- Projectile turrets lead moving targets using the real flight time (air drag) and drop of their projectiles, so slow projectiles no longer hit below the target
- Projectiles scatter by a fifth of the turret's inaccuracy instead of a twentieth, since the better aiming made turrets far too accurate
- __1.12.2 only:__ turret bases pick the targets of their turrets and drop a target as soon as it is no longer valid (out of range or sight, trusted, settings changed)
- __1.12.2 only:__ targeting priorities are added up instead of multiplied and use the real distance, so turrets prefer the targets their priorities describe
- __1.12.2 only:__ the mob block list config is honoured, and the neutral force list wins over the mob force list
- __1.12.2 only:__ only blocks with a collision box block the view of turrets
- __1.12.2 only:__ turrets aim relative to the side of the base they sit on, the same way on server and client, and turn smoothly
- __1.12.2 only:__ pets of players in the owner's scoreboard team are no longer targeted, and team members no longer get turret warnings
- __1.12.2 only:__ pets are protected by the trust list of their owner also while the owner is offline
- __1.12.2 only__ · _OMLib_: members of the owner's scoreboard team count as trusted (lowest access level) for owned blocks
- __1.20.1/1.21.1 only:__ projectile turrets aim at the target's eyes instead of its body when a ledge hides the body
- __1.20.1/1.21.1 only:__ turret hits no longer knock their targets back

### Turrets

- The Relativistic Turret is now the Slowing Turret
- The Rail Gun Turret ignores Scatter Shot upgrades (no extra rays, ammo, energy or scatter); with them it dealt a multiple of its damage, since it barely scatters and every ray hit
- The Melee, Slowing and Teleporter Turrets no longer use more energy with Scatter Shot upgrades; they act once per shot
- The Melee Turret strikes everything it may hurt in a 3x2x3 area around itself and its base, without waiting for the base to pick a target
- The Melee Turret only fits on top of or below a turret base
- __1.12.2 only:__ melee turrets on the sides of a base drop as items
- __1.12.2 only:__ the Arc Turret can be placed on every side of a base, not only on top
- __1.12.2 only:__ the particles of the Teleporter Turret are shown in multiplayer too
- __1.20.1/1.21.1 only:__ the Arc Turret chains a bit farther and bounces up to two times
- __1.20.1/1.21.1 only:__ the Crossbow Turret fires the new Crossbow Bolt ammo (iron ingot, stick, feather) instead of vanilla arrows (placeholder texture)
- __1.20.1/1.21.1 only:__ the grenade flies for 1.5 seconds instead of 2 and explodes 4 ticks after hitting a valid enemy

### Turret bases, addons and energy

- Mobs killed by turrets only drop loot if the base has a fake drops addon; each further addon adds one level of Looting
- Only admins of a turret base can attach turrets to it (the placement outline says why otherwise)
- Hoppers and pipes can no longer take ammo out of a turret base, so nobody can disarm someone else's base with them
- Turret bases without an owner (e.g. placed by a machine or a structure) no longer drop themselves; they stay inert until claimed, unless `bases.unownedBasesActive` is set
- Turrets can be attached to a turret base without an owner only by players who may use command blocks (operators, mapmakers; on 1.12.2 operators in creative mode)
- __1.12.2 only:__ a broken turret base scatters its items like a chest
- __1.12.2 only:__ the Recycler addon saves ammo with the configured chance (it saved about 1 % of shots whatever the config said)
- __1.12.2 only:__ the Solar Panel addon charges a base once per tick instead of once per tick for every turret on it
- __1.12.2 only:__ turret bases no longer give their energy to other blocks
- __1.12.2 only:__ the generator GUI labels are black like in the other turret GUIs (they were dark grey on the dark background)
- __1.12.2 only__ · _OMLib_: stored energy above a lowered capacity is cut off
- __1.12.2 only__ · _OMLib_: owned blocks without an owner no longer count as owned by a placeholder player; they stay unowned until someone claims them

### Camouflage and passive defense

- Right-clicking a turret base or camouflage trap with a block no longer camouflages it; the camouflage menu does it now
- Hardened blocks can be used as camouflage (other blocks with a tile/block entity still cannot)
- __1.12.2 only__ · _OMLib_: the camouflage menu has a dark grey background like the turret base GUI instead of the vanilla light grey
- __1.12.2 only__ · _OMPD_: the camouflage trap blocks light like a solid block by default
- __1.12.2 only__ · _OMPD_: fences no longer hurt the owner's team and their pets

### Other

- License: the source code is now MIT (was GPLv3) and the art CC BY-NC-SA 4.0
- __1.12.2 only:__ `turretBreakable` makes turrets mineable with a pickaxe (hardness 3, needs a restart)
- The jar files are named `<mod>-<version>-mc<minecraft version>-<loader>.jar` (`openmodularturrets`; on 1.12.2 also `omlib` and `ompd`)
- __1.20.1/1.21.1 only:__ releases on CurseForge and Modrinth are titled like the jar file
- __1.20.1/1.21.1 only:__ German and English (UK) translations completed

## Removed

- __1.12.2 only:__ inventory and power expanders: they disappear from worlds, together with the items in them (they were not ported to 1.20.1 and 1.21.1 either)
- __1.12.2 only:__ the loot deleter base addon (turret kills drop nothing without a fake drops addon now); placed loot deleters disappear
- __1.12.2 only:__ the power generator attachment (it had no function); the Generator replaces it
- __1.12.2 only:__ the config options `doTurretsKillsDropMobLoot` and `doLootAddonsOverrideMobLootSetting`
- __1.12.2 only__ · _OMLib_: global trust lists (they could not be turned on in game)
- __1.12.2 only__ · _OMLib_: the unfinished network cable block (it crashed the client with missing model variants); placed cables disappear
- __1.12.2 only__ · _OMLib_: the IC2 config options `EUSupport` and `EUtoRFRatio` (they had no effect since IC2 support was removed)

## Fixed

- The `turretBreakable` config option did nothing; turrets can now be broken with a pickaxe when it is enabled
- Cranks and generators did not turn with rotated or mirrored structures
- __1.12.2 only:__ the Melee, Relativistic and Teleporter Turrets crashed the game when they were saved (3.2.0 alpha)
- __1.12.2 only:__ player kills of a base are counted and saved (they were loaded into the kill counter and never saved)
- __1.12.2 only:__ the neutral force list config was read into the mob block list
- __1.12.2 only:__ turrets on auto fire took the ammo of a shot twice
- __1.12.2 only:__ forced shots of Laser, Arc and Railgun Turrets crashed the game without a target and ignored missing energy
- __1.12.2 only:__ the Grenade Turret was only available while the Laser Turret was enabled in the config
- __1.12.2 only:__ the Crossbow Turret's config section had the name of the Potato Cannon Turret's; it is "Crossbow Turret" now
- __1.12.2 only:__ rays of Laser, Railgun and Arc Turrets could hit entities next to the ray
- __1.12.2 only:__ the Plasma Turret tooltip showed tier 3, although the turret needs a tier 5 base
- __1.12.2 only:__ disposable ammo projectiles were invisible
- __1.12.2 only:__ the Melee and Crossbow Turrets had no name (and the Arc Turret none in German, Portuguese, Russian and Chinese)
- __1.12.2 only:__ the configure GUI no longer draws its buttons below its background
- __1.12.2 only:__ the info panel of the turret base GUI no longer covers the GUI when its lines are long (e.g. long player names)
- __1.12.2 only:__ ComputerCraft: `getTrustedPlayer` added the queried player to the trust list when they were not on it
- __1.12.2 only:__ ComputerCraft: `setTurretAutoForceFire` and `forceShootTurret` rejected every valid side
- __1.12.2 only:__ ComputerCraft: number arguments (access levels, modes, sides) were rejected because Lua numbers arrive as decimals; missing arguments now answer "Wrong parameters!"
- __1.12.2 only:__ WAILA/HWYLA crashed the server on a turret whose base was not loaded, and showed the accuracy deviation instead of the accuracy
- __1.12.2 only:__ turrets added by other mods could not fire slower than every 20 ticks (their config clamped `baseFireRate` to 20)
- __1.12.2 only:__ decimal settings of turrets added by other mods (damage amp, upgrades, recycler chances, accuracy deviation) were not limited to their range
- __1.12.2 only:__ the config ranges of `baseFireRate` (now 1–200 ticks) and `baseAccuracyDeviation` (0–100 %) did not include the turrets' default values
- __1.12.2 only:__ computers (ComputerCraft, OpenComputers) could not change access levels: `changeAccessLevel` / `changeTrustedPlayerAccess` and `addTrustedPlayer` with a level reported success but changed nothing
- __1.12.2 only:__ OpenComputers: `setTurretYawPitch` rejected valid angles and used the side as yaw, `forceShootTurret` did not check the side, side 6 counted as the bottom, `addTrustedPlayer` without an access level failed, `getTrustedPlayer` returned nothing for unknown players
- __1.12.2 only:__ turret base GUI actions (range, mode, targeting, dropping) were handled for unloaded or far-away bases, which could load chunks; they now need the base loaded and the player within reach
- __1.12.2 only:__ other mods asking a turret without base (or with its base in an unloaded chunk) for its stats crashed; such a turret now reports its configured values and targets nothing
- __1.12.2 only:__ the maximum range shown in the turret base GUI also counted turrets mounted on a neighbouring base
- __1.12.2 only:__ turret bases, _OMLib_'s camouflaged blocks and _OMPD_'s camo traps could create their tile entity on the chunk render thread, which can crash or corrupt the world
- __1.12.2 only:__ a turret base placed without saved data (e.g. by `/setblock` or a structure) with turrets already attached no longer starts with range 0; it starts at the range of its shortest reaching turret
- __1.12.2 only:__ boxes in the turret logic compared `0.0` and `-0.0` as equal while hashing them differently
- __1.12.2 only:__ tooltips and the turret placement outline used the client's own config instead of the server's
- __1.12.2 only__ · _OMLib_: machines answered other mods' Redstone Flux (RF) capability requests with nothing, and crashed with Redstone Flux installed but not Tesla
- __1.12.2 only__ · _OMLib_: camouflaged blocks could render as grass while their tile entity was missing
- __1.12.2 only__ · _OMLib_: the trusted players GUI crashed on the remove and permission buttons when no player was selected
- __1.12.2 only__ · _OMLib_: the target settings GUI crashed when closed for machines without client sync
- __1.12.2 only__ · _OMLib_: very old trust lists (saved as a plain list of names) are read again
- __1.12.2 only__ · _OMLib_: clients could make the server load or generate chunks anywhere by sending trust list, camouflage or GUI messages for far-away positions; these messages now need the block loaded and the player within reach
- __1.12.2 only__ · _OMLib_: players without access to a block could receive its updates (trust list, settings) by sending its GUI-open message
- __1.12.2 only__ · _OMLib_: loading a world kept the owner share lists (`/omlib share`) of the world opened before it in the same game
- __1.12.2 only__ · _OMLib_: a renamed player (or, in offline mode, a player with another UUID) could be missed in lookups of players and trusted players
- __1.12.2 only__ · _OMLib_: changes in OMLib's config GUI were only applied after a restart
- __1.12.2 only__ · _OMLib_: the debug tool crashed a dedicated server when used on a turret base
- __1.12.2 only__ · _OMLib_: items dropped from a broken machine lost data other mods keep on the item stack (capabilities)
- __1.12.2 only__ · _OMPD_: crash on hardened blocks, walls, fences and camo traps with invalid metadata (damaged chunks, /give)
- __1.12.2 only__ · _OMPD_: hardened blocks, walls, fences and camo traps placed by something other than a player (e.g. a deployer) crashed the game
- __1.12.2 only__ · _OMPD_: sneak-right-clicking your own block with an empty hand did not always pick it up
- __1.12.2 only__ · _OMPD_: the creative tab showed its translation key instead of its name
- __1.12.2 only__ · _OMPD_: WAILA/HWYLA showed no owner name for hardened blocks, walls and fences
- __1.20.1/1.21.1 only:__ shift-clicking addons and upgrades into a turret base no longer ignores their slot stack limit
- __1.20.1/1.21.1 only:__ projectiles now properly apply on-hit effects on their motion, and grenades no longer hurl away when they hit entities
- __1.20.1/1.21.1 only:__ Potato Cannon and Disposable Turret projectiles are visible right at the turret instead of a few blocks away, and show a potato or cobblestone when fired without ammo (Creative Upgrade)
- __1.20.1/1.21.1 only:__ turret projectiles that flew into a chunk without entity ticking froze there; they remove themselves now, as in 1.12.2
- __1.20.1/1.21.1 only:__ on the very first start (no config file yet), the disposable ammo list and the entity black and force lists were ignored until the next restart
- __1.20.1/1.21.1 only:__ the Redstone Reactor addon burns a redstone block or dust when its energy fits the free storage exactly; before, it needed more room than that
- __1.20.1/1.21.1 only:__ the English (UK) Turret Limit label was broken
- __1.20.1/1.21.1 only:__ the mod metadata named the wrong license (GPL-3.0); the jar now contains all three license files
- __1.20.1/1.21.1 only:__ turret bases and generators no longer drop a second copy of their items when they are moved or replaced without breaking (`/setblock`, mods that move blocks)
- __1.20.1/1.21.1 only:__ turrets also turn with rotated or mirrored structures, and turrets, cranks and generators with moved blocks, so turrets and cranks stay attached to their base
- __1.20.1/1.21.1 only:__ adding a trusted player by a name the server does not know no longer freezes the server while the name is looked up at Mojang
- __1.20.1/1.21.1 only:__ "Drop turrets" only breaks blocks that are still turrets

## For mod and addon developers

- Turret API: other mods can add turrets with their own weapons, ammo and models, and custom logic: self-targeting weapons find their own targets, projectile and ray weapons can run code when they hit an entity, and `OMTApi.canDamage` / `OMTApi.hurt` apply the base's trust and damage rules; plugins are marked with `@OMTPlugin.Register` / `@OMTClientPlugin.Register`. See `docs/turret-api.md` in the mod's repository
- __1.12.2 only:__ added turrets get their config in `config/openmodularturrets_addon_turrets.cfg`
- __1.20.1/1.21.1 only:__ added turrets get their config entries under `turrets.addon_turrets`; on Fabric, plugins use the `openmodularturrets` entrypoint instead of the annotations
- __1.12.2 only:__ removed the base controller API (`IBaseController`, `ILaserController`) of the discontinued OMTControl addon
- __1.12.2 only:__ removed the entity and ammo lists of the 3.x API (`api.lists`); they no longer affected targeting (the config lists and the disposable ammo allow list stay)
- __1.12.2 only__ · _OMLib_: the client-only GUI and render helpers moved from `omtteam.omlib.api.gui` / `api.render` to `omtteam.omlib.client.gui` / `client.render` (`ColorOM`, `ICamoSupport` and `RenderBlockStateContainer` stay)
- __1.12.2 only__ · _OMLib_: `ICamoSupport` has four new methods (`isCamoEnabled`, `supportsLight`, `canSetCamo`, `canChangeLight`), and `getOwnedBlock()` is now `getCamoTileEntity()`, returning any `TileEntity`, so camouflage hosts no longer need to be owned blocks
- __1.12.2 only__ · _OMLib_: memory card rules (`core.card`: card data, who may copy and write, trust list copying) shared by turret bases and camouflage traps
- __1.12.2 only__ · _OMLib_: tile entity base `tileentity.TileEntitySynced` (data hooks `readData` / `writeData`, separate client data `writeClientData`, `syncToClient`, `remesh`); `TileEntityBase` now builds on it and behaves as before
- __1.12.2 only__ · _OMLib_: `container.WindowValues` syncs int values of a container to its GUI as window properties (two 16-bit halves each)
- __1.12.2 only__ · _OMLib_: `util.inventory.InvUtil.dropItems` spills an inventory when its block breaks, `inventory.AutomationItemHandler` is the hopper/pipe view of a machine's slots
- __1.12.2 only__ · _OMLib_: `WorldUtil.getTileEntity(IBlockAccess, BlockPos)` looks up a tile entity without creating it
- __1.12.2 only__ · _OMLib_: `api.permission.IOwnedHost` (owner, claim, clear; implemented by `TileEntityOwnedBlock`), `handler.ClaimSpread`, `block.UnownedMarker` (green sparkle on unowned blocks), `api.block.IPlainLookingBlock` (blocks with a tile entity that may still be a disguise) and `IDrawOutline.canPlace` with the player
- __1.12.2 only__ · _OMLib_: removed the tile entity base classes `TileEntityElectric`, `TileEntityContainerElectric`, `TileEntityMachine`, `TileEntityTrustedMachine` and `TileEntityContainer`; tile entities hold the helpers `power.EnergyCapabilities` and `tileentity.InventoryNbt` instead (same NBT keys)
- __1.12.2 only__ · _OMLib_: removed the unused device network API (`api.network.OMLibNetwork`, `INetworkTile`, `IPowerExchangeTile`, `IController`, `INameController`) and helpers (`Tuple3`, `EntityUtil`, `ItemUtil`, `ItemStackList`, `PropertyTools`, `BlockingAbstractGui`)

## Coming in the next pre-release

These changes are done but not released yet.

### Changed

- __1.20.1/1.21.1 only:__ the camouflage menu has a dark grey background like the turret base GUI instead of the vanilla light grey (1.12.2 has this since 4.0.0-beta.3)
- __1.20.1/1.21.1 only:__ the generator GUI labels are black like in the other turret GUIs (1.12.2 has this since 4.0.0-beta.3)

### Fixed

- __1.20.1/1.21.1 only:__ a turret base placed without saved data (e.g. by `/setblock` or a structure) with turrets already attached no longer starts with range 0; it starts at the range of its shortest reaching turret (1.12.2 has this fix since 4.0.0-beta.2)

## Release history

| Version | 1.12.2 (OMT, OMLib, OMPD) | 1.20.1/1.21.1 |
| --- | --- | --- |
| 4.0.0-alpha.1 | 2026-10-23 | 2026-10-12 |
| 4.0.0-alpha.2 | 2026-10-23 | 2026-10-13 |
| 4.0.0-alpha.3 | | 2026-10-13 |
| 4.0.0-alpha.4 | | 2026-10-13 |
| 4.0.0-beta.1 | 2026-10-24 | 2026-10-14 |
| 4.0.0-beta.2 | 2026-10-26 | 2026-10-15 |
| 4.0.0-beta.3 | 2026-10-26 | 2026-10-15 |
| 4.0.0-beta.4 | | 2026-10-17 |
| 4.0.0-beta.5 | | 2026-10-21 |
| 4.0.0-beta.6 | | 2026-10-24 |
| 4.0.0-beta.7 | | 2026-10-24 |
| 4.0.0-beta.8 | | 2026-10-25 |
| 4.0.0-beta.9 | | 2026-10-25 |

The changelogs of the single releases are in the mods' repositories:
[OpenModularTurrets 1.20.1/1.21.1](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/blob/1.20.1%2B/CHANGELOG.md),
[OpenModularTurrets 1.12.2](https://github.com/OpenModularTurretsTeam/OpenModularTurrets/blob/1.12/CHANGELOG.md),
[OMLib 1.12.2](https://github.com/OpenModularTurretsTeam/OMLib/blob/1.12/CHANGELOG.md),
[OpenModularPassiveDefense 1.12.2](https://github.com/OpenModularTurretsTeam/OpenModularPassiveDefense/blob/1.12/CHANGELOG.md).
