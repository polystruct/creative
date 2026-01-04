---
layout: default
title: Residential Areas
parent: Residential
nav_order: 1
---
# Residential Areas
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Hamlets

Hamlets are small municipalities with a few houses. It is characterized as a
single center with one to four houses across. These houses should have villagers
inside them, with some standard (vanilla-style) loot.

![Example taiga hamlet](https://i.imgur.com/xtIMxt3.jpg)

*Example of a taiga hamlet*

Of course, bad things can happen in real life, so this should be reflected in
the Minecraft world as well. Hamlets can be destroyed (for whatever reason)
with only some ruins left over.

![Example of a ruined taiga hamlet](https://i.imgur.com/YJdZfDl.jpg)

*Example of a ruined taiga hamlet*

## Biomes

The intention is to have hamlets for most of the biomes, as in real world
people are able to settle nearly everywhere. Right now, hamlets are made
available for the following biomes:

- badlands
- desert
- plains (including sunflower plains)
- savanna (including savanna plateau)
- snowy plains (called `snowy`)
- swamp
- taiga

## Hamlets in data pack

In my data pack, hamlets can be found through `polygame:hamlet_<biome>`. Ruined
hamlets can be found as `polygame:ruined_hamlet_<biome>`.

As the hamlets are a center with directly attached houses, most of the hamlets
that are placed in the world seem to be presented quite decently. This is
because there are no paths that use the `terrain_matching` projection, so less
quirky generation.

Hamlet generation starts from the center (using the `centers` pool of the
appropriate biome).

# Villages

Villages are municipalities that are characterized with houses that are spread
out. The intention is to have roughly 5 to 10 houses.

![Example plains village](https://i.imgur.com/pLg7QGe.jpg)

*Example of a plains village*

The intention is that villages too can be in ruins (e.g. when they were pillaged
by pillagers). However, it is also possible that villages have some buildings
that are in ruins, and other buildings that are being built up (where you can
find obvious signs that the building is being created, such as having
scaffolding in place and chests with the raw building materials).

![Example ruined plains village](https://i.imgur.com/v1ZEqSb.jpg)

*Example of a ruined plains village*

## Biomes

Villages are available in many of the biomes as well, but not in the swamp.
The idea here is that the swamp isn't sufficiently hospitable to host larger
residential areas, so villages are limited to the following biomes:

- badlands
- desert
- plains (including sunflower plains)
- savanna (including savanna plateau)
- snowy plains (called `snowy`)
- taiga

## Villages in data pack

In my data pack, villages can be found through `polygame:village_<biome>`. Ruined
villages can be found as `polygame:ruined_village_<biome>`.

The structure of villages is a bit more like the native Minecraft villages,
including paths that are using the `terrain_matching` projection. Hence, it is
possible that they generate in a bit more quirky manner.

Village generation starts from the center (using the `centers` pool of the
appropriate biome).

# Towns

{: .note }
Town development has not yet started.

A town is more centralized in nature, and could be fortified. Houses are more
close to each other. Towns also have the possibility to include:

- Speciality shops (e.g. winery)
- Public warehouses (horreums, storage buildings)

## Towns in data pack

The idea is to have a town in a single, large structure (using the maximum 48x48x48
size) and have the buildings generate within this structure.

# Cities

{: note }
City development has not yet started.

A city is a settlement where houses are close or even adjacent to each other.

Cities have specialized buildings, like:

- Speciality shops (e.g. firework shops)
- Cisterns (underground water holding tanks)
- Sewers

## Cities in data pack

The idea is to have a town in either a 2x2 grid of larger structures in which
the city then generates, or in a 3x3 grid. As there is a generation limit in
Minecraft (maximum distance from the center is 128 blocks) I have yet to figure
out how this limit is used.

