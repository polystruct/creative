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

I try to keep some consistency in the use of villagers and villager houses. Especially
for the houses in residential areas, I like to stick to designs that force the
villager into a particular profession. This does mean I am somewhat limited for
the interior design and the use of certain materials (especially barrels) as I
do not want villagers to take on a different profession than intended.

# Professions, chests and colors

For the standard professions, I keep a standard coloring scheme for their beds.
Furthermore, as my intention is to facilitate exploration, I do like to have
loot placed in every house. The loot tables are currently always those of
vanilla minecraft.

| Profession    | Workstation       | Bed color  | Loot table                            |
|:--------------|:------------------|:-----------|:--------------------------------------|
| Armorer       | Blast Furnace     | blue       | `chests/village/village_armorer`      |
| Butcher       | Smoker            | orange     | `chests/village/village_butcher`      |
| Cartographer  | Cartography Table | brown      | `chests/village/village_cartographer` |
| Cleric        | Brewing Stand     | white      | `chests/village/village_temple`       |
| Farmer        | Composter         | lime       | `chests/village/village_plains_house` |
| Fisherman     | Barrel            | green      | `chests/village/village_fisher`       |
| Fletcher      | Fletching Table   | yellow     | `chests/village/village_fletcher`     |
| Leatherworker | Cauldron          | light blue | `chests/village/village_plains_house` |
| Librarian     | Lectern           | pink       | `chests/village/village_plains_house` |
| Mason         | Stonecutter       | magenta    | `chests/village/village_mason`        |
| Shepherd      | Loom              | light gray | `chests/village/village_shepherd`     |
| Toolsmith     | Smithing Table    | gray       | `chests/village/village_toolsmith`    |
| Weaponsmith   | Grindstone        | black      | `chests/village/village_weaponsmith`  |

I have not yet switched the loot table based on biomes, even though that is also
available (such as `village_taiga_house` rather than `village_plains_house`).
Something on the never-ending TODO list.

The list of available loot tables can be found on [Minecraft Chest Loot Table
List](https://www.planetminecraft.com/blog/minecraft-lootchests/) by McMeddon
or on [Misode's mcmeta
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

