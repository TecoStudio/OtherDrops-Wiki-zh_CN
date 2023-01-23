This page contains a list of all creatures which can be referenced by name in OtherDrops. Creatures can be referenced in parameters in several ways:
- If you use a creature as a drop, that creature is spawned on the spot.
- If you use a creature as an object, you can set what the creature drops upon death or when a player clicks on it.
- If you use a creature as a tool, you can restrict a drop such that it must have been triggered by that creature (for instance, requiring a pig to be killed by a zombie would use ZOMBIE as the tool).

Note that all creature names (including group synonyms) optionally accept a space in place of an underscore. Creature names can also be prefaced with "CREATURE_", which _could_ come in handy if a future block/item name ever overlapped with a creature name.

The plugin generally functions extremely well. However, in some cases, incorrectly interprets the separator. If you are having any issues with OtherDrops detecting a mob, please try swapping the separator. If you are using `!` attempt `!!` and if you are using `!!` attempt `!`

To reduce the overall length of this Wiki page, it has been sectioned off into spoilers. You can easily open the container which you need, and view the contents.

<details>
<summary> <b>Creature List</b> </summary>
<p>

This list provides all of the possible creatures you can use. 
* For an updated list of 1.13 entities, refer to the [Spigot EntityTypes](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html).
* BAT
* BLAZE
* CAVE_SPIDER
* CHICKEN (ENTITY_CHICKEN for 1.13+)
* COW
* CREEPER
* DONKEY
* ELDER_GUARDIAN
* ENDERMAN
* ENDERMITE
* ENDER_DRAGON
* ENTITY_ENDER_CRYSTAL
* EVOKER
* EVOKER_FANGS
* EXPERIENCE_ORB
* GHAST
* GIANT
* GUARDIAN
* HORSE
* HUSK
* ILLUSIONER
* IRON_GOLEM
* LLAMA
* MAGMA_CUBE
* MULE
* MUSHROOM_COW
* OCELOT
* PARROT
* PIG
* PIG_ZOMBIE
* POLAR_BEAR
* RABBIT
* SHEEP
* SHULKER
* SILVERFISH
* SKELETON
* SKELETON_HORSE
* SLIME
* SNOWMAN
* SPIDER
* SQUID
* STRAY
* VEX
* VILLAGER
* VINDICATOR
* WITCH
* WITHER
* WITHER_SKELETON
* WOLF
* ZOMBIE
* ZOMBIE_HORSE
* ZOMBIE_VILLAGER
</p></details>

***
<details>
<summary> <b>Creature Groups</b> </summary>
<p>

