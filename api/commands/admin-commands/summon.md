# Summon

**Description**\
Summon an existing custom item to its configured spawn point. Works for both internal `ICustomItem` and `APICustomItem` definitions.

**Command / Invocation**\
`uci summon <Item Id>`

**Visible args**\
`<Item Id>`

**Required permission**\
`uci.summon`

**Aliases**\
`spawn`, `s`

**Example usage**\
`uci summon 42`

**Behavior notes**

* Only allowed when a round is started.
* Accepts a numeric Item Id and tries to find it in `CustomItem` and `APICustomItem` collections.
* Calls appropriate summon methods for each type and returns success/failure.
