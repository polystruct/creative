---
layout: default
title: Processors
parent: Data pack
nav_order: 4
---

Processors allow for modifying structures. This is used to use generic builds,
which are then customized through the processors for whatever purpose they
have.

# Block matching processors

The most common approaches used for processors is to match blocks and then
change them to other blocks. This could be to simulate decay, or switch a
build from using `oak_planks` to `spruce_planks`.

Some of the more obscure supported processors are somewhat harder to find
information about online though.

## Changing NBT

It is possible to change the NBT of a block. This can be used to change the
loot table of a chest:

```
{
  "processors": [
    {
      "processor_type": "minecraft:rule",
      "rules": [
        {
          "input_predicate": {
            "predicate_type": "block_match",
            "block": "minecraft:chest"
          },
          "location_predicate": {
            "predicate_type": "always_true"
          },
          "output_state": {
            "Name": "minecraft:chest"
          },
          "output_nbt": "{LootTable:\"polystruct:chests/fishing_ruin\"}"
        }
      ]
    }
  ]
}
```

{: .note }
In the above example, the `LootTable` is escaped. There are example datapacks
online where no escaping is done, so this might be supported nowadays.

By modifying the NBT, you can add in hidden treasures in blocks that users don't
immediately associate with it. For instance, the NBT for a blast furnace
could be set as containing a bundle, which contains 3 diamonds and 15 charcoal:

```
{Items:[
  {Slot:1, id:"minecraft:bundle", tag:{Items:[
    {id:"minecraft:diamond", Count:3b},
    {id:"minecraft:charcoal", Count:15b}
   ]},Count:1}
]}
```
