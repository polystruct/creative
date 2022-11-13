---
layout: default
title: Dimension Properties
parent: WorldPainter
nav_order: 2
---

With the *Dimension Properties* we can prepare world generation.

# General

In the *General* tab, we want the following settings at least:

- *Underground material* should be set to `Resources` so it matches the
  resource layers identified in the other tab (which provides a Minecraft
  alike generation).

# Theme

The *Theme* tab is the most important one for quickly generating the right
terrain.

On the *Terrain* tab, we use the following layers:

1. From level 0, we use `Gravel`
2. From level 62, we use `Sand`
3. From level 66, we use `Bare Grass` or `Grass`
4. From level 120, we use `Rocky` (custom terrain)
5. From level 150, we use `RockyMountain` (custom terrain)
6. From level 200, we use `Deep Snow`

On the *Layers* tab, delete the default `Frost` layer as a custom script will
be used for this.

# Caves, Caverns and Chasms

In the *Caves, Caverns and Chasms* the following should be activated:

- *Caves everywhere* with the setting in the middle
- *Chasms everywhere* with the setting in the middle
