---
layout: page
title: OMLib on 1.20.1/1.21.1/1.21.11
permalink: /changelog/omlib/1.20.1-1.21.1-1.21.11/
---

This is the changelog of **OMLib for Minecraft 1.20.1, 1.21.1 and 1.21.11** (Fabric, NeoForge, Forge).
On these versions OMLib is a library that [Open Modular Turrets](/changelog/omt/1.20.1-1.21.1-1.21.11/) (since 4.0.0-beta.10) and [Open Modular Lighting](/changelog/oml-1.0.0/) (since 1.0.0-beta.9) bundle, so there is nothing to install separately.
It has no release of its own yet (its version is 1.0.0-alpha.1): the changes below ship inside the mods, and what they mean for players is in the changelogs of the mods.
On 1.12.2 OMLib is a mod of its own, see [OMLib on 1.12.2](/changelog/omlib/1.12.2/).

Other changelogs: [OMT on 1.12.2](/changelog/omt/1.12.2/), [OMT on 1.20.1/1.21.1/1.21.11](/changelog/omt/1.20.1-1.21.1-1.21.11/), [OMLib on 1.12.2](/changelog/omlib/1.12.2/), [OMPD on 1.12.2](/changelog/ompd/1.12.2/), [Open Modular Lighting 1.0.0](/changelog/oml-1.0.0/).

## Added

- Containers whose slots hold more than one stack (`LargeStackContainer`, with menu slots, menu and screen): saved, synced and moved by hoppers and pipes on all loaders; counts from four digits on are drawn smaller, and the tooltip shows count and limit

## Fixed

- On Forge 1.20.1, the common item tags (`c:iron_ingots`, `c:gold_ingots`, `c:redstone_dusts`, `c:quartz`, `c:diamonds`, `c:glass_panes`) are defined from Forge's own tags; Forge has none, so recipes using them matched no items

The changelog of OMLib is in its repository: [OMLib 1.20.1/1.21.1/1.21.11](https://github.com/OpenModularTurretsTeam/OMLib/blob/1.20.1%2B/CHANGELOG.md).
