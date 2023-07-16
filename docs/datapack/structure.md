---
layout: default
title: Structure
parent: Data pack
nav_order: 1
---

{: .note }
This is about the structure of the data packs, not about Minecraft structures.

# Location of structures

The Minecraft structures are stored in the `polystruct` data pack. It mostly
uses the following directory structure, although for some building classes the
directory structure might be less extensive.

```
<building_class> / <biome> / <sequence> / <build_type> / <structure_part>
```

| Name             | Description                    | Example             |
|:-----------------|:-------------------------------|:--------------------|
| `building_class` | Class for the building         | `village`, `hamlet` |
| `biome`          | Biome the build is for         | `plains`, `snowy`   |
| `sequence`       | Sequence (to support variants) | `01`, `02`          |
| `build_type`     | Generation type of the build   | `regular`, `ruin`   |
| `structure_part` | Part of the structure          | `center`, `road`    |

The sequence is to support multiple variants. For instance, if I want to create
a new plains village with a different build style, then I create one in a new
sequence. The `polygame` data pack will randomly pick one (this is done by
joining the pools for all the variants in a single pool, for which I use a
shell script).

# Location of template pools

The same directory structure is used for the template pools. The main
difference is that the `<structure_part>` is no longer a directory, but a JSON
file named after the part (but in plural).

For instance, while all road structures for the 1st plains village are located
in `village/plains/01/regular/road/` (inside the `structures` directory of the
data pack), the pool for the road items is in
`village/plains/01/regular/roads.json` (inside the `template_pool` directory of
the data pack).

