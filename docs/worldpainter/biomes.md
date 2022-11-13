---
layout: default
title: Biomes
parent: WorldPainter
nav_order: 5
---

# Swamps

To generate a swamp-alike biome, use the spray to generate the water using
the (custom) *River* layer, making sure the water is sufficiently connected.

Next, apply the ground cover on this *River* layer. While you can use the
`River Terrain` other cover can be chosen as well if it doesn't fit the swamp
design.

To add water plants, create another custom terrain which contains the water
plants as well as regular water. Then create a layer using the newly created
custom terrain, with thickness set to -1, and apply that to the *River* layer.

# Deserts

To make better-looking deserts, have height difference around 25 across the
desert. Use slopes between 15 and 30 degrees.
