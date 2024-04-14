---
layout: default
title: General
parent: Commands
nav_order: 1
---

{: .note }
This is a placeholder for now

# Exploration maps

It is possible to generate custom exploration maps. The main approach is to
use loot tables, where you provide a `minecraft:map` and then use the the
`minecraft:exploration_map` function to modify it accordingly.

For instance:

```
{
  "type": "minecraft:chest",
  "pools": [
    { 
      "rolls": { "type": "minecraft:uniform", "min": 1, "max": 1 },
      "entries": [ {
        "type": "item",
        "name": "minecraft:map",
        "weight": 1,
        "functions": [ {
          "function": "minecraft:exploration_map",
          "destination": "polygame:village",
          "decoration": "red_x",
          "zoom": 2,
          "skip_existing_chunks": false
        } ]
      } ]
    }
  ]
}
```

{: .important }
The target of the `destination` field **must be a tag**, not an actual
structure. See [MC-249449](https://bugs.mojang.com/browse/MC-249449).


