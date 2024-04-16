---
layout: default
title: Data pack
nav_order: 4
has_children: true
---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


As part of my ongoing learning, I am also working on a data pack. The intention
initially was to have a datapack through which I can quickly add structures in
a custom world. With the support for structure placing and more extensive data
packs, this has changed a bit to also (and even primarily) generate structures
in a newly generated world, so that I can enjoy the builds when starting a new
world.

The data pack actually consists of two data packs (for now):

- `polystruct` contains all the structures, functions and other material
  that I would like to use in custom worlds, without actually modifying world
  generation at all. This allows me to add the data pack to worlds where I do
  not want to influence regular gameplay.
- `polygame` contains the world generation related settings (including
  placement of structures in biomes). This data pack depends on the first one,
  but also modifies the world and thus gameplay.

The latter data pack will most likely also gradually include more non-native
changes as I play along with the data pack capabilities.

# Subdirectory structure

Within my data packs, I use some structure to quickly find the right asset.

## Build folder structure

For larger builds, I use the following folder structure:

```
[<style> /] <build_class> / <style> / <biome> / <sequence> / <build_type> / <structure>
```

| Name | Description | Example |
|:-----|:------------|:--------|
| `style` | (Optional) Style for which the pool is meant. If undefined, the style is `rustic`. | `rustic` |
| `build_class` | Class of the building or structure | `village`, `hamlet`, `studio` |
| `biome` | Biome for which the pool is meant. Might be called `generic` or other identification that is cross-biome. | `plains`, `snowy` |
| `sequence` | Identifier for the build pallette/results, generally just a number but can be titled as well | `01`, `02` |
| `build_type` | Generation type of the build | `regular`, `ruin`, `build` |
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

# Styles

Style names I use:

| Style | Description |
|:------|:------------|
| rustic | Well-defined, easy, slightly boring style. |

