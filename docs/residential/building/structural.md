---
layout: default
title: Structural
parent: Building Style
grand_parent: Residential
nav_order: 1
---

# Structural building
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

Structural building focuses on how to create the base structure of a building.
Rather than creating a 5x7 house over and over again, many creators use
different structural builds to keep enough diversity around. Some builds are
L-shape, others have several layers to them. There are buildings with a
cross-shape, and others focus more on interconnected buildings.

Some content creators have even perfected the art of creating diagonal
buildings or slightly rotated ones (e.g. builds that are 30 degrees from the
standard lines).

To keep things diverse, I am looking for some randomization in the builds that
I create.

# Generic shape

In DnD world building, one way of creating new worlds is to use
crafting/building generations based on the roll of a dice. So why not apply the
same to Minecraft builds?

Below are the steps I take to get to a general shape.

## Create a rough foundation

Buildings should have a rough, stony foundation (if applicable to the biome
they are meant to be in). This allows for a more proper generation in case
the building is on a cliff (or similar).

Minecraft can generate this for us if we want. In the structure definition
(part of `worldgen/structure`) the parameter `terrain_adaptation` can be used
for this. Possible values are:
- `none` (default)
- `beard_thin`, which does slight foundation work
- `beard_box`, which should do more foundation work
- `bury`, which encases the build

For most overworld structures, `beard_thin` is a good approach. If the
generations are not good, create a foundation yourself and use `none`.

When building an entire "set" of buildings in a similar pallette, it is
always a good idea to first generate a template (e.g. using some black wool)
and copy/paste that.

## Building size

The first thing I want to settle on is how big a building should be. Now, if
there is a specific purpose for the building I might skip this step, but I find
myself often creating same-sized buildings (e.g. in villages and hamlets),
mostly looking into 9x9-ish size. After a while, that becomes a bland size...

So, what I do is use a width and length based on `4 + 1d6` (meaning, throw one
6-sided die and add the results to 4). This gives the width and length, but
excluding possible extrusions and decorations. A roof that expands one block
thus is not included in this size - it is meant for the foundation(s) of a
build.

This gives a size of 5 to 10 blocks. This seems to fit Minecraft build style
pretty well (not too big) while still allowing for some detailing. If you
prefer larger builds, you can always increase the base (say start with a
8-width base, and add `1d6` to get up to 14 width) or use dice that give larger
numbers.

## Grid size

Next, I want to deduce the grid size. This is like the width and height, and
are combined with the building size from earlier on.

For regular houses, I use `1d4` for width and height each. So if I throw a 3
and a 2, then I would get a 3x2 grid, which would look like so:

```
+---+---+---+
|   |   |   |
+---+---+---+
|   |   |   |
+---+---+---+
```

## Cell sizes

Next I want to assign the size of each cell. This takes into account the total
size. To calculate the size of a cell, I start with a minimum size of 2.

Say the building size is 9, and there are 2 cells to consider. That means that
already 4 blocks are 'reserved', and I have to assign 5 more blocks across the
two cells. While you could create lists of all possible distributions, I tend
to distribute according to the `1d12` die. This allows me to use the ratio of
the resulting numbers.

For two cells, I throw `2d12`, for three cells `3d12`, etc. The resulting values
give me an indication on how to distribute the remaining work. Let's see a few
examples:

- A building size of 5 with two cells. Four blocks are already assigned. `2d12`
  gives 10 and 2, so the first cell gets the available block. The end result is
  `{3,2}`.
- A building size of 9 with 4 cells. Eight blocks are already assigned. `4d12`
  gives 9, 1, 7, 7, so the first cell gets the available block. The end result
  is `{3,2,2,2}`.
- A building size of 9 with 2 cells. Four blocks are already assigned. `2d12`
  gives 5 and 9. So I distribute 2 and 3 (which is roughly the ratio of 5 and
  9) to give an end result of `{4, 5}`.
- A building size of 8 with 2 cells. Four blocks are already assigned. `2d12`
  gives 2 and 8, so I distribute 1 and 3 to get `{3, 5}`.


