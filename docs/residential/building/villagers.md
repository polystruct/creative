---
layout: default
title: Villagers
parent: Building Style
grand_parent: Residential
nav_order: 2
---

# Villagers
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

In my builds, especially in residential areas, I either use builds that are
consistent with the profession of the villager, or at least have some
consistency in the interior design. 

If the build is consistent, then the interior is part of the build itself
(the structure). When this is more open (for instance, when the interior
itself is randomly allocated) then the interior will try to stick to a
certain choice set (such as bed color, and chest loot table).

# Professions, chests and colors

For the standard professions, I keep a standard coloring scheme for their beds.
Furthermore, as my intention is to facilitate exploration, I do like to have
loot placed in every house.

The loot table that I use is a custom one, although for jump-starting the
data pack I do have it pick immediately and only from the vanilla one (the
default loot table I use just has a reference to the "main" loot table). My
intention is to switch to more custom loot once I've found a good balance.

| Profession    | Workstation       | Bed color  | Loot table                            |
|:--------------|:------------------|:-----------|:--------------------------------------|
| Armorer       | Blast Furnace     | blue       | `chests/<area>/<biome>/armorer`       |
| Butcher       | Smoker            | orange     | `chests/<area>/<biome>/butcher`       |
| Cartographer  | Cartography Table | brown      | `chests/<area>/<biome>/cartographer`  |
| Cleric        | Brewing Stand     | white      | `chests/<area>/<biome>/cleric`        |
| Farmer        | Composter         | lime       | `chests/<area>/<biome>/farmer`        |
| Fisherman     | Barrel            | green      | `chests/<area>/<biome>/fisherman`     |
| Fletcher      | Fletching Table   | yellow     | `chests/<area>/<biome>/fletcher`      |
| Leatherworker | Cauldron          | light blue | `chests/<area>/<biome>/leatherworker` |
| Librarian     | Lectern           | pink       | `chests/<area>/<biome>/librarian`     |
| Mason         | Stonecutter       | magenta    | `chests/<area>/<biome>/mason`         |
| Shepherd      | Loom              | light gray | `chests/<area>/<biome>/shepherd`      |
| Toolsmith     | Smithing Table    | gray       | `chests/<area>/<biome>/toolsmith`     |
| Weaponsmith   | Grindstone        | black      | `chests/<area>/<biome>/weaponsmith`   |

All professions also have a loot table `chests/<profession>` without indication of
area (like `hamlet`) or biome (like `snowy`). This generic one, which is based upon
a plains biome, regular Minecraft loot table, is used for structures that do not
yet know which biome and area they are in.

The intention is that these generic loot tables are later on substituted through
the processor(s) assigned to a build.

The list of Minecraft vanilla available loot tables can be found on 
[Minecraft Chest Loot Table List](https://www.planetminecraft.com/blog/minecraft-lootchests/)
by McMeddon or on [Misode's mcmeta
repository](https://github.com/misode/mcmeta/tree/data-json/data/minecraft/loot_tables/chests).

## Villagers in data pack

To place a villager, Minecraft has standard pools available.

Place an upside-directed jigsaw block with the following definition:

| Setting     | Value                                |
|:------------|:-------------------------------------|
| Pool        | `minecraft:village/plains/villagers` |
| Name        | `minecraft:bottom`                   |
| Target name | `minecraft:bottom`                   |

Make sure there is at least 3 blocks of space above (although 2 might work as
well, the villager will spawn with their head in the block but can fall out of
it - as long as that block doesn't hurt the villager that's fine).

