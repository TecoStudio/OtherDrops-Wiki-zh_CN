# 常见的一些问题
OtherDrops 是一个极其复杂的插件，需要学习和适应。我们希望此常见问题解答页面将有助于解决我们收到的有关该插件的一些更常见的问题。

Q: 如何安装 OtherDrops 的 beta 版本？
---
A: 为了安装本插件的 Beta 版本，您必须加入我们的 [插件支持 Discord 服务器](discord.gg/eHBxk5q "获得 OtherDrops 支持的最佳地点"). 加入服务器后，请阅读并接受我们的条款和条件。 完成后，在 [#plugin-selection](https://discordapp.com) 中找到插件通知选择菜单<sup>[[1]](#fn1 "Footnote 1")</sup> [#plugin-selection](https://discordapp.com/channels/418432278113550337/604078032671473715 "Plugin Selection")频道。使用 B 对消息做出反应并转到 [#beta-updates](https://discordapp.com/channels/418432278113550337/442705812234698752 "Beta Releases") 频道. 最新的测试版将有一个标有 NEW 的标签。 对于 1.12 及以下版本，请使用 Legacy。 对于所有更高版本，请使用 1.13。

Q: OtherDrops 是否支持带有自定义名称和传说的物品？
---
A: 简而言之，是的！ OtherDrops 允许您掉落具有自定义传说的物品，甚至可以将它们指定为工具！ 为此，请遵循以下格式： `ITEM_ID@~CustomName;lore line 1;line 2;line 3`<sup>[[2]](#fn2 "Footnote 2")</sup> where  
  - `ITEM_ID` 是您指定的项目
  - `CustomName` 是项目的名称（支持 &x 颜色代码）
  - `lore line 1`, `line 2`, 以及 `line 3` 是lore的行（支持&x颜色代码）

Q: 我可以使用自定义生物作为掉落物和目标吗？
---
A: 您可以删除并指定具有自定义名称的某些实体。 你应该使用格式 `ENTITY_TYPE@~CustomName`<sup>[[2]](#fn2 "Footnote 2")</sup> where  
  - `ENTITY_TYPE` 是您指定的实体
  - `CustomName` 是生物的名称（支持 &x 颜色代码）

Q: 我可以在我的工具/掉落的物品上使用附魔吗？
---
A: 您可以在物品上指定任意数量的附魔。使用格式`ITEM_ID@!ENCHANTMENT1#LEVEL!ENCHANTMENT2#LEVEL!~CustomNameData`<sup>[[2]](#fn2 "Footnote 2")</sup> where  
  - `ITEM_ID` 是您指定的项目
  - `ENCHANTMENT1` 和 `ENCHANTMENT2` 均为魔咒ID
  - `LEVEL` 是魔咒的等级 

指定数据时，使用 `!` 字符拆分数据的新部分（例如，在不同的附魔之间）。 `#` 是附魔和等级的分隔符 (`ENCHANTMENT#LEVEL`)。 如脚注 2 所述，一旦指定了所有其他项目数据，自定义名称数据就会出现在最后。
***
<a name="fn1"><sup>1</sup></a> 通知选择菜单

![插件选择菜单](https://i.imgur.com/aFalLWw.jpg)

<a name="fn2"><sup>2</sup></a> 确保在指定所有其他数据后指定自定义名称/知识。