The creature group can be used to refer to all of the mobs inside the group, rather than individually defining each mob. If you have any suggestions for these mob groups (this includes things you feel should be added or removed from the groups), please create a [Ticket](https://github.com/CoolLord22/OtherDrops/issues)!

* `CREATURE_HOSTILE` includes Blaze, Creeper, Elder Guardian, Endermite, Evoker, Ghast, Guardian, Husk, Magma Cube, Silverfish, Skeleton, Slime, Stray, Vex, Vindicator, Witch, Wither Skeleton, Zombie, and Zombie Villager.
* `CREATURE_FRIENDLY` includes Bat, Chicken, Cow, Mushroom Cow, Pig, Rabbit, Sheep, Squid, Donkey, Mule, Horse, Parrot, and Ocelot.
* `CREATURE_NEUTRAL` includes Enderman, Llama, Polar Bear, Wolf, and Zombie Pigman
* `CREATURE_ANIMAL` includes Bat, Chicken, Cow, Donkey, Mule, Mushroom Cow, Horse, Parrot, Pig, Polar Bear, Rabbit, Sheep, Squid, Ocelot, and Wolf.
* `CREATURE_UNDEAD` includes Enderman, Husk, Skeleton, Stray, Zombie, Zombie Pigman, and Zombie Villager. 
* `CREATURE_BUG` includes Cave Spider, Endermite, Silverfish, and Spider.
* `CREATURE_WATER` includes Elder Guardian, Guardian, and Squid.

You can also use the creature group synonyms as a drop. It can be prefaced with a carat (^) to force OtherDrops to spawn **every** applicable creature rather than just picking one. 
For example, using ```^CREATURE_FRIENDLY``` would spawn all of the Friendly mobs, rather than just picking 1 mob to spawn when the ```^``` isn't specified.

</p>
</details>

*** 
<details>
<summary> <b>Data Values</b> </summary>
<p>

Some creatures also support data values. All creatures that support data values also support the "@NORMAL" data value. This specifies that only the normal variant of a mob is affected. This is because specifying only the mob-name, like "CHICKEN", will apply to all chickens regardless of their attributes (whether they're a baby or not).
<details>
<summary>Cow, Chicken, and Mushroom Cow </summary>
<p>

   * BABY
   * ADULT
</p>
</details>
<details>
<summary>Creeper </summary><p>

   * UNPOWERED (Default)
   * POWERED</p></details>
<details><summary>Enderman </summary><p>

   * An Enderman's data value refers to the block type it's carrying (i.e. `ENDERMAN@DIRT`). 
   * A dying Enderman can be forced to drop the block it's carrying by adding the parameter `drop: CONTENTS`</p></details>
<details><summary>Husk, Zombie, and Zombie Villager</summary><p>

* BABY
* ADULT</p></details>
<details>
<summary>Horse </summary><p>

   1. Styles:
      * STYLE_NONE 
      * STYLE_BLACK_DOTS 
      * STYLE_WHITE_DOTS 
      * STYLE_WHITE 
      * STYLE_WHITEFIELD 
   2. Colors:
      * COLOR_WHITE 
      * COLOR_CREAMY 
      * COLOR_CHESTNUT 
      * COLOR_BROWN
      * COLOR_BLACK 
      * COLOR_GRAY 
      * COLOR_DARK_BROWN 
   3. Data:
      * ADULT
      * BABY
      * TAMED
      * UNTAMED
   * The format for a horse is ```HORSE@!<color>!<style>!<data>``` For example: ```HORSE@!COLOR_WHITE!STYLE_BLACK_DOTS!ADULT!TAMED``` Selects any tamed, adult Horse which is white with black dots. Please realize that if you want to specify a color you must use `!COLOR_<color>` and if you want to specify a style you must use `!STYLE_<style>` This is because there is both a `WHITE` color, and a `WHITE` style.</p></details>

<details><summary>Pig</summary><p>

* UNSADDLED (default)
* SADDLED 
* ADULT
* BABY </p></details>

<details><summary>Rabbit</summary><p>

   1. Types:
      * TYPE_BLACK
      * TYPE_BLACK_AND_WHITE
      * TYPE_BROWN
      * TYPE_GOLD
      * TYPE_SALT_AND_PEPPER
      * TYPE_THE_KILLER_BUNNY
      * TYPE_WHITE
   2. Data:
      * ADULT
      * BABY
 </p></details>

<details><summary>Sheep</summary><p>

* UNSHEARED
* SHEARED
* BABY
* ADULT
* Use SHEEP@!COLOR to specify the color of the sheep. Possible colors are: WHITE, ORANGE, MAGENTA, LIGHT_BLUE, YELLOW, LIME, PINK, GRAY, SILVER, CYAN, PURPLE, BLUE, BROWN, GREEN, RED, BLACK. 
* Sheep data is a bit different from most mobs. To specify **any** data, you must use the `!` ```SHEEP@SHEARED``` won't work because it needs to be ```SHEEP@!SHEARED``` 
* To specify all three flags, you can use something like this: ```SHEEP@!BLUE!SHEARED!ADULT``` to specify an adult sheep, that has been dyed blue, and has no wool on it. If you specify a BABY sheep, but set it as SHEARED, the plugin will ignore your request since baby sheep cannot be sheared. </p></details>
<details><summary>Slime/Magma Cube</summary><p>

* TINY (size: 1)
* SMALL (size: 2)
* LARGE (size: 4)
* HUGE (size: 8; does not spawn naturally)
* An integer (1-32) can also be specified instead.</p></details>

<details><summary>Wolf</summary><p>

* Neutral (default)
* Tamed
* Angry </p></details>
<details><summary>Villager</summary><p>

* FARMER (default)
* BUTCHER
* LIBRARIAN
* PRIEST
* BLACKSMITH
* BABY
* You can combine BABY with any other type using the syntax: VILLAGER@BUTCHER!BABY </p></details>
<details><summary>Zombie Pigman</summary><p>

* BABY
* ADULT
* A zombie pigman's data value is an integer which determines how long it will remain angry (0 makes it neutral).</p></details>
<details><summary>Mule, Donkey, Skeleton Horse, and Zombie Horse</summary><p>

* BABY
* ADULT
* TAMED
* UNTAMED
* These 4 mobs utilize the same data. To specify a tamed, adult Skeleton Horse, use `SKELETON_HORSE@!TAMED!ADULT`

</p></details>

####
Because I attempted to fix various data for newer mobs, the plugin will sometimes incorrectly interpret the separator ( `!` vs `!!` ) for some mobs. For example, one mob may require `!!` to work, whereas another requires just `!` This bug **cannot** be patched. If you are having any issues with detecting the mob, please try swapping the separator. If you are using `!` attempt `!!` and vice versa.
</p></details>

***

<details><summary><b>Mob Equipment</b></summary><p>

You can also specify equipment on mobs, as long as they're able to equip them. Mobs that can carry equipment in vanilla Minecraft are zombies, zombie pigmen, strays, husks, witches, vindicators, vexes, illusioner, wither skeletons, and skeletons.

The format for specifying equipment on mobs follows below. Note that equipped mobs can both be specified as an object and as a drop.
```
MOBNAME@eq:{slot}:{material}@{data}\!{enchantment}#{ench level}%{dropchance}!!{next slot...}
```
* Slot refers to position. You can specify "head", "body", "mainhand", "offhand", "legs", or "feet". 
* Material refers to the item name. 
* Data refers to the item's damage value. 
* The rest should be self-explanatory.

You need "!!" rather than "!" as the main separator, and "\!" as the separator before any enchantments. This is because there is no easier way to parse the configuration. Here's an example that equips a skeleton with a diamond helmet (with Thorns 5) and a diamond sword (with sharpness 3):
```
  SAND:
    - drop: SKELETON@eq:head:DIAMOND_HELMET@\!THORNS#5%50!!eq:mainhand:DIAMOND_SWORD@\!DAMAGE_ALL#3%50
```
</p></details>

***
<details><summary><b>Mob Health</b></summary><p>

To specify the max health of a creature, simply use a number (as if it were a data value) followed by an "h". For example, `ZOMBIE@20h` means a zombie with a maximum health of 20 points.</p></details>

***
<details><summary><b>Mob Names</b>
</summary><p>

You can specify drops to happen for only custom named mobs with the `~` symbol. Use Zombie@~Custom Name (color codes are supported!). If you want to include an `&` inside the mob's name, you MUST use `&&`. The plugin automatically replaces all occurrences of `_` with a space (` `). To specify an underscore inside the name, use `&_`. Lastly, to include very literally the text `&_` inside the name, use `&&_`. 

If you want the drop to apply only to nameless, regular zombies, you must use `ZOMBIE@~:` This is because the `<name>` parameter is blank; essentially meaning a nameless zombie. This will make it so that named zombies will NOT perform the drop, but any unnamed zombies will. Do note that all data must be specified BEFORE the name. These guidelines apply for all creatures.</p></details>

***
<details><summary><b>Multiple Parameters</b></summary>
<p>

To specify multiple parameters on the same creature, you have to separate each type of parameter with a single exclamation mark, `!` To specify both data and names, the format is: `<MobName>@!<Data1>!<Data2>!<Etc><Name>` If you have any issues with this, it may be due to the following reason. The plugin will sometimes incorrectly interpret the separator ( `!` vs `!!` ) for some mobs. For example, one mob may require `!!` to work, whereas another requires just `!` This bug **cannot** be patched. If you are having any issues with detecting the mob, please try swapping the separator. If you are using `!` attempt `!!` and vice versa.

</p></details>