---
icon: wrench
---

# Spawning

### DoSpawn

* **Type:** `bool`
* **Default:** `false`
* **Description:**\
  If `true`, the custom item can spawn naturally in the game. If `false`, it will not spawn.

***

### Count

* **Type:** `uint`
* **Default:** `1`
* **Description:**\
  How many instances of this custom item should be spawned.

***

### PedestalSpawn

* **Type:** `bool?`
* **Default:** `false`
* **Description:**\
  If `true`, this item will replace an item in an SCP Pedestal. If `false`, the custom item will spawn at a specified coordinate location.

***

### Coords

* **Type:** `List<Vector3>`
* **Default:** `[]`
* **Description:**\
  A list of custom coordinate locations where the item can spawn. If empty, `DynamicSpawn` will be used instead.

***

### DynamicSpawn

* **Type:** `List<DynamicSpawn>`
*   **Default:**

    ```yaml
    [
      {
        "Room": "Lcz914",
        "Chance": 30
      }
    ]
    ```
* **Description:**\
  Room-based spawn logic where each entry specifies a room type and a spawn chance. If `Coords` is empty, this will be used. If this is also empty, the `Zones` list will be used.

***

### Zones

* **Type:** `List<ZoneType>`
* **Default:** `[HeavyContainment, Entrance]`
* **Description:**\
  Fallback option used if `Coords` and `DynamicSpawn` are both empty. Specifies the general zones where this item can spawn.

***

### ReplaceExistingPickup

* **Type:** `bool`
* **Default:** `false`
* **Description:**\
  If `true`, this item will replace an existing pickup in the game world. If `false`, it will spawn on the floor.

***

### ForceItem

* **Type:** `bool`
* **Default:** `false`
* **Description:**\
  If `true`, this item will only replace pickups of the same `ItemType` as the custom item itself.

***

### ReplaceItemsInPedestals

* **Type:** `bool?`
* **Default:** `false`
* **Description:**\
  If `true`, allows this item to replace existing items found inside SCP Pedestals.

***

### DynamicSpawn

Defines a room-based spawn point for a custom item.

#### Properties

### Room

* **Type:** `RoomType`
* **Default:** `Lcz330`
* **Description:**\
  The specific room where the item can spawn.

***

### **Chance**

* **Type:** `int`
* **Default:** `30`
* **Description:**\
  The percentage chance (0–100) that the item will spawn in this room.

***

### **Coords**

* **Type:** `Vector3`
* **Default:** `(0, 0, 0)`
* **Description:**\
  The specific in-room coordinates to spawn the item at, relative to the room origin.
