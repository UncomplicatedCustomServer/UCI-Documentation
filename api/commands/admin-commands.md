# Admin Commands

## UCI Admin Commands Documentation

Welcome to the **Uncomplicated Custom Items (UCI)** Admin Command reference. Below is a complete list of the administrative commands available for managing and debugging UCI custom items in-game.

***

### `uci generate`

**Description:** Generate a new custom item.

**Usage:**

```
uci generate <id> <Name> <ItemType> <CustomItemType> <Description>
```

**Aliases:** `gen`

**Permission:** `uci.gen`

**Example:**

```
uci generate 10 SuperGun Gun Firearm "A custom firearm that shoots lasers."
```

***

### `uci get`

**Description:** Get information about a summoned custom item using its serial.

**Usage:**

```
uci get <Item Serial>
```

**Aliases:** `get`

**Permission:** `uci.get`

**Output:** Item name, serial, position, relative room position, room name.

***

### `uci give`

**Description:** Give a custom item to a specific player or all players.

**Usage:**

```
uci give <Item Id|Name> [Player Id|Name|all]
```

**Aliases:** `g`

**Permission:** `uci.give`

**Examples:**

```
uci give 5 all
uci give SuperGun player123
```

***

### `uci info`

**Description:** Retrieve all detailed info and settings of a custom item.

**Usage:**

```
uci info <Item Id>
```

**Aliases:** `info`

**Permission:** `uci.info`

**Displays:**

* Basic info (ID, Item type, Scale, Weight)
* Spawn configurations
* Flag-specific settings (Audio, CantDrop, Cluster, Effects, etc.)

***

### `uci list`

**Description:** Lists all registered and unregistered custom items.

**Usage:**

```
uci list
```

**Aliases:** `l`

**Permission:** `uci.list`

**Output:**

* Green ✔ for registered items
* Red ❌ for unregistered items

***

### `ucilogs`

**Description:** Share UCI debug logs with developers (server console only).

**Usage:**

```
ucilogs
```

**Permission:** Console-only

**Output:** Prints a developer log ID on success.

***

### `uci reload`

**Description:** Reloads all UCI items, unregistering and cleaning up pickups.

**Usage:**

```
uci reload
```

**Aliases:** `reload`

**Permission:** `uci.reload`

**Notes:**

* Destroys all summoned items
* Re-registers from config
* Reassigns previously summoned items

***

### `uci summon`

**Description:** Summon a custom item to its spawn point.

**Usage:**

```
uci summon <Item Id>
```

**Aliases:** `spawn`, `s`

**Permission:** `uci.summon`

***

### `uci summoned`

**Description:** Lists every currently summoned item in the game.

**Usage:**

```
uci summoned
```

**Permission:** `uci.summoned`

**Output:** Table with serial, ID, name, owner, and status (pickup/item).

***

### `uci toolgun`

**Description:** Gives the player the UCI ToolGun.

**Usage:**

```
uci toolgun [Player Id/Name]
```

**Aliases:** `tg`

**Permission:** `uci.toolgun`

**Behavior:**

* Defaults to command issuer if no player provided.
* Fails if player is spectator, destroyed, or inventory full.

***

> **Note:** All commands require the round to be started unless specified otherwise.
