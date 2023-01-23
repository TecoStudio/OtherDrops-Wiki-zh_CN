# ![OtherDrops](https://i.imgur.com/Ep0hdRz.png)
Welcome to the OtherDrops wiki! OtherDrops is a plugin for the Minecraft Spigot API that lets you change what mobs and blocks drop when they die or are broken. It is very flexible, but out of the box does nothing. Please read the rest of this page to understand how to configure OtherDrops to do what you want.

For the latest download, see the Spigot resource: <https://www.spigotmc.org/resources/otherdrops-updated.51793/>

Config Examples and Ideas (Coming soon) - Ideas and Ways to achieve specific functionality 

[[Material and Creature Values|Creature and Material List]] - Block, item, creature and tool values

[[Color and Data Values|Data Values]] - A list of valid color or data values


# Installing and Configuring

1. Stop the server.
2. If you have already installed it before, save a copy of your current OtherDrops folder, and delete the old otherdrops-config.yml file in the original.
3. Delete the old jar (if applicable) and copy this jar in place of it.
    * If you are using 1.13, use OtherDrops1.13-3.2.6.jar
    * If you are using a version below 1.13 (1.11-1.12), use OtherDropsLegacy-3.2.6.jar
4. Restart the server and the new configuration file should be generated. You can view the entire config as a whole here.
5. Modify the config to your liking, and run /odr to update the config.
6. Report bugs to GitHub.
 
Out of the box, OtherDrops does nothing. To make it do what you want, edit the file **plugins/OtherDrops/otherdrops-drops.yml**. Example files are supplied and can be enabled simply by un-commenting them (removing the ```#```).  Additional custom configuration can be included at the bottom of the global file or you can add your own files.  Drop parameters are details further down this page.

```
include-files: 
##########
# The plugin will scan through and load these files after loading the main config below.
# Note: drops from included files will are inclusive and will all be added to the drop list.
##########
#  - includes/od-fix_undroppables.yml    # fix glass, bookshelf, boat and stairs drops
#  - includes/od-goldtools-basic.yml     # allow gold tools chance to get ice, glowstone and grass
#  - includes/od-goldtools-smelt.yml     # gold-pickaxe smelts ores to ingots, sand to glass, etc
#  - includes/od-ore_extrtrigger.yml      # allow ores to be "extracted" - leaving behind the stone
#  - includes/od-leaf_overhaul.yml       # overhaul leaf drops (apples, cocoa beans, leaves, sticks & a very small chance of golden apple)
#  - includes/od-playerdeath_zombie.yml  # players drop zombies on death
#  - includes/od-undead_chaos.yml        # the undead shall rise again! Includes players dropping zombies/skeletons
#  - includes/od-random_examples.yml     # For crazy testing only :) Read through examples before activating.
#  - includes/od-dyewool.yml             # Dye wool after placing!
#  - includes/od-stop_mob_farms.yml      # Stop mob farming!

## Other users overhauls
#  - includes/overhaul-catballs.yml     # great example/playable config from Catballs (disable "ob" configs before using this one, otherwise you might have too many drops)
#  - includes/overhaul-zarius.yml       # Zar's messy config (I run this with no other includes, at the moment)
    
## Add your files here (alternatively just add your custom drops to the bottom of this file)
#  - my_custom_file1.yml
```

# Customised configs
Here is an example that goes through it step-by-step:

```yaml
otherdrops:
    SAND:
        - tool: GOLD_SPADE
          drop: GLASS
        - tool: DIAMOND_SPADE
          drop: GLOWSTONE
          chance: 50
    COAL_ORE:
        - tool: [GOLD_PICKAXE, DIAMOND_PICKAXE]
          drop: NETHERRACK
          quantity: 2-4
    LEAVES@BIRCH:
        - tool: ALL
          drop: APPLE
          chance: 5
    CREATURE_CREEPER:
        - tool: DIAMOND_SWORD
          drop: DIAMOND
          world: creeperworld
    SPECIAL_LEAFDECAY:
        - drop: APPLE
          chance: 10
```
- "**otherdrops:**" starts the main block of substitutions. Note that from this point on, every line is indented by **at least four spaces, _not tabs_**


  - The first is for when you break a _sand_ block:
    - If you break it with a _gold spade_, you always get _glass_
    - If you break it with a _diamond shovel_, you get _glowstone_ 50% of the time, otherwise sand.
    - The rest of the time, it always drops sand.

  - The second shows the list syntax and how to have a randomized drop quantity. If you break _coal ore_ with either a _diamond_ or _gold pickaxe_, you get between two and four _netherrack_ blocks.

  - The third shows the "all" keyword, and how to select the original block data type. Birch tree leaves drop apples 5% of the time, regardless of tool. Leaves from other trees do not change their behaviour.

  - The fourth shows a mob drop and the multiworld option. If you kill a creeper, with a diamond sword, in the world called "_creeperworld_", it drops a diamond.

  - The final shows the special "leaf decay" event. Leaves decaying drop an apple 10% of the time - less than if you break by hand, in this example.

