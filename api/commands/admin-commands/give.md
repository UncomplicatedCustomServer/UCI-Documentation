# Give

**Description**\
Give a custom item (or API custom item) to a player, all players, or yourself.

**Command / Invocation**\
`uci give <Item Id|Name> <PlayerId|all>`

**Visible args**\
`<Item Id> <Player Id/All>`

**Required permission**\
`uci.give`

**Aliases**\
`g`

**Example usage**\
`uci give 42 1` — gives item id 42 to player with id 1.\
`uci give "My Custom Item" all` — gives that custom item to all players.

**Behavior notes**

* Accepts either numeric ID or display name (strips tags).
* Supports both `ICustomItem` and `APICustomItem` instances.
* Special handling for `SCP330` candy items (handles candy bag fullness).
* Validates that the target player exists and is not a spectator/destroyed and that the inventory is not full.
* Supports `all` to give to all ready players who have inventory space.
