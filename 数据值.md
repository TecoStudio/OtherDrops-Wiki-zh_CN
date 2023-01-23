There are two places you can specify an additional data value:

1. In the drop:
```
otherdrops:
    SAND:
        - tool: ALL
          drop: WOOL@RED
```

2. In the original block specifier:
```
otherdrops:
    WOOL@RED:
        - tool: ALL
          drop: DIRT
```

The data values you are allowed to use depends on which block you are tying the data value to. Note that, if not listed here, you can always use the raw data values as given in the Minecraft wiki (e.g. WOOL@14 and WOOL@RED give the same result).

## WOOL, DYE, INK_SACK & CREATURE_SHEEP
* WHITE
* ORANGE
* MAGENTA
* LIGHT_BLUE
* YELLOW
* LIME
* PINK
* GRAY
* SILVER
* CYAN
* PURPLE
* BLUE
* BROWN
* GREEN
* RED
* BLACK

## LOG, LEAVES, WOOD_STEP, and WOOD_DOUBLE_STEP
* GENERIC - Represents the common (Oak) tree
* ACACIA - Represents the Acacia tree
* BIRCH	- Represents the Birch tree
* DARK_OAK - Represents the Dark Oak tree
* JUNGLE - Represents the Jungle tree
* REDWOOD - Represents the Darker Barked tree

## COAL
* COAL
* CHARCOAL

## CROPS
* SEEDED
* GERMINATED
* VERY_SMALL
* SMALL
* MEDIUM
* TALL
* VERY_TALL
* RIPE

## STEP and DOUBLE_STEP
* STONE
* SANDSTONE
* COBBLESTONE
* BRICK
* SMOOTH_BRICK
* NETHER_BRICK
* QUARTZ (Implemented in 3.2.6)

## STONE_SLAB2 and DOUBLE_STONE_SLAB2
* RED_SANDSTONE (Implemented in 3.2.6)

## MAP
Just use the number of the map required.  Map number is shown in the name (eg. Map #9).

## CREATURES
* Refer to the [[Creature|Creatures]] Page