# All config parameters
Here is a summarised list of parameters: 

Conditions: tool, toolexcept, quantity, chance, worlds, weather, biomes, time, height, permissions, permissiongroups, exclusive, attackrange, regions.

Actions: drop, color, event, message, damagetool, damageattacker, delay, runcommands.


For full usage details see: Configuration Parameters (Coming soon)

# ![Core Features](https://i.imgur.com/ACRducI.png)

* Drop anything!*
* Use triggers such as block break, combat, fishing & more
* Conditions to fine-tune your drops such as tool, world, regions, weather, permissions & more
* Add actions including damage, healing, messages, potion effects & more
* Easy syntax allows you to quickly customize drops & rewards for your server
* Future Support
  * Where-ever possible the official Bukkit lists are used so OtherDrops supports all current and future:
blocks, items, mobs, enchantments, potion effects, biomes, spawn reasons, tree, villager professions, cat & skeleton types
* Support for special item data:
  * Custom names & lore text
  * Enchanted weapons & armour (or add random enchantments)
  * Enchant anything with unlimited levels (dirt with level 30 damage?)
  * Enchanted books with any enchantment
  * Written books (wtih custom title/author/pages)
  * Leather armour colors
  * Custom fireworks colors
  * Skull types & custom player heads
* Support for special mob data:
  * Custom names, HP (health) & equipment for any mob
  * Baby animals (all "Ageable" mobs - chicken, cow, pig, zombie etc)
  * Tame wolves (including collar color) or cats (& different cat types)
  * Sheep colors (and sheared/unsheared)
  * Villager professions, villager zombies, powered creepers & agressive level for pig-zombies
  * Wither skeletons, Slime & lava-slimes of any size
* Economy support (via Vault)
  * Support for all major economy plugins (see Vault project page)
  * Players can gain, lose or steal money based on fixed amount or percentage
  * Compatible with "MoneyDrop" to drop physical money items.
# ![Conditions](https://i.imgur.com/N1uRWTz.png)
* Multi-world support - create separate files to handle each world
* Add super rare drops with chance values down to 0.000000001%
* Specify tools required (or a list of tools eg. [any sword, -diamond sword])
* Lorename, Heroes (class & level) conditions
* Cooldowns
# ![Actions](https://i.imgur.com/iNVU6TE.png)
* Apply actions alongside the drop (or even without a drop)
* Damage tools and/or consume items (eg. use dyes to color wool)
* Damage or heal the victim, player or even the whole world
* Apply potion effects to the victim, player, radius, world or server
* Display custom messages (or a list of messages with one selected at random)
* Create explosions, lightning, visual effects (including particles), sound effects
* Run commands
# ![Ideas](https://i.imgur.com/jrgCIDE.png)
* Give leaves various chances of dropping apples, sticks, cocoa beans, saplings, etc on break and/or leaf decay.
* Make glass, stairs, and boats reclaimable (can be tool-specific if you wish).
* Allow gold and iron to be mined directly into ingots with a golden pickaxe.
* Allow users to right-click on cobblestone with vines in hand to turn the cobblestone mossy.
* Nerf mob traps by disabling drops from environmental damage.
* Unleash the zombie apocalypse by setting zombies to drop zombies when they die! (This can be world-specific.)
* Make mobs that don't normally spawn naturally spawn.
* Make mob spawning, drops, and events biome specific!
# ![Contact Me](https://i.imgur.com/p3KBhhv.png)
If you have a problem please create a ticket (on [GitHub](https://github.com/CoolLord22/OtherDrops/issues/new/choose)) and include the error (if there was one). 
To receive support, report bugs, get information on updates, test out beta updates, and so much more, join our [Discord](https://discord.gg/eHBxk5q).
***
_*from Bukkit - if it doesn't, let me know_