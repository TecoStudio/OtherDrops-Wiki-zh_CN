This page explains aliases, an advanced YAML technique which can save you from having to repeat the same Parameters or groups of parameters in your drops file. Aliases are typically defined in the aliases: section of a drops file, though they can, in fact, be defined anywhere.

YAML allows you to use an advanced tool called "aliases". These tricks work in any config file that's written in YAML.

Aliases allow you to define a string/list/number or even a whole block of data, give it a name and recall it later with just that name. You can even modify sub-sections of the data when recalling the alias.

Some examples follow:
## Simple Example
```
aliases:
    # example of an alias that defines just a single piece of data
    - &environ [DAMAGE_ENTITY_EXPLOSION, DAMAGE_FIRE,  DAMAGE_CONTACT, DAMAGE_DROWNING, DAMAGE_FALL, DAMAGE_SUFFOCATION]

    # example of an alias that defines a block of data, using the previously defined alias
    - &environDropNothing
      tool: *environ
      drop: NOTHING
      exclusive: 1 # this means that if this drop occurs - none of the others will, unless they have the same number


otherblocks:
    CREATURE_ZOMBIE:
        - &environDropNothing  # stop mob farming - no environmental drops

        # continue with any other custom drops....

```
## Modifying alias contents
The following example is designed to allow you to easily copy a similar config between different blocks whilst modifying a section of the alias. Note the use of <:: (a "merge key") as this is what allows you to modify the alias.
```
aliases:
        - &damageall
          tool: ALL
          drop: AIR
          damageattacker: 1

        - &dropnothing
          tool: ALL
          drop: NOTHING
          chance: 100

        - &defaultdroplow  # this alias has a low chance of dropping default item
          tool: ALL
          drop: DEFAULT
          chance: 5

        - &specitem  # this alias is being used specifically for overwriting the "tool" condition later
          tool: ALL
          drop: DEFAULT
          chance: 100
          exclusive: 1

otherblocks:
#stones
    STONE:
        - *dropnothing
        - *damageall
        - *defaultdroplow
        - <<: *specitem
          tool: ANY_PICKAXE

    DIRT:
        - *dropnothing
        - *damageall
        - *defaultdroplow
        - <<: *specitem
          tool: ANY_SPADE
```
## Defining aliases from modified aliases
Again a more advanced example. Pay attention to how `&specitem-pick` is defined from a modification of the `&specitem` alias.
```
    # original example by enelar
    ALIASES:

    #1) With fingers - damage attacker, nothing changed with block. (&damageall)
    #2) On wrong tool - nothing changed with block. (&wrongtool)
    #3) On pickaxe, each race individual chance to drop, always drops cobblestone.
    #4) Kill player else. (Broken with dirt, sand, fish, seeds, etc) (&atata)

        - &wrongtool
          tool: ANY
          drop: DENY
          exclusive: wrong
        - &atata
          damageattacker: 20
          tool: ANY
          drop: NOTHING
          toolexcept: [ANY_SPADE, ANY_AXE, ANY_HOE, ANY_PICKAXE]
          replacementblock: DEFAULT
          message: "WTF! Wrong item... Non RP playing..."
          exclusive: atata
        - &damageall
          tool: ALL
          drop: AIR
          replacementblock: DEFAULT
          message: "Oh, my fingers!"
          damageattacker: 1
        - &defaultdroplow
          tool: ALL
          drop: DEFAULT
          chance: 5
        - &specitem
          tool: ALL
          drop: DEFAULT
          chance: 100
          exclusive: 1
        - &dropstone
          tool: ANY_PICKAXE
          drop: COBBLESTONE
          exclusive: 1

    COAL_ORE:
        - <<: *wrongtool
          toolexcept: ANY_PICKAXE
        - <<: *damageall
          damageattacker: 8
        - <<: *atata
        - <<: *dropstone
        - &specitem-pick 
          <<: *specitem
          tool: ANY_PICKAXE
          chance: 40
          permissions: race_a.COAL_ORE
        - <<: *specitem-pick
          chance: 60
          permissions: race_h.COAL_ORE
        - <<: *specitem-pick
          chance: 60
          permissions: race_t.COAL_ORE
        - <<: *specitem-pick
          chance: 5
          permissions: race_r.COAL_ORE
```
If you missed it here is the specific part defining `&specitem-pick`:
```
        - &specitem-pick # note: this alias name must be on it's own line
          <<: *specitem  # remember, <<: allows you to modify the alias
          tool: ANY_PICKAXE # change tool from &specitem's ALL value to ANY_PICKAXE
```
## Use with DropGroups
Aliases can also be used with DropGroups to create more complex aliases.
```
aliases:
  - &map_and_compass
    dropgroup: mapcompass
    chance: 0.01%
    drops:
      - drop: MAP
      - drop: COMPASS

otherblocks:
  SAND:
    - *map_and_compass
```
This likely has more practical applications (as you probably wouldn't want to define the mapcompass drop more than once). I might improve this example later with a more practical example if I think of one.
