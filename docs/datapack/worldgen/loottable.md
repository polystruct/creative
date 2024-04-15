---
layout: default
title: Loot table
parent: Worldgen
grand_parent: Data pack
nav_order: 3
---

Loot tables inform Minecraft what to drop or to show when a user
kills an entity or opens a block that can contain items.

The location for loot tables is at `loot_tables`.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

# Subdirectory structure

Within my data packs, I use some structure to quickly find the right asset.

## chests

For the residential areas, I have custom chest loot table definitions which
currently only refer to the main, vanilla loot table. My builds will gradually
use these custom loot tables instead, as that allows me to adjust and fine-tune
the loot tables.

```
chests / <residential> / <biome> / <profession>
```

| Name | Description | Example(s) |
|:--|:--|:--|
| `residential` | Type of residential area | `hamlet`, `village` |
| `biome` | Biome in which the area is placed | `plains`, `swamp` |
| `profession` | Profession of the villager the chest belongs to | `farmer`, `cartographer` |


