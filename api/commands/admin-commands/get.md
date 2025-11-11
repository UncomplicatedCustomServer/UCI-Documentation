# Get

**Description**\
Get info on a summoned custom item by its serial (shows pickup position, room, and relative coordinates).

**Command / Invocation**\
`uci get <Item Serial>`

**Visible args**\
`<Item Serial>` (required)

**Required permission**\
`uci.get`

**Aliases**\
`get`

**Example usage**\
`uci get 1024`

**Behavior notes**

* Parses the serial and tries two lookups: `SummonedCustomItem.TryGet` and `SummonedAPICustomItem.TryGet`.
* Returns formatted position, relative position inside room, and room name for the matching summoned item.
* Returns a message if the serial doesn't match a custom item.