## Cell builds

Next, for each cell in the grid, I throw the dice to see if that cell will
contain a house unit (which is a bit like a room, although the final house
might not use each cell as a separate room - it depends on the constraints
given like the size).

- For the ground floor, the cell gets a unit if `1d4` is 1, 2 or 3.
- For the first level, the cell gets a unit if `1d4` is 1 or 2.
- For the second level, the cell gets a unit if `1d4` is 1.

Hence, houses will get at most 3 layers.

As an example, using the 3x2 grid, let's say for the ground floor I had the
values 2, 1, 2, 4, 2 and 4. Hence, the ground floor would have units like so:

```
+---+---+---+
| 2 | 1 | 2 |
+---+---+---+
  4 | 2 | 4
    +---+
```

The first floor gets 1, 2, 3, 2, 4 and 4, so:

```
+---+---+
| 1 | 2 | 3
+---+---+
| 2 | 4   4
+---+
```

The third floor gets 1, 1, 4, 3, 4 and 2, so:

```
+---+---+
| 1 | 1 | 4
+---+---+
  3   4   2
```

You might wonder, the second floor has a unit on top of nothing? Indeed, that
gives an area where you have a roof but are otherwise still outside. I might
use that location as a workspace for a blacksmith for instance.

![Example of an area with 1st floor used for building but not on ground level](https://i.imgur.com/M8SFHSL.jpg)

*Example of a building where the ground floor had a cell that isn't containing a build, whereas the floor above does. In this case, it was a 2x2 grid.*

## Unit modifiers

Finally, and actually also optionally, I look if a unit should be modified.
Modifiers here are about placement in the three dimensions: horizontal (flat
plan) and vertical (height).

{: . note}
Unit modifiers are useful when the build is very large and can use some
additional detailing. For most of the residential builds I tend to ignore unit
modifiers, although occasionally one or two come into play if the alternative
would be too little differentiation.

The result of the shifting might not always make sense, but it gives for some
nice random ideas to work with. Note that these modifiers can/will adjust the
unit sizes as described earlier.

### Modify horizontally

First, on the plane, I want to know if I have to shift a unit. I use `1d4` to
see if I need to shift it. A value of 1 or 2 means that it stays where it is. A
value of 3 means to shift one block, whereas a value of 4 means two blocks.

If I have to shift, then I use a `1d8` to find the direction. The direction is
based on the following map:

```
 8  1  2
 7  x  3
 6  5  4
```

So basically, a 1 means the unit shifts backwards, whereas a 4 means forward and sideways. Or, using a compass-alike view, it means:

| Number | Direction  |
|:-------|:-----------|
| 1      | North      |
| 2      | North-East |
| 3      | East       |
| 4      | South-East |
| 5      | South      |
| 6      | South-West |
| 7      | West       |
| 8      | North-West |

### Modify vertically

Then the same is done with vertical shifts, using the same method:

- First `1d4` to see if I do want to stay as-is (1, 2), shift one block (3) or two blocks (4)
- Next, if I need to shift, `1d8` with the value giving the direction to shift.

# Roofs

There are different roof designs possible.

I generally try to use a small set of roof designs per village so there is not
that many variation within a single village. However, besides the roof design,
there are also other roof structural changes to apply.

## Roof styles

There are several roof styles, based upon how steep you want the roof to go.

1. Flat roofs
2. Gradual raise, using slabs
3. Regular raise, using stairs
4. Sharp raise, using stairs alternating with full blocks

Furthermore, you can have

1. Symmetric roofs (`/\` shape)
2. One-sided roofs (`/` shape)
3. Tip-shaped roofs (like with church towers)

## Roof adjustments

Next to the regular roof, there are adjustments one can take up.

| Number | Description |
|:-------|:------------|
|        | Regular roof, no adjustments |
|        | Dormer window, perhaps use dice to see on which units of the structural build to apply. |
|        | Skylight sideways (i.e. window/glass follows the shape of the roof ) |
|        | Skylight at peak of the roof |
|        | Chimney |
