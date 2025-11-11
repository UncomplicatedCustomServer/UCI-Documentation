# Info

**Description:**\
Gets the extended description of a `CustomItem` the player is currently holding. If the player is not holding a custom item, the command will attempt to find a summoned custom item in the player's inventory and return an appropriate error message.

**Command:**\
`.customiteminfo`\
**Aliases:** `.info`, `.cinfo`

**Example usage:**\
`info` — while holding a CustomItem that has an extended description.

**Behavior / logic summary:**

* Command must be executed in-game by a player (not server console).
* If the player does not hold an item, it checks the player's inventory for summoned custom items and returns an error if none are found.
* If the held item is a summoned custom item and it contains a non-empty `ExtendedDescription`, the command returns that description.
* The returned description supports placeholders which are replaced before being sent:
  * `%name%` -> CustomItem name
  * `%playername%` / `%player%` -> owner display name
  * `%id%` -> custom item ID
  * `%serial%` -> summoned item serial
