---
layout: default
title: Dimension Properties
parent: WorldPainter
nav_order: 2
---
# Dimension Properties
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

With the *Dimension Properties* I prepare world generation.

# General

In the *General* tab, I want the following settings at least:

- *Underground material* should be set to `Resources` so it matches the
  resource layers identified in the other tab (which provides a Minecraft
  alike generation).

# Theme

The *Theme* tab is the most important one for quickly generating the right
terrain.

On the *Terrain* tab, I use the following layers:

1. From level 0, I use `Gravel`
2. From level 62, I use `Sand`
3. From level 66, I use `Bare Grass` or `Grass`
4. From level 120, I use `Rocky` (custom terrain)
5. From level 150, I use `RockyMountain` (custom terrain)
6. From level 200, I use `Deep Snow`

On the *Layers* tab, delete the default `Frost` layer as a custom script will
be used for this.

# Caves, Caverns and Chasms

In the *Caves, Caverns and Chasms* the following should be activated:

- *Caves everywhere* with the setting in the middle
- *Chasms everywhere* with the setting in the middle
