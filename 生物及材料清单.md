The values which you can specify for your `BLOCK:`, `tool:` and `drop:` fields are given below, and sorted into categories.

Note that these values are a superset of those values given in the Material Enum built into [Spigot Material List (1.13 ONLY)](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html). New values will automatically work.

### OtherBlocks custom values
<table width="100%">
  <tr><th>Special Values - Block</th></tr>
  <tr><td><ul style="padding:0">
    <li><b>PLAYER</b> - set what drops what a player is killed, can also use PLAYER@name</li>
    <li><b>PLAYERGROUP@name</b> - set what drops what a player within the named permission group is killed</li>
    <li><b>SPECIAL_LEAFDECAY</b> - sets the drops for when leaves decay</li>
    <br />
  </ul></td></tr>
  <tr><th>Special Values - Tool</th></tr>
  <tr><td><ul style="padding:0">
    <li><b>ANY / ALL</b> - used in the <i>tool:</i> slot, allows any weapon to be used.</li>
    <li><b>NOTHING</b> - shorthand for <i>AIR</i>. When used as a <i>tool</i>, represents an empty hand </li>
    <li><b>DYE</b> - shorthand for <i>INK_SACK</i></li>
    <br />
  </ul></td></tr>
  <tr><th>Special Values - Drop</th></tr>
  <tr><td><ul style="padding:0">
    <li><b>NOTHING</b> - shorthand for <i>AIR</i>. Prevents the default drop from ever occurring </li>
    <li><b>DEFAULT</b> - allows the default drop to occur along with whatever else drops.</li>
    <li><b>MONEY</b> - give (or take) money as per amount in <i>quantity:</i> parameter.</li>
    <li><b>DYE</b> - shorthand for <i>INK_SACK</i></li>
    <li><b>CONTENTS</b> - used in the <i>drop:</i> slot, drops the contents of the block (for e.g. furnaces)</li>
    <li><b>DENY</b> - for block break only, denies the block from breaking at all, other drops may still occur</li>
    <li><b>NODROP</b> - for PLAYER only, default for a player is to drop default inventory, use this if you want killed players to drop no inventory items</li>
    <br />
  </ul></td></tr>
  <tr><th>Collective names (used for `BLOCK:` or `tool:`)</th></tr>
  <tr><td><ul> 
    <li><b>ANY_FURNACE</b> - <i>FURNACE</i> or <i>BURNING_FURNACE</i></li>
    <li><b>ANY_SIGN</b> - <i>SIGN_POST</i> or <i>WALL_SIGN</i> or <i>SIGN</i></li>
    <li><b>ANY_REDSTONE_ORE</b> - <i>REDSTONE_ORE</i> or <i>GLOWING_REDSTONE_ORE</i></li>
    <li><b>ANY_REDSTONE_TORCH</b> - <i>REDSTONE_TORCH_OFF</i> or <i>REDSTONE_TORCH_ON</i></li>
    <li><b>ANY_DIODE_BLOCK</b> - <i>DIODE_BLOCK_OFF</i> or <i>DIODE_BLOCK_ON</i></li>
    <li><b>ANY_SPADE</b> - <i>WOOD_SPADE</i> or <i>STONE_SPADE</i> or <i>GOLD_SPADE</i> or <i>IRON_SPADE</i> or <i>DIAMOND_SPADE</i></li>
    <li><b>ANY_AXE</b> - <i>WOOD_AXE</i> or <i>STONE_AXE</i> or <i>GOLD_AXE</i> or <i>IRON_AXE</i> or <i>DIAMOND_AXE</i></li>
    <li><b>ANY_HOE</b> - <i>WOOD_HOE</i> or <i>STONE_HOE</i> or <i>GOLD_HOE</i> or <i>IRON_HOE</i> or <i>DIAMOND_HOE</i></li>
    <li><b>ANY_PICKAXE</b> - <i>WOOD_PICKAXE</i> or <i>STONE_PICKAXE</i> or <i>GOLD_PICKAXE</i> or <i>IRON_PICKAXE</i> or <i>DIAMOND_PICKAXE</i></li>
    <li><b>ANY_SWORD</b> - <i>WOOD_SWORD</i> or <i>STONE_SWORD</i> or <i>GOLD_SWORD</i> or <i>IRON_SWORD</i> or <i>DIAMOND_SWORD</i></li>
    <li><b>ANY_HELMET</b> - <i>LEATHER_HELMET</i> or <i>CHAINMAIL_HELMET</i> or <i>GOLD_HELMET</i> or <i>IRON_HELMET</i> or <i>DIAMOND_HELMET</i></li>
    <li><b>ANY_CHESTPLATE</b> - <i>LEATHER_CHESTPLATE</i> or <i>CHAINMAIL_CHESTPLATE</i> or <i>GOLD_CHESTPLATE</i> or <i>IRON_CHESTPLATE</i> or <i>DIAMOND_CHESTPLATE</i></li>
    <li><b>ANY_LEGGINGS</b> - <i>LEATHER_LEGGINGS</i> or <i>CHAINMAIL_LEGGINGS</i> or <i>GOLD_LEGGINGS</i> or <i>IRON_LEGGINGS</i> or <i>DIAMOND_LEGGINGS</i></li>
    <li><b>ANY_BOOTS</b> - <i>LEATHER_BOOTS</i> or <i>CHAINMAIL_BOOTS</i> or <i>GOLD_BOOTS</i> or <i>IRON_BOOTS</i> or <i>DIAMOND_BOOTS</i></li>
    <br />
  </ul></td></tr>
  <tr><th>Damages (can be used as tools against creatures)</th></tr>
  <tr><td><ul>
    <li><b>DAMAGE_FIRE</b> - death by fire or lava</li>
    <li><b>DAMAGE_ENTITY_ATTACK</b> - killed by an entity (for specific entities, use a <i>CREATURE</i> value)</li>
    <li><b>DAMAGE_BLOCK_EXPLOSION</b> - killed by TNT or other exploding block</li>
    <li><b>DAMAGE_ENTITY_EXPLOSION</b> - killed by a creeper or other exploding entity</li>
    <li><b>DAMAGE_CONTACT</b> - killed by touching a block, such as a cactus</li>
    <li><b>DAMAGE_DROWNING</b> - killed by drowning in water</li>
    <li><b>DAMAGE_FALL</b> - killed by falling from a high height</li>
    <li><b>DAMAGE_SUFFOCATION</b> - killed by suffocating in a block</li>
    <br />
  </ul></td></tr>
