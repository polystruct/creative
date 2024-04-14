---
layout: default
title: Structure
parent: Data pack
nav_order: 2
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

# Template pools

## Location of template pools

The same directory structure is used for the template pools. The main
difference is that the `<structure_part>` is no longer a directory, but a JSON
file named after the part (but in plural).

For instance, while all road structures for the 1st plains village are located
in `village/plains/01/regular/road/` (inside the `structures` directory of the
data pack), the pool for the road items is in
`village/plains/01/regular/roads.json` (inside the `template_pool` directory of
the data pack).

## Combining structures

Structures are combined to build the complete structure set. For this, certain
standard jigsaw combinations (connectors) are used.

### Roads

Roads are all defined in the `roads.json` file. Connectors for roads use level
definitions:

- `polystruct:road_level0` is for the main road. Level-0 roads are allowed to
  turn left or right, or split, at which point the road becomes a Level-1 road.
- `polystruct:road_level1` only contains straight roads. The intention of a
  Level-1 road is that it is equally significant as a Level-0 road (e.g. 3
  blocks wide).
- `polystruct:road_level2` only contains straight roads. These are smaller
  roads than Level-1 roads.

### Triggering full builds

While minecraft nowadays supports placing structures through commands, I do
want to support triggering a full build through a jigsaw. This allows me to
place full builds at the location I want, and with the `/place jigsaw` command
this becomes even easier than before.

To support this, the starting point of a build (like residential areas) have
a jigsaw with a connector name `polystruct:generator`. You can then generate
that build directly with the following command:

```
/place jigsaw polystruct:hamlet/plains/centers polystruct:generator 7 ~ ~ ~
```

### Triggering structures

Structures that are part of a larger build use the `polystruct:struct` connector.

```
/place jigsaw polystruct:hamlet/plains/01/ruin/structs polystruct:struct 7 ~ ~1 ~
```

The receiving jigsaw is always one up (on top of the ground) in the builds, hence
the need to place it one level higher than ground.

{: .note }
Initially I used `polystruct:structure` so some parts of the data pack might
still use that.

### Triggering interior

Some builds separate the outside of a structure from the inside. This allows me
to randomize the interior of buildings, and facilitate more rapid development
of structures.

{: .note }
The jigsaw for a room is always at the most left side in the room, facing
to the side of the door to the room.

The receiving connector uses a connector based on the type of room:

* `polystruct:studio` for an interior that covers a complete living space,
  including bed and workstation
* `polystruct:bedroom` for an interior that covers a bedroom only
* `polystruct:livingroom` for an interior that covers regular living space
* `polystruct:workplace` for an interior covering the workstation and working space

## Randomizing structures

Generic structures, like the rooms, will be stored in a location that has `generic`
instead of a biome name. These structures are always built with two main pallettes
for wood (oak and warped wood) and stone (stone and mossy stone brick). These will
then be converted into the right pallette through datapack processors `oak_to_*`,
`warped_to_*`, `stone_to_*` and `mossy_stone_to_*`.

By providing all these processed entries in a pool, we can effectively provide more
randomized interiors.


