# Where do I put the configs?
Before we get into the examples you need to know where they go. Any of these entries can be placed at the bottom of the "otherdrops-drops.yml" file.

## Simple Drop
A standard drop can be defined with:

```target: thing_to_drop[/quantity][/chance%]```

More information about the "things to drop" can be found here (_Entity list Wiki under construction_).
## Examples:
```
  glass:       thin_glass       # glass drops thin glass
  diamond_ore: diamond/2/5%     # 5% chance of 2 diamonds from diamond_ore
  zombie:      diamond/1-3/1%   # zombie has 1% chance of dropping between 1 & 3 diamonds
```
## Lists
You can also use a list of items, like such:
```
  zombie:   [default, iron_ingot/1/10%, diamond/1/0.5%]
  grass:    [default, brown_mushroom/1/5%, red_mushroom/1/8%]
```
In the example above the Zombie starts with the default drop and adds a 10% chance of dropping an iron ingot plus 0.5% chance of dropping a diamond. The grass always drops default (eg. dirt) and has a 5% chance of dropping an brown mushroom (in addition to default) and a 8% chance of dropping a red mushroom.

Note that the square brackets `[]` mean "drop this AND this AND this" so there's a chance of all three items for the grass to drop (dirt, brown mushroom & red mushroom). If you only want one of the items to drop you can use curly bracks `{}` which mean "drop this OR this OR this".
```
  zombie:   {iron_ingot/1/10%, diamond/1/0.5%}
  grass:    {brown_mushroom/1/5%, red_mushroom/1/8%}
```
You don't need to specify `default` in this instance because if neither of the items drops then it falls back to the default drop. More details about multiple drops can be found here (_Drops Wiki under construction_).

## Long format
Using the longer format allows you to add new parameters such as conditions(time, biome, world, permissions, etc) and actions(messages, damage, consumetool, etc). Writing the grass example from above in a long format you could say drop brown mushrooms at night only and red mushrooms during the day.
```
  grass:
  - drop: brown_mushroom/1
    chance: 5%
    time: darkness   # covers dusk, night and dawn

  - drop: red_mushroom/1
    chance: 8%
    time: day
```
## Adding messages
```
  ghast:
  - drop: diamond/1-4
    chance: 1%
    message: "That ghast seems to have swallowed a jewellery box."
```
Keep in mind with a long format drop that the "item chance" - eg. `diamond/1-4/1%` - only applies to the drop. Unless you specify a "chance" parameter (as per the `chance: 1%` above), then other parameters (such as "message" above) will be at always show (ie. 100% chance).