</table>

### Built-in values
<table width="100%">
  <tr>
    <th>Blocks</th>
    <th>Items and tools</th>
    <th>Creatures</th>
  </th>
  <tr>
    <td valign="top">
      <ul>
        <li>AIR</li>
        <li>STONE</li>
        <li>GRASS</li>
        <li>DIRT</li>
        <li>COBBLESTONE</li>
        <li>WOOD</li>
        <li>SAPLING</li>
        <li>BEDROCK</li>
        <li>WATER</li>
        <li>STATIONARY_WATER</li>
        <li>LAVA</li>
        <li>STATIONARY_LAVA</li>
        <li>SAND</li>
        <li>GRAVEL</li>
        <li>GOLD_ORE</li>
        <li>IRON_ORE</li>
        <li>COAL_ORE</li>
        <li>LOG</li>
        <li>LEAVES</li>
        <li>SPONGE</li>
        <li>GLASS</li>
        <li>LAPIS_ORE</li>
        <li>LAPIS_BLOCK</li>
        <li>DISPENSER</li>
        <li>SANDSTONE</li>
        <li>NOTE_BLOCK</li>
        <li>BED_BLOCK</li>
        <li>WOOL</li>
        <li>YELLOW_FLOWER</li>
        <li>RED_ROSE</li>
        <li>BROWN_MUSHROOM</li>
        <li>RED_MUSHROOM</li>
        <li>GOLD_BLOCK</li>
        <li>IRON_BLOCK</li>
        <li>DOUBLE_STEP</li>
        <li>STEP</li>
        <li>BRICK</li>
        <li>TNT</li>
        <li>BOOKSHELF</li>
        <li>MOSSY_COBBLESTONE</li>
        <li>OBSIDIAN</li>
        <li>TORCH</li>
        <li>FIRE</li>
        <li>MOB_SPAWNER</li>
        <li>WOOD_STAIRS</li>
        <li>CHEST</li>
        <li>REDSTONE_WIRE</li>
        <li>DIAMOND_ORE</li>
        <li>DIAMOND_BLOCK</li>
        <li>WORKBENCH</li>
        <li>CROPS</li>
        <li>SOIL</li>
        <li>FURNACE</li>
        <li>BURNING_FURNACE</li>
        <li>SIGN_POST</li>
        <li>WOODEN_DOOR</li>
        <li>LADDER</li>
        <li>RAILS</li>
        <li>DETECTOR_RAIL</li>
        <li>POWERED_RAIL</li>
        <li>COBBLESTONE_STAIRS</li>
        <li>WALL_SIGN</li>
        <li>LEVER</li>
        <li>STONE_PLATE</li>
        <li>IRON_DOOR_BLOCK</li>
        <li>WOOD_PLATE</li>
        <li>REDSTONE_ORE</li>
        <li>GLOWING_REDSTONE_ORE</li>
        <li>REDSTONE_TORCH_OFF</li>
        <li>REDSTONE_TORCH_ON</li>
        <li>STONE_BUTTON</li>
        <li>SNOW</li>
        <li>ICE</li>
        <li>SNOW_BLOCK</li>
        <li>CACTUS</li>
        <li>CLAY</li>
        <li>SUGAR_CANE_BLOCK</li>
        <li>JUKEBOX</li>
        <li>FENCE</li>
        <li>PUMPKIN</li>
        <li>NETHERRACK</li>
        <li>SOUL_SAND</li>
        <li>GLOWSTONE</li>
        <li>PORTAL</li>
        <li>JACK_O_LANTERN</li>
        <li>CAKE_BLOCK</li>
        <li>DIODE_BLOCK_OFF</li>
        <li>DIODE_BLOCK_ON</li>
        <li>LOCKED_CHEST</li>
        <li>TRAP_DOOR</li>
        <li>DEAD_BUSH</li>
        <li>LONG_GRASS</li>
        <li>PISTON_BASE</li>
        <li>PISTON_STICKY_BASE</li>
      </ul>
    </td>
    <td valign="top">
      <ul>
        <li>IRON_SPADE</li>
        <li>IRON_PICKAXE</li>
        <li>IRON_AXE</li>
        <li>FLINT_AND_STEEL</li>
        <li>APPLE</li>
        <li>BOW</li>
        <li>ARROW</li>
        <li>COAL</li>
        <li>DIAMOND</li>
        <li>IRON_INGOT</li>
        <li>GOLD_INGOT</li>
        <li>IRON_SWORD</li>
        <li>WOOD_SWORD</li>
        <li>WOOD_SPADE</li>
        <li>WOOD_PICKAXE</li>
        <li>WOOD_AXE</li>
        <li>STONE_SWORD</li>
        <li>STONE_SPADE</li>
        <li>STONE_PICKAXE</li>
        <li>STONE_AXE</li>
        <li>DIAMOND_SWORD</li>
        <li>DIAMOND_SPADE</li>
        <li>DIAMOND_PICKAXE</li>
        <li>DIAMOND_AXE</li>
        <li>STICK</li>
        <li>BOWL</li>
        <li>MUSHROOM_SOUP</li>
        <li>GOLD_SWORD</li>
        <li>GOLD_SPADE</li>
        <li>GOLD_PICKAXE</li>
        <li>GOLD_AXE</li>
        <li>STRING</li>
        <li>FEATHER</li>
        <li>SULPHUR</li>
        <li>WOOD_HOE</li>
        <li>STONE_HOE</li>
        <li>IRON_HOE</li>
        <li>DIAMOND_HOE</li>
        <li>GOLD_HOE</li>
        <li>SEEDS</li>
        <li>WHEAT</li>
        <li>BREAD</li>
        <li>LEATHER_HELMET</li>
        <li>LEATHER_CHESTPLATE</li>
        <li>LEATHER_LEGGINGS</li>
        <li>LEATHER_BOOTS</li>
        <li>CHAINMAIL_HELMET</li>
        <li>CHAINMAIL_CHESTPLATE</li>
        <li>CHAINMAIL_LEGGINGS</li>
        <li>CHAINMAIL_BOOTS</li>
        <li>IRON_HELMET</li>
        <li>IRON_CHESTPLATE</li>
        <li>IRON_LEGGINGS</li>
        <li>IRON_BOOTS</li>
        <li>DIAMOND_HELMET</li>
        <li>DIAMOND_CHESTPLATE</li>
        <li>DIAMOND_LEGGINGS</li>
        <li>DIAMOND_BOOTS</li>
        <li>GOLD_HELMET</li>
        <li>GOLD_CHESTPLATE</li>
        <li>GOLD_LEGGINGS</li>
        <li>GOLD_BOOTS</li>
        <li>FLINT</li>
        <li>PORK</li>
        <li>GRILLED_PORK</li>
        <li>PAINTING</li>
        <li>GOLDEN_APPLE</li>
        <li>SIGN</li>
        <li>WOOD_DOOR</li>
        <li>BUCKET</li>
        <li>WATER_BUCKET</li>
        <li>LAVA_BUCKET</li>
        <li>MINECART</li>
        <li>SADDLE</li>
        <li>IRON_DOOR</li>
        <li>REDSTONE</li>
        <li>SNOW_BALL</li>
        <li>BOAT</li>
        <li>LEATHER</li>
        <li>MILK_BUCKET</li>
        <li>CLAY_BRICK</li>
        <li>CLAY_BALL</li>
        <li>SUGAR_CANE</li>
        <li>PAPER</li>
        <li>BOOK</li>
        <li>MAP</li>
        <li>SLIME_BALL</li>
        <li>STORAGE_MINECART</li>
        <li>POWERED_MINECART</li>
        <li>EGG</li>
        <li>COMPASS</li>
        <li>FISHING_ROD</li>
        <li>WATCH</li>
        <li>GLOWSTONE_DUST</li>
        <li>RAW_FISH</li>
        <li>COOKED_FISH</li>
        <li>INK_SACK</li>
        <li>BONE</li>
        <li>SUGAR</li>
        <li>CAKE</li>
        <li>BED</li>
        <li>DIODE</li>
        <li>COOKIE</li>
        <li>GOLD_RECORD</li>
        <li>GREEN_RECORD</li>
        <li>WEB</li>
        <li>SHEARS</li>
      </ul>
    </td>
    <td valign="top">
Moved to  [[Creature Page|Creatures]]
    </td>
  </tr>
</table>
