---
layout: default
title: Template pool
parent: Worldgen
grand_parent: Data pack
nav_order: 1
---

The template pools contain the definitions of the pools of structures
that Minecraft can use when structures are generated. Template pools are
the target for structure sets, as well as targets for jigsaw blocks.

The location for pools is at `worldgen/template_pool`.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

# Subdirectory structure

Within my data packs, I use some structure to quickly find the right asset.

## Build folder structure

For larger builds, I use the following folder structure:

```
<build_class> / <biome> / <sequence> / <build_type> / <structure>
```

| Name | Description | Example |
|:-----|:------------|:--------|
| `build_class` | Class of the building or structure | `village`, `hamlet`, `studio` |
| `biome` | Biome for which the pool is meant. Can also be `generic` for reusable builds. | `plains`, `snowy` |
| `sequence` | Identifier for the build pallette/results, generally just a number | `01`, `02` |
| `build_type` | Generation type of the build | `regular`, `ruin` |
| `structure` | Structure type | `center`, `road` |

The _sequence_ is to support multiple variants. For instance, if I want to
create a new plains village with a different build style, then I create one in
a new sequence. I then use a script that merges the various centers into one
big JSON file, allowing for random picks to be used.

# Build classes

Currently, the `polystruct` data pack has the following build classes (that I
want to retain - there are others in it that I want to adjust):

| Build class | Description | Subdirectory structure |
|:------------|:------------|:-----------------------|
| camp | Places where hikers might have set up, currently containing tents | build |
| hamlet | Smallest residential area | build |
| village | Regular residential area | build |
| town | More centralized residential area | build |
| city | Large, centralized residential area | build |
| studio | Interior design for rooms containing bed, workstation and living aspects | build |

## Studio

Studios are interior builds, with a given width-depth-height. For instance,
a 3x5x4 is a 3 blocks wide, 5 blocks deep and 4 blocks high interior room.

A studio _always_ has a jigsaw in the most left of the interior, on the floor
(i.e. one block above the ground itself). This jigsaw has `polystruct:studio`
as name.

| Size  | Structure base                                |
|:------|:----------------------------------------------|
| 3x3x2 | `polystruct:studio/generic/01/regular/3x3x2/` |
| 5x5x3 | `polystruct:studio/generic/01/regular/5x5x3/` |
| 3x3x3 | `polystruct:studio/generic/01/regular/3x3x3/` |
