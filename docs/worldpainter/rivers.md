---
layout: default
title: Rivers
parent: WorldPainter
nav_order: 4
---

I generally use the following settings for rivers:

- *Material* is set to `water`.
- *Thickness* is set to -7.
- We apply *linear* carving.
- Use 4 width.

You can differentiate a bit more if needed, e.g.

- Streams use -2 thickness, sheer type, 1 width
- Small Rivers use -3 thickness, linear, 4 width
- Regular Rivers use -7 thickness, linear, 4 width
- Wide Rivers use -7 thickness, linear, 10 width

Alongside the river itself, there are two additional terrain types to use.

The first is the `River Terrain` which is used on the river floors. It
uses a *Complex* type with noise pattern, and the following material:

| Material           | Size |
|:-------------------|:-----|
| gravel             | 35   |
| cobblestone        | 5    |
| mossy\_cobblestone | 15   |
| podzol             | 10   |
| coarse\_dirt       | 35   |

The second is the `Riverbank Terrain` to use alongside the river banks.
It too uses a *Complex* type with noise pattern, and has the following
materials:

| Material           | Size |
|:-------------------|:-----|
| podzol             | 1    |
| gravel             | 2    |
| mossy\_cobblestone | 1    |
| coarse\_dirt       | 4    |

To carve a river into the terrain, use *Raise/Lower Terrain* with intensity
50%, apply only on the layer used for rivers, and use a single click (as
otherwise this will carve a too-steep decline).
