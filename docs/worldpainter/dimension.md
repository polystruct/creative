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

1. From level -64, I use `Deepslate`
2. From level -20, I use `Gravel`
3. From level -2, I use `Sand`
4. From level 1, I use `Bare Grass` or `Grass`
4. From level 90, I use `Rocky` (custom terrain)
5. From level 140, I use `RockyMountain` (custom terrain)
6. From level 250, I use `Deep Snow`

On the *Layers* tab, delete the default `Frost` layer as a custom script will
be used for this.

# Caves, Caverns and Chasms

In the *Caves, Caverns and Chasms* the following should be activated:

- *Caves everywhere* with the setting at position 3
- *Chasms everywhere* with the setting at position 3
