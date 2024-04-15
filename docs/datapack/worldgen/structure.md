---
layout: default
title: Structure
parent: Worldgen
grand_parent: Data pack
nav_order: 4
---

Structures within the `worldgen` location are the definitions of the in-game
structures. For instance, a village is defined as a structure, and can be placed
as such. Structure definitions inform Minecraft about what the start (template)
pool is, how high to place the structure (mostly on the world, but can be below
ground as well), etc.

Minecraft wiki: [Structure/JSON](https://minecraft.wiki/w/Structure/JSON_format)

# Introduction

TODO

# Using pool aliases

From [minecraft snapshot 23w42a](https://www.minecraft.net/en-us/article/minecraft-snapshot-23w42a)
onward, Minecraft supports `pool_aliases` within a structure definition. This allows
for changing the target pool in the jigsaw blocks used within the (NBT) structures to
another pool.

One of the use cases is to create a generic set of roads, and use the `pool_aliases` to
switch from a generic pool to a specific pool. For instance, a structure for a ruined
badlands village (`polygame:ruined_village_badlands`) could switch from a generic roadset
to a pool definition specific for ruined village badlands:

```
    "pool_aliases": [
        {
            "type": "direct",
            "alias": "polystruct:village/generic/roads"
            "target": "polystruct:village/badlands/01/ruin/roads"
        },
        {
            "type": "direct",
            "alias": "polystruct:village/generic/structs",
            "target": "polystruct:village/badlands/01/ruin/structs"
        }
    ]

```
