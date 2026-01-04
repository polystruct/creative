---
layout: default
title: Development
parent: Home
nav_order: 1
---
# Development
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

This page covers bugs I have either in my datapack that I deliberately put on
the backlog for future, or bugs from Minecraft itself that I need to keep an
eye out for.

# Minecraft Bugs

During development, when placing structures using the `/place` command, the
jigasaws will not connect correctly: they might generate one block too low, and
with a random direction. This is covered by
[MC-252801](https://bugs.mojang.com/browse/MC/issues/MC-252801) and only
affects the placement through the command. Generation through the data pack
(worldgen) is not affected (if you think it is, make sure there are no
overlapping placements, e.g. a villager jigsaw and interior).



