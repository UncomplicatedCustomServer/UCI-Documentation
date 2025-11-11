# Reload

**Description**\
Reloads all custom items, actions, and API items. Safely destroys current summoned instances, clears registries, reloads files, and re-summons preserved items back to players/positions.

**Command / Invocation**\
`uci reload`

**Visible args**\
`(none)`

**Required permission**\
`uci.reload`

**Aliases**\
`reload`

**Example usage**\
`uci reload`

**Behavior notes**

* Captures current summoned items and where they were (player inventories or pickup positions) to re-summon after reload.
* Unregisters all custom items and actions, clears registries, reloads configuration files (including example files & actions), and runs any import/actor tasks asynchronously.
* Re-spawns pickups and re-gives items to players where possible.
* Returns summary counts describing reloaded items/actions/API items and how many new/unregistered ones existed.
