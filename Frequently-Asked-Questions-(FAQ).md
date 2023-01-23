# Frequently Asked Questions
OtherDrops is an extremely complicated plugin to learn and adapt to. We hope this FAQ page will help address some of the more commonly asked questions we receive about the plugin.

Q: How do I install beta builds of OtherDrops?
---
A: In order to install Beta-Releases of our plugin, you must join our [Plugin Support Discord Server](discord.gg/eHBxk5q "The best place to receive support for OtherDrops"). Upon joining the server, read and accept our Terms and Conditions. Once you have done so, find the find the Plugin Notification Selection Menu<sup>[[1]](#fn1 "Footnote 1")</sup> in the [#plugin-selection](https://discordapp.com/channels/418432278113550337/604078032671473715 "Plugin Selection") channel. React to the message with the B and head over to the [#beta-updates](https://discordapp.com/channels/418432278113550337/442705812234698752 "Beta Releases") channel. The latest beta releases will have a sticker that says NEW. For 1.12 and below, use Legacy. For all versions greater, use 1.13.

Q: Does OtherDrops support items with custom names and lores?
---
A: In short, yes! OtherDrops allows you to drop items with custom lores, and even specify them as tools! In order to do so, follow the following format: `ITEM_ID@~CustomName;lore line 1;line 2;line 3`<sup>[[2]](#fn2 "Footnote 2")</sup> where  
  - `ITEM_ID` is the item you're specifying
  - `CustomName` is the name of the item (supports &x color codes)
  - `lore line 1`, `line 2`, and `line 3` are the lines of lore (supports &x color codes)

Q: Can I use custom mobs as drops and targets?
---
A: You can drop, and specify, certain entities with custom names. You should use the format `ENTITY_TYPE@~CustomName`<sup>[[2]](#fn2 "Footnote 2")</sup> where  
  - `ENTITY_TYPE` is the entity you're specifying
  - `CustomName` is the name of the mob (supports &x color codes)

Q: Can I use enchantments on my tool/dropped items?
---
A: You can specify as many enchantments as you want on your items. Use the format `ITEM_ID@!ENCHANTMENT1#LEVEL!ENCHANTMENT2#LEVEL!~CustomNameData`<sup>[[2]](#fn2 "Footnote 2")</sup> where  
  - `ITEM_ID` is the item you're specifying
  - `ENCHANTMENT1` and `ENCHANTMENT2` are the enchantments
  - `LEVEL` is the level of the enchantment. 

When specifying data, use the `!` character to split up new portions of your data (e.g. between different enchantments). The `#` is a separator for the enchantment and level (`ENCHANTMENT#LEVEL`). As noted on footnote 2, the custom name data comes at the end, once all other item data has been specified.
***
<a name="fn1"><sup>1</sup></a> Notification Selection Menu

![Plugin Selection Menu](https://i.imgur.com/aFalLWw.jpg)

<a name="fn2"><sup>2</sup></a> Make sure that you specify the custom name/lore AFTER all other data has been specified.