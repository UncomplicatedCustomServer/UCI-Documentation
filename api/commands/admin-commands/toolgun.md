# ToolGun

**Description**\
Give the ToolGun APICustomItem to a target player or yourself.

**Command / Invocation**\
`uci toolgun <Player Id/Name>`

**Visible args**\
`<Player Id/Name>`

**Required permission**\
`uci.toolgun`

**Aliases**\
`tg`

**Example usage**\
`uci toolgun 1` — gives ToolGun to player id 1.\
`uci toolgun` — gives ToolGun to the command sender.

**Behavior notes**

* Looks up `APICustomItem` named `"ToolGun"` from API items and summons it to the target player or the sender.
* Validates target player presence and inventory space and that the target is not a spectator/destroyed.
