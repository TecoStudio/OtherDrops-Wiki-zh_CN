This page contains examples for different ways you can utilize some of the parameters of OtherDrops. For more detailed information about the parameters being used please take a look at the Parameters page.

## Useful Snowballs
In these examples, we will take a look at the "potioneffect" and "damage" parameters. We will turn snowballs into a useful weapon against mobs.
```
    ANY_CREATURE:
        - trigger: HIT
          tool: PROJECTILE_SNOW_BALL
          potioneffect.victim: SLOW@100@2
```
In this example, we are targeting all mobs (ANY_CREATURE) when a mob is hit by a THROWN snowball. It is important that you use PROJECTILE_SNOW_BALL and not SNOW_BALL. They are afflicted with the SLOW potion effect for 5 seconds (100 ticks). 

Now let's add a damage value to it so it can actually hurt mobs.
```
    ANY_CREATURE:
        - trigger: HIT
          tool: PROJECTILE_SNOW_BALL
          potioneffect.victim: SLOW@100@2
          damage.victim: 2
```
This example exclude PLAYERS. This was done because the "damage" parameter doesn't take a player's armor into consideration and will do damage regardless of it, leading to a lot of complaining. You can choose to add it to players if you want. You can also add this to individual mobs instead of using ANY_CREATURE which would have the added benefit of being able to set different damage values per mob (for example, making nether creatures take extra damage).

## Nether-Wart Bonemeal Growth
Let's start off with something fairly simple, we are going to make it so bonemeal can affect the growth of nether warts.
```
    NETHER_WARTS@0:
        - trigger: RIGHT_CLICK
          tool: INK_SACK@15
          consumetool: 1
          replaceblock: NETHER_WARTS@3
```
The block we are changing is NETHER_WARTS, notice the @0 on it, that is telling OtherDrops that we want to modify freshly planted nether warts (growth stage 0). We set the trigger to RIGHT_CLICK, and, the tool to INK_SACK@15 (Bonemeal). The consumetool parameter is set to 1 so each time you grow a nether wart it consumes one bonemeal. The replaceblock parameter is used to change the freshly planted nether wart to its fully grown, harvest-able state.

Now that we have the basic example set up, let's make it so you can apply bonemeal to all stages of a nether wart. Same as before, just change the block-type from NETHER_WART@0 to @1 and @2. Like this:
```
    NETHER_WARTS@0:
        - trigger: RIGHT_CLICK
          tool: INK_SACK@15
          consumetool: 1
          replaceblock: NETHER_WARTS@3
    NETHER_WARTS@1:
        - trigger: RIGHT_CLICK
          tool: INK_SACK@15
          consumetool: 1
          replaceblock: NETHER_WARTS@3
    NETHER_WARTS@2:
        - trigger: RIGHT_CLICK
          tool: INK_SACK@15
          consumetool: 1
          replaceblock: NETHER_WARTS@3
```
And there you have it. Bonemeal can instantly grow nether warts.

## Enchantment Enhancer
This next one is really simple too. We are going to give the Looting enchantment the extra effect of giving players money when they kill a mob with a sword that has the enchantment.
```
    ZOMBIE:
        - tool: DIAMOND_SWORD@!LOOTING#1
          drop: MONEY
          chance: 25
          quantity: 5-10
        - tool: DIAMOND_SWORD@!LOOTING#2
          drop: MONEY
          chance: 30
          quantity: 10-15
        - tool: DIAMOND_SWORD@!LOOTING#3
          drop: MONEY
          chance: 35
          quantity: 15-20
```
In this example, we have extended the function of the looting enchantment to make mobs to drop money (given that an economy plugin is present). Each level of looting gives a different amount of money and has a slightly higher chance of dropping money.

## Grass Seeds
In this next example, we will make use of the lorename condition to create a new type of seed that turns dirt into grass when applied to it.
```
    DIRT:
        - trigger: RIGHT_CLICK
          tool: SEEDS@2
          consumetool: 1
          lorename: '&rGrass Seeds'
          replacementblock: 2
```
As you can see the block we are affecting this time is DIRT. This setup will make it so right clicking dirt while holding SEEDS with a data value of TWO that have been renamed to "Grass Seeds" either by this plugin or another plugin will turn the dirt block into a grass block.

## Special Mobs
In this example, we are going to use the MOBSPAWN trigger and the ability to spawn mobs with equipment. The following example will create a skeleton that appears as a floating pumpkin head carrying a golden hoe (scythe). I call them Reapers. This same example can be used to naturally spawn Giants, Baby Zombies, Witches, Charged Creepers or any other mob that you want. Just adjust the parameters to match the mob.
```
    SKELETON:
        - trigger: MOBSPAWN
          drop: SKELETON@eq:head:PUMPKIN%0!!eq:hands:GOLDEN_HOE%0
          potioneffect.drop: INVISIBILITY@20000@1
          chance: 10
          biome: [PLAINS, FOREST]
          flag: UNIQUE
```
The MOBSPAWN triggers when a mob spawns (in this case when skeletons spawn). In this example, the chance parameter is being used to only replace 10% of spawned skeletons, rather than all of them. In addition, the biome parameter is present so only skeletons that spawn in PLAINS or FOREST biomes will have a chance of spawning as a Reaper. The potioneffect.drop parameter is used to apply the INVISIBILITY potion effect to the Reaper as soon as it spawns. A really high duration as used to make sure it stays invisible for a long time. The %0 after the PUMPKIN and GOLDEN_HOE is the equipment "drop chance." A 0% means it won't drop the equipment when killed.

## Super Creeper
Like the previous example, we will be spawning a special mob using the MOBSPAWN trigger. This time, we will be spawning Charged Creepers that have a speed boost. (For those server owners who have an evil streak in them).
```
    CREEPER:
        - trigger: MOBSPAWN
          drop: CREEPER@POWERED
          chance: 10
          weather: STORM
          potioneffect.drop: SPEED@12000@2
          flag: UNIQUE
```
This example is much simpler- all we are doing here is making it so 10% of creeper spawns will become a charged creeper with a speed boost during a storm. I don't recommend doing this unless you want to hear your chat filled with death messages. ;)

## Elemental Dragons
In this final example, we will give Ender Dragons some new powers by using the HIT trigger.
```
    PLAYER:
        - trigger: HIT
          tool: ENDER_DRAGON
          damage.victim: [LIGHTNING]
          message.victim: "&aThe dragon struck you with a bolt of lightning!"
          chance: 5
          exclusive: 1
        - trigger: HIT
          tool: ENDER_DRAGON
          damage.victim: [FIRE@400]
          message.victim: "&aThe dragon hit you with its fiery breath!"
          chance: 5
          exclusive: 1
        - trigger: HIT
          tool: ENDER_DRAGON
          damage.victim: [FIRE@200]
          event: EXPLOSION
          message.victim: "&aThe dragon hit you with an exploding fireball!"
          chance: 5
          exclusive: 1
        - trigger: HIT
          tool: ENDER_DRAGON
          potioneffect.victim: POISON@200@2
          message.victim: "&aThe dragon bit you with its poisonous fangs!"
          chance: 5
          exclusive: 1
```
This is all pretty straight-forward stuff so I won't go into too much detail. This is giving the dragon a chance to use one of these different attacks each time it hits a player. The "exclusive" parameter is present so multiple attacks can't trigger at the same time (would likely result in instant death!) As you can see, we are taking advantage of many different parameters including: potioneffect, damage, and effect in order to create these attacks. The chance is kept low in these examples because an ender dragon usually scores multiple hits when attacking.