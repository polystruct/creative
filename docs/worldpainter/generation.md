---
layout: default
title: Generation
parent: WorldPainter
nav_order: 1
---

# Generating World

We can generate relatively nice looking terrain using [Azgaar's Fantasy Map
Generator](https://azgaar.github.io/Fantasy-Map-Generator/).

I generally use the following settings. First, select heightmap and deselect
rivers.  Then, in the *Styles* menu:

- select *Monochrome* for style preset
- select *Coastline* and write down the color value (usually `1F3846`). Set
  the opacity then to 0.
- select *Ocean* element and set the color to the previously written down
  value (or clear it out completely and fit later in WorldPainter).
- select *Landmass* element and set the fill to the previously written down
  value.
- select *Lakes* element and set the *Opacity* to 0 for each lake type.
- select *Heightmap* element and set *Reduce layers* to 0, and *Filter* to
  *Blur 7*.

When exporting, scale here rather than in WorldPainter (a scale of 3 seems to
work fine).

Keep the map open, because we also generate additional information which we can
later import as masks:

- Export the *Rivers* of the map. Make sure only the rivers are shown (black
  background, white rivers, no fuzzy pixels). Save it as a file (PNG) with equal
  size as the heightmap. Next, **convert** the PNG file into a true black/white
  so we can use it for imports:

```
~$ convert <source> -threshold %1 <destination>
```

- Export the *Biomes* of the map. In this case, the colors will be used for the
  annotations so we can later generate biomes based on the annotation color.

When importing in WorldPainter:

- Set the minecraft height to a relatively small range so that the heightmap 
  doesn't result in two-block high jumps. For instance, 50-64-150. Current best
  practice seems to be to look at the color difference as shown in WorldPainter,
  and take half of it as the rough difference. 
- Adjust the height of the image based on the preview.
- Do not scale here as it generates artefacts.

{: .note }
The generation is still somewhat finicky, so play around with it. It is better
to have a lower generation and add mountains with WorldPainter afterwards.

# Regeneration

It is advisable to use *annotations* and biomes as much as possible so that the
world can be easily regenerated and reapplied.

To regenerate the world, following the next steps...

First, use the default theme generation (`Ctrl+G`, and select *reset terrain and
layers to theme*).

Then apply the `Hills` custom terrain (which you can do with a WorldPainter
script as well):

- Use *fill with terrain type*
- Select `Hills` (custom terrain)
- Apply *at or above* 64
- Apply *at or below* 150
- Apply *above* 35 degrees
- Do not apply feathering as it will corrupt beaches and ocean edges.

Apply the `Rocky` custom terrain (which you can do with a WorldPainter script as
well):

- Use the *fill with terrain type*
- Select `Rocky` (custom terrain)
- Apply *at or above* 64
- Apply *above* 45 degrees

Apply the snow layers:

- In *Tools*, select *Run Script*
- Use LordDakr's MountainFrost script (as [linked in his YouTube
  tutorial](https://www.youtube.com/watch?v=IK4gcobBBO0)).
- Set the first parameter to 200.

