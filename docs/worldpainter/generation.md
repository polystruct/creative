---
layout: default
title: Generation
parent: WorldPainter
nav_order: 1
---
# Generating World
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Initial generation

Automatically getting awsome terrain requires generating heightmaps using tools
like Gaea or World Machine. These are however commercial products (although
limited use non-commercial is possible as well, for instance World Machine provides
all the capabilities but limits the size to around 1024x1024). However, I prefer
to use [Azgaar's Fantasy Map Generator](https://azgaar.github.io/Fantasy-Map-Generator/).

## Azgaar's Fantasy Map Generator

This online tool is free and open source. It also has the capability to generate
heightmaps, but these are not as nice-looking as they are intended for general,
full world representations. But it has a few features that I like to combine
with World Painter:

- It generates biomes, which I can export as image to use as a mask in World
  Painter.
- It places rivers, which I can use as a reference
- It places landmarks and cities/villages, which I can use as a reference
  to populate the world

Before generating a world through AFMG, go to *Options* and set the *Canvas
size* to the size of the Minecraft world you want to generate. Then, generate a
new world.  While you might not be able to view the entire world through AFMG
(there is no "zoom out" option that I know of), you can generate it completely
later.

Next, we generate the necessary views...

### Heightmap

The first part is the heightmap. Select heightmap in the tool, and deselect
all other options (like rivers). Then, in the *Styles* menu:

- select *Monochrome* for style preset
- select *Coastline* and write down the color value (usually `1F3846`). Set
  the opacity then to 0. Without this setting, the coastline will generate
  with an abrupt wall.
- select *Ocean* element and set the color to the previously written down
  value (or clear it out completely and fit later in WorldPainter). We want 
  the ocean to be relatively flat in the output so that we can easily adjust
  this in World Painter later.
- select *Landmass* element and set the fill to the previously written down
  value. Again, this is to make sure we do not get abrupt walls as edges.
- select *Lakes* element and set the *Opacity* to 0 for each lake type.
- select *Heightmap* element and set *Reduce layers* to 0, and *Filter* to
  *Blur 5* or *Blur 7*.

The blurring reduces the terracing you get, but also makes the generated
landscape less interesting (more boring) so requires a bit more work in
World Painter.

To export the heightmap, export as SVG. Then, convert the SVG to a PNG file.
For instance, with Inkscape:

```
~$ inkscape heightmap.svg -o heightmap.png
```

### Rivers

Next, I export the rivers. Now, this will not be a mask that we can immediately
convert into a river, but it gives a rough feeling where to place rivers. 

- Make sure only rivers are shown.
- Go to *Style* and switch the *Style preset* to something else
  than `Monochrome`, and then set it back to `Monochrome`.
- In *Select elements*, select `Rivers`.
  - Set *Opacity* to `1`
  - Set *Fill* to white
  - Set *Filter* to `None`
- In *Select elements*, select `Ocean`.
  - Set *Color* to black
  - Set *Pattern* to `No pattern`

Export as SVG, then convert to PNG. Next, make sure that the resulting
PNG only has white or black:

```
~$ convert <source> -threshold %1 <destination> 
```

### Biomes

Next, I export the biomes as a color map. This cannot always be used as
a mask though, as the number of annotation colors in WorldPainter is
not matching the number of biomes that can be generated. But for a quick,
first-pass biome allocation, this works just fine.

- In *Layers*, select `Biomes map`, and make sure only `Biomes` are
  rendered.
- In *Style*, use `default` as *Style preset*
- For the `Ocean` element
  - Set *Pattern opacity* to `0`
  - Set *Color* to black

When trying to generate masks, try to limit the number of colors:

```
~$ convert <source> -posterize 3 <target>
````

With ImageMagick, counting the number of colors is done like so:

```
~$ identify -format "%k" <source>
```

You can also remap colors to the colors in another image. I have an
image that contains the 15 annotation colors:

```
~$ convert <source> -dither None -remap worldpainter_colormap.gif <target>
```

However, I have not yet found a way to force a remapping even when
the target color is not close to the source.

## Other

Other exports can be made as well. I recommend to have each item as a
separate export, as that might occasionally result in usable masks.

For instance, you can select the routes (and remove trails) and export
for a mask, allowing to easily generate roads on the map. 

# World Painter

When loading the map in World Painter, an important aspect is to keep
away from terrain materials as long as possible, and instead use 
biomes and annotations.

But before this is done, let's first load the map from the heightmap.

## Heightmap

Use *Import new world* and then *from heightmap*.

I tend to use a custom world height, from -128 to 320. The water level
is then set at 0. To load the heightmap itself, I generally map the
highest value of the heightmap to around 120. This gives me leeway to
generate the mountains, hills and plateaus through WorldPainter, and
also reduces the number of artefacts that are loaded in from the
heightmap.

The mapping for the lowest level is somewhat done on sight, making sure
that the beach gets at the right level.


To regenerate the world, following the next steps can be used manually. 

{: .note }
I use a script to apply this (`polystruct-AutoRegenerate.js`).

First, use the default theme generation (`Ctrl+G`, and select *reset terrain and
layers to theme*).

Then apply the `Hills` custom terrain:

- Use *fill with terrain type*
- Select `Hills` (custom terrain)
- Apply *at or above* 1
- Apply *at or below* 90
- Apply *above* 35 degrees
- Do not apply feathering as it will corrupt beaches and ocean edges.

Apply the `Rocky` custom terrain:

- Use the *fill with terrain type*
- Select `Rocky` (custom terrain)
- Apply *at or above* 1
- Apply *at or below* 140
- Apply *above* 45 degrees

Apply the snow layers:

- In *Tools*, select *Run Script*
- Use LordDakr's MountainFrost script (as [linked in his YouTube
  tutorial](https://www.youtube.com/watch?v=IK4gcobBBO0)).
- Set the first parameter to 120.

