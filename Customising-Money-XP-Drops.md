Monetary rewards are provided via Vault - please ensure you have it installed along with your economy plugin.

As of June 2018 Vault officially supports the following economy plugins: iConomy 4,5,6, BOSEconomy 6 & 7, EssentialsEcon, 3Co, MultiCurrency, MineConomy, eWallet, EconXP, CurrencyCore, CraftConomy, AEco, Gringotts.

## Rewards:
```
  zombie:   2    # reward $2 (or whatever currency you have)
  spider:   1.53 # reward $1.53
  skeleton: 1-5  # reward between $1 and $5 (fractional amounts allowed)
  wolf:     -3   # deduct $3 from players account (ie. penalty)
  player:   20   # reward $20 for pvp kills
```
## Advanced layout
This allows you to add messages and conditions such as time, biome, world, etc.
```
  zombie:
  - drop: money/3
    message: "You got %q credits for killing %v."
    time: day

  - drop: money/2
    message: "You got %q credits for killing %v."
    time: night
```