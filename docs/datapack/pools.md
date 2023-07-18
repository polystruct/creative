---
layout: default
title: Pools
parent: Data pack
nav_order: 3
---

Template pools are the entry point to bring structures (or mobs, or features, or ...) into the world.

# Minecraft pools

The following pools are provided by minecraft automatically.

## Villagers

Villagers are provided per biome.

| Biome | Pool |
|:------|:-----|
| Plains | `minecraft:village/plains/villagers` |
| Desert | `minecraft:village/desert/villagers` |
| Savanna | `minecraft:village/savanna/villagers` |
| Snowy | `minecraft:village/snowy/villagers` |
| Taiga | `minecraft:village/taiga/villagers` |

These pools give a 10-1-1 chance of providing an unemployed vilager, baby villager, or nitwit.

There are also equivalent zombie villagers:

| Biome | Pool |
|:------|:-----|
| Plains | `minecraft:village/plains/zombie/villagers` |
| Desert | `minecraft:village/desert/zombie/villagers` |
| Savanna | `minecraft:village/savanna/zombie/villagers` |
| Snowy | `minecraft:village/snowy/zombie/villagers` |
| Taiga | `minecraft:village/taiga/zombie/villagers` |

These pools give a 10-1 chance of providing an unemployed zombie villager, 
or nitwit. This is done through the structures `minecraft:village/plains/villagers/<name>`,
with `<name>` being either `baby`, `unemployed`, or `nitwit`.

Both of these pools require an update-directed jigsaw block to connect to, with the following properties:

| Property | Value |
|:---------|:------|
| pool | See above |
| name | `minecraft:empty` |
| target name | `minecraft:bottom` |

# Template pools

In my datapack, the following supporting template pools exist.
