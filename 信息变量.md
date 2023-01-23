|Variable|Info|
|----------|------|
%loc.x  |  Displays the X coordinate of the player/drop
%loc.y  |  Displays the Y coordinate of the player/drop
%loc.z  |  Displays the Z coordinate of the player/drop
%loc.world |   Displays the WORLD of the player/drop
%date  |  Displays the date
%time  |  Displays the time
%displayname  |  Shows the custom name of the tool or mob used
%deathmessage  |  Shows the death message for the tool or mob used
%t |   Displays as the name of the tool used
%q |   Displays as the drop quantity in-message
%p |   Displays as the (attacking) player's name (or player who broke the block)
%v |   Displays as the victim's name (or block-name if a block is broken)
&`x` |   Changes the text color (where "`x`" is a color code)
&& |   Displays as a single ampersand (used in situation where a single ampersand may be interpreted as a color, eg. "white&&black")

The following message.`x` can be used to send the message to various groups of players:

|Value for `x`|Info|
|----------|------|
attacker | Show a message to the player who triggered the action
victim | Show a message to the player killed (or interacted with)
world | Send a message to all players in the world in which the event occurred
server | Send a message to all players on the server
radius | Sends a message to all players within the action_radius defined in the config
radius@`#` | Sends a message to all players within the `#` block radius