---
layout: default
title: Processor list
parent: Hierarchy
grand_parent: Data pack
nav_order: 2
---

Processor lists provide conversions for structures that Minecraft can
apply. They are generally referenced in the template pools so that
structures can be reused while still providing changes tailored to
that particular structure pool.

The location for processor lists is at `worldgen/processor_list`.

# Subdirectory structure

I use subdirectories that group the main processors together.

# Color switchers

Color switching processors change a block from one color to another.
This allows me to build a structure with a common colored block, and
then randomize this a bit.

## wool processors

In the `wool/` folder, I have the processors that convert wool blocks
from one color to another.

### Single wool processor

```
polystruct:wool/pink_to_<color>
```

Switches the pink wool block to the given color. There is also a 
`pink_to_pink` one so that I can iterate over the colors easily.

### Dual wool processor

{: .note }
This is not yet implemented

```
polystruct:wool/blackwhite_to_<pair>
```

Converts black and white to another color pair. I do not iterate across
all possible values (256) as that would result in far too many referenced
structures in a pool. As Minecraft currently does not support variables
in processors (or something like loot tables to get some block) I limit
this to color pairs that I think make sense.

| yellowblack | yellowred | redwhite |
| whiteblue | yellowblue | blueblack |
| yellowgreen | graylight | orangegray |

## terracotta processors

```
polystruct:terracotta/regular_to_<color>
```

Switches regular terracotta to colored terracotta.

# Interior conversion

Interior conversion processors have a number of functionality
that they cover:

- they switch the pallette of wood and stone a bit, providing some
  randomization
- they change the state of blocks (like furnaces) so they (can)
  contain some random loot, with a chance of good loot
- they change the state of lightsources (candles, torches, ...)

## Room decoration

```
polystruct:interior/room_decor_<wood1>_<wood2>
```

Decorates the room by substituting oak with `wood1` and warped with `wood2`.

This only supports regular wood types though, so no hyphae. I do not provide
a full set of all iterations (as that would give 100 processors), but focus
on a few common combinations:

| `oak_spruce` |

# Using processors

Processors can be used in template pools like so:

```
{
    "weight": 1,
    "element": {
        "description": "Simple tent with chest and crafting table",
        "location": "polystruct:camp/plains/regular/01/tent_01",
        "processors": "polystruct:wool/pink_to_black",
        "projection": "rigid",
        "element_type": "minecraft:single_pool_element"
    }
},
```

Processors do have some limitations.

* You cannot add multiple processors in a template pool. Yes, you can create
  an array of processors, but then they have to be fully described. I would
  have loved to chain processors together (like having an array of processor
  names).
* You cannot use variables in processors. I would have loved to have a variable
  defined in the beginning, perhaps using a loot table to get a value, as that
  would truly make some processors easy to use for randomization.
