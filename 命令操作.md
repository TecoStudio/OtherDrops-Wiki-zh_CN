The `command:` action allows you to perform a command - all [Message Variables](Message-Variable) are supported. Enclose commands with quotation marks. To run multiple commands, use brackets and commas. You can use the following command prefixes:

| Prefix | Run as... | Send resulting messages to... |
|--------|-----------|-------------------------------|
/  |  Player   | Player
/!  |  Player  |  Console
/*  |  Player (OP override)  |  Player
/!*  |  Player (OP override)  |  Console
/$   | Console  |  Player
/!$   | Console  |  Console

Example:
```/!$case givekey %p premium 1```