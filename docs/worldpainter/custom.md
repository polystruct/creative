---
layout: default
title: Customization
parent: WorldPainter
nav_order: 3
---
# Customization
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

WorldPainter allows for ample customization to quickly develop your worlds.

# Custom Terrains

The following custom terrains are used. Once created, save the files with a
leading number. This is needed so that, if I load then, they are loaded in
the same order (which is needed if I want to use them in scripts).

## Rocky terrain

*Rocky* terrain is used for steep hills (above 45 degrees) and in the start
of mountains (height 90 - 140). It uses the following materials:

| Material                      | Sizing |
|:------------------------------|:-------|
| Dirt                          | 20     |
| Cobblestone                   | 55     |
| Stone                         | 650    |
| Mossy\_cobblestone            | 2      |
| Gravel                        | 38     |
| Coal\_ore                     | 5      |
| Andesite                      | 100    |
| Iron\_ore                     | 5      |
| Light\_gray\_concrete\_powder | 50     |

## Rocky Mountain terrain

*RockyMountain* is used for mountains between 140-250. It has *Blobs* enabled,
and contains the following material:

| Material  | Sizing |
|:----------|:-------|
| Stone     | 10     |
| Coal\_ore | 1      |
| Andesite  | 5      |
| Diorite   | 5      |

## Hills terrain

*Hills* has the following materials:

| Material     | Sizing |
|:-------------|:-------|
| Gravel       | 1      |
| Coarse\_dirt | 3      |
| Stone        | 3      |
| Grass\_block | 3      |
| Andesite     | 2      |

## Spruce terrain

*SpruceTerrain* has the following materials, with *Blobs* enabled:

| Material     | Sizing |
|:-------------|:-------|
| Podzol       | 3      |
| Coarse\_dirt | 3      |
| Grass\_block | 3      |

## Farmland and farmcrops

To create nice looking farmland and crops, two custom terrains can be created.

The first is the `Farmland Terrain` custom terrain, which uses layers:

- Layer with X-axis angle of 45 and Z-axis angle of 20
- Use `farmland` with count 3
- Use `coarse_dirt` or `podzol` with count 2

The second is the `Farmland Foliage` custom terrain, which also uses layers
to match the farmland terrain:

- Layer with X-axis angle of 45 and Z-axis angle of 20
- Use `wheat` (with `age 7`) and count 3
- Use `air` with count 2

# Custom Layers

Custom layers allow for quick drawing of environments.

{: .important }
> Use a fixed naming scheme so that the custom layers can be easily built up
> again.

## Tree layers

For tree layers, four custom layers need to be combined:

1. A Trees layer (e.g. `Spruce Trees`) which contains the tree objects
2. A Cover layer (e.g. `Spruce Cover`) which contains the floor covering (souch
   as boulders)
3. A Foliage layer (e.g. `Spruce Foliage`) which contains the plants
4. A Terrain layer (e.g. `Spruce Terrain`) which contains the floor/terrain

The Trees layer should use an appropriate thickness:

- Spruce forests for instance are rather densely packed, so have 1 object
  per 50 blocks at 50% intensity.
- Oak forests are more sparse, so we use 1 object per 100 blocks at 50%
  intensity.

{: .important }
> When drawing forests, first have the paths and rivers drawn before applying 
> the tree layers so that the trees do not generate on the paths or rivers.

### Applying biome

First apply the biome. Use the height differences to apply it correctly.

- Use `Forest` to apply regular forest biome
- Use `Giant Spruce Taiga` for a spruce forest

### Applying trees

Use the appropriate Trees layer (custom). Apply it as follows:

- Use the *Pencil* brush type (not *Spray paint*)
- Use *Constant circle* brush
- Change the intensity as needed. Start with 50 for the entire surface,
  then 75 for the larger inner surface, and 100 for the densely populated
  forest.
- Make sure to only apply on the right biome.

### Applying terrain

Use the appropriate Terrain layer (custom). Apply it as follows:

- Use the *Pencil* brush type.
- Use the *Constant circle* brush.
- Set intensity to 100.
- Make sure to only apply on the right biome.

An exception is when this would generate a too abrupt change. In that case, 
apply it with *Pencil* only on the more intense areas, and use *Spray* to
gradually decreate it to the edges.

### Applying cover

Apply the appropriate Cover layer (custom).

- Use the *Pencil* brush.
- Set *intensity* to 8%.

### Applying foliage

Apply the appropriate Foliage layer (custom).

- Use the *Spray* brush
- Set the *intensity* to 8%.

## Farmland custom layers

For the `Farmland`, use:

- *Thickness* set to -1.
- *Material* set to `Farmland Terrain`.

For the farm crops, use

- *Material* set to `Farmland Foliage`.
