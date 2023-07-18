---
layout: default
title: Data pack
nav_order: 4
has_children: true
---

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

