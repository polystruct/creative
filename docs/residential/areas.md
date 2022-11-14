---
layout: default
title: Areas
parent: Residential
nav_order: 1
---

# Hamlets

Hamlets are small municipalities with a few houses. It is characterized as a
single center with one to four houses across. These houses should have villagers
inside them, with some standard (vanilla-style) loot.

![Example taiga hamlet](https://i.imgur.com/Mcp9MFU.png)

Of course, bad things can happen in real life, so this should be reflected in
the Minecraft world as well. Hamlets can be destroyed (for whatever reason)
with only some ruins left over.

![Example of a ruined taiga hamlet](https://i.imgur.com/z05sfTj.png)

## Biomes

The intention is to have hamlets for most of the biomes, as in real world
people are able to settle nearly everywhere. Right now, hamlets are made
available for the following biomes:

- badlands
- desert
- plains and sunflower plains
- savanna and savanna plateau
- snowy plains
- swamp
- taiga

## Hamlets in data pack

In my data pack, hamlets can be found through `polygame:hamlet_<biome>`. Ruined
hamlets can be found as `polygame:ruined_hamlet_<biome>`.

As the hamlets are a center with directly attached houses, most of the hamlets
that are placed in the world seem to be presented quite decently. This is because
there are no paths that use the `terrain_matching` projection, so less quirky
generation.

# Villages

Villages are municipalities that are characterized with houses that are spread
out. The intention is to have roughly 5 to 10 houses.

![Example plains village](https://i.imgur.com/KF0dWHS.png)

The intention is that villages too can be in ruins (e.g. when they were pillaged
by pillagers). However, it is also possible that villages have some buildings
that are in ruins, and other buildings that are being built up (where you can
find obvious signs that the building is being created, such as having
scaffolding in place and chests with the raw building materials).

![Example ruined plains village](https://i.imgur.com/vgpJqRY.png)

## Biomes

Villages are available in many of the biomes as well, but not in the swamp.
The idea here is that the swamp isn't sufficiently hospitable to host larger
residential areas, so villages are limited to the following biomes:

- badlands
- desert
- plains and sunflower plains
- savanna and savanna plateau (not yet implemented)
- snowy plains (not yet implemented)
- taiga (in progress)

## Villages in data pack

In my data pack, villages can be found through `polygame:village_<biome>`. Ruined
villages can be found as `polygame:ruined_village_<biome>`.

The structure of villages is a bit more like the native Minecraft villages,
including paths that are using the `terrain_matching` projection. Hence, it is
possible that they generate in a bit more quirky manner.

# Towns

A town is more centralized in nature, and could be fortified. Houses are more
close to each other. Towns also have the possibility to include:

- Speciality shops (e.g. winery)
- Public warehouses (horreums, storage buildings)

# Cities

A city is a settlement where houses are close or even adjacent to each other.

Cities have specialized buildings, like:

- Speciality shops (e.g. firework shops)
- Cisterns (underground water holding tanks)
- Sewers


