# Random

**Description**\
Give a random normal `ItemType`, a random `CustomItem`, or either to the command sender.

**Command / Invocation**\
`uci random <Item|CustomItem|Both>`

**Visible args**\
`<type>` — `Item`, `CustomItem`, or `Both`.

**Required permission**\
`uci.random`

**Aliases**\
`ran`

**Example usage**\
`uci random Item` — gives a random normal item.\
`uci random CustomItem` — gives a random custom item.\
`uci random Both` — gives either a custom item or a normal item.

**Behavior notes**

* Requires an in-game player (sender must be a player).
* Picks a random entry from `Enum.GetNames(typeof(ItemType))` or `CustomItem.List`.
* When `Both` is selected, combines both lists and then resolves to custom vs normal and gives the item accordingly.
