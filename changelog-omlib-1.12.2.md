---
layout: page
title: OMLib 4.0.0 on 1.12.2
permalink: /changelog/omlib/1.12.2/
---

This is the full changelog of **OMLib 4.0.0 for Minecraft 1.12.2** (Forge), the library mod that Open Modular Turrets, Open Modular Passive Defense and Open Modular Lighting require, merged from all of its alpha and beta releases.
It holds the ownership, trust, camouflage and memory card code that the mods share; what these mean for the turrets is in the [OMT changelog](/changelog/omt/1.12.2/).

The latest pre-release is **4.0.0-beta.6** (2026-10-29).

Other changelogs: [OMT on 1.12.2](/changelog/omt/1.12.2/), [OMT on 1.20.1/1.21.1/1.21.11](/changelog/omt/1.20.1-1.21.1-1.21.11/), [OMLib on 1.20.1/1.21.1/1.21.11](/changelog/omlib/1.20.1-1.21.1-1.21.11/), [OMPD on 1.12.2](/changelog/ompd/1.12.2/), [Open Modular Lighting 1.0.0](/changelog/oml-1.0.0/).

## Added

### Ownership

- Right-clicking a turret base, turret, camouflage trap or hardened block/wall/fence without an owner claims it and the unowned blocks connected to it (up to `claimSpreadLimit`, default 1024); machines' fake players only claim if `fakePlayersCanClaim` is set
- Ownership Wand (creative, operators only) for mapmakers: right-click makes you the owner of an owned block, sneak-right-click removes its owner; it spreads to the connected blocks of the same owner unless switched off with a sneak-right-click into the air 

### Camouflage, trust and memory card

- Camouflage menu for turret bases and camouflage traps: a disguise slot (click with a block to set it, empty-handed to reset) and, on tier 4 and 5 bases and the camouflage trap, light value and light opacity sliders
- Turret bases and camouflage traps can be camouflaged as any full block, opaque or transparent (glass, ice, leaves)
- The camouflage trap's trust list names its lowest level "Trusted" (and its button fits the label), explains both levels when hovering "Permissions", and has tooltips on its Trusted and Disown buttons; trust list tooltips and the disown confirmation use the texts of the modern versions
- The camouflage menu shows the block's name as its title
- The Ownership Wand has epic rarity, and its tooltip lists the turret immunity line last

## Changed

### Targeting and aiming

- Members of the owner's scoreboard team count as trusted (lowest access level) for owned blocks

### Turret bases, addons and energy

- Stored energy above a lowered capacity is cut off
- Owned blocks without an owner no longer count as owned by a placeholder player; they stay unowned until someone claims them

### Camouflage and passive defense

- Right-clicking a turret base or camouflage trap with a block no longer camouflages it; the camouflage menu does it now

## Removed

- Global trust lists (they could not be turned on in game)
- The unfinished network cable block (it crashed the client with missing model variants); placed cables disappear
- The IC2 config options `EUSupport` and `EUtoRFRatio` (they had no effect since IC2 support was removed)

## Fixed

- Machines answered other mods' Redstone Flux (RF) capability requests with nothing, and crashed with Redstone Flux installed but not Tesla
- Camouflaged blocks could render as grass while their tile entity was missing
- The trusted players GUI crashed on the remove and permission buttons when no player was selected
- The target settings GUI crashed when closed for machines without client sync
- Very old trust lists (saved as a plain list of names) are read again
- Camouflaged blocks with a see-through disguise such as leaves no longer make the neighbouring blocks look transparent
- The disguise slot of the camouflage menu shows a new disguise at once instead of after reopening the menu
- Picking a camouflaged block (turret base, camouflage trap) gives its disguise instead of revealing the block
- The Multi Tool showed a raw name and was in no creative tab
- The access level tooltip of the trust list appeared over the player list; it shows when hovering the "Permissions" label now
- A negative maximum range could make the targeting range negative
- Missing German camouflage menu texts and untranslated Chinese trust list tooltips
- Clients could make the server load or generate chunks anywhere by sending trust list, camouflage or GUI messages for far-away positions; these messages now need the block loaded and the player within reach
- Players without access to a block could receive its updates (trust list, settings) by sending its GUI-open message
- Loading a world kept the owner share lists (`/omlib share`) of the world opened before it in the same game
- A renamed player (or, in offline mode, a player with another UUID) could be missed in lookups of players and trusted players
- Changes in OMLib's config GUI were only applied after a restart
- The debug tool crashed a dedicated server when used on a turret base
- Items dropped from a broken machine lost data other mods keep on the item stack (capabilities)

## For mod and addon developers

- The client-only GUI and render helpers moved from `omtteam.omlib.api.gui` / `api.render` to `omtteam.omlib.client.gui` / `client.render` (`ColorOM`, `ICamoSupport` and `RenderBlockStateContainer` stay)
- `ICamoSupport` has four new methods (`isCamoEnabled`, `supportsLight`, `canSetCamo`, `canChangeLight`), and `getOwnedBlock()` is now `getCamoTileEntity()`, returning any `TileEntity`, so camouflage hosts no longer need to be owned blocks
- Inventories whose slots hold more than one stack (`LargeStackHandler` / `LargeStackItemHandler`, with container slots, container and GUI): saved, synced and filled by hoppers and pipes up to the slot limit
- Camouflage hosts say which blocks they accept with `DisguiseRules` (also their refusal message and slot hint), and a Back button leads to a host's parent menu (`ICamoSupport.hasParentMenu` / `openParentMenu`, opened by the server); lightning render messages carry a colour
- Memory card rules (`core.card`: card data, who may copy and write, trust list copying) shared by turret bases and camouflage traps
- Tile entity base `tileentity.TileEntitySynced` (data hooks `readData` / `writeData`, separate client data `writeClientData`, `syncToClient`, `remesh`); `TileEntityBase` now builds on it and behaves as before
- `container.WindowValues` syncs int values of a container to its GUI as window properties (two 16-bit halves each)
- `util.inventory.InvUtil.dropItems` spills an inventory when its block breaks, `inventory.AutomationItemHandler` is the hopper/pipe view of a machine's slots
- `WorldUtil.getTileEntity(IBlockAccess, BlockPos)` looks up a tile entity without creating it
- `api.permission.IOwnedHost` (owner, claim, clear; implemented by `TileEntityOwnedBlock`), `handler.ClaimSpread`, `block.UnownedMarker` (green sparkle on unowned blocks), `api.block.IPlainLookingBlock` (blocks with a tile entity that may still be a disguise) and `IDrawOutline.canPlace` with the player
- Removed the tile entity base classes `TileEntityElectric`, `TileEntityContainerElectric`, `TileEntityMachine`, `TileEntityTrustedMachine` and `TileEntityContainer`; tile entities hold the helpers `power.EnergyCapabilities` and `tileentity.InventoryNbt` instead (same NBT keys)
- Removed the unused device network API (`api.network.OMLibNetwork`, `INetworkTile`, `IPowerExchangeTile`, `IController`, `INameController`) and helpers (`Tuple3`, `EntityUtil`, `ItemUtil`, `ItemStackList`, `PropertyTools`, `BlockingAbstractGui`)

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

The changelogs of the single releases are in the mod's repository: [OMLib 1.12.2](https://github.com/OpenModularTurretsTeam/OMLib/blob/1.12/CHANGELOG.md).
