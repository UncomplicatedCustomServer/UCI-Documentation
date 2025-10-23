---
description: A fast setup for SCP:SL server owners to fully enable custom items using UCI.
icon: bolt
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Quickstart

### What Is UCI?

**UncomplicatedCustomItems (UCI)** is an open‑source plugin for EXILED & LabAPI that lets you **configure custom items entirely via YAML**, without writing C# code. You can define damage values, behaviors, crafting, and more—all from config files.

🔗 [GitHub Repository](https://github.com/UncomplicatedCustomServer/UncomplicatedCustomItems)

***

### Installation

1. Go to the [latest release](https://github.com/UncomplicatedCustomServer/UncomplicatedCustomItems/releases) and download `UncomplicatedCustomItems-FRAMEWORK.dll`.
2. Place the DLL into your server’s `EXILED/Plugins` / `LabAPI/Plugins` folder.
3. Restart your SCP:SL server to load the plugin.

***

### Initial Setup

* UCI uses **its own config files**, separate from EXILED’s main config.
* Find a folder like `Config/UncomplicatedCustomItems` and add your custom items as `.yml` files.

#### 📄 Example Config

```yaml
# Sets the ID of the custom item. Custom items cannot share IDs.
id: 2
# Sets the name of the custom item.
name: FunnyGun
# Sets the description of the custom item. This is shown as part of a hint when the item is equipped or picked up.
description: A magic weapon that has a shotgun-like bullet spread
# Sets the badge name of the custom item. Remove the text in quotes to disable it.
badge_name: FunnyGun
# Sets the badge color of the custom item.
badge_color: pumpkin
# Sets the weight of the custom item. This affects movement speed when equipped.
weight: 2
# Sets the item the custom item will use.
item: GunFRMG0
# Sets the scale of the custom item when dropped.
scale:
  x: 1
  y: 1
  z: 1
# Defines the spawn settings for the custom item. Information on rooms can be found in the UCI Information forum on Discord.
spawn:
# If true, the custom item can spawn. If false, it will not.
  do_spawn: false
  # The number of custom items to spawn.
  count: 1
  # Replace a existing item in a SCP Pedestal with this CustomItem.
  pedestal_spawn: false
  # Custom coordinates where the custom item will spawn.
  coords: []
  # The room(s) where the custom item can spawn.
  dynamic_spawn:
  - room: Lcz914
    chance: 30
    coords:
      x: 0
      y: 0
      z: 0
  # The zone(s) where the custom item can spawn.
  zones:
  - HeavyContainment
  - Entrance
  # If true, the custom item will replace an existing in-game item.
  replace_existing_pickup: false
  # If true, this item will only replace another pickup of the same item type as the custom item.
  force_item: false
  # If true, this item can replace items in SCP Pedestals.
  replace_items_in_pedestals: false
# Sets the custom flags of the custom item. Information about custom flags can be found in the UCI Information forum on Discord.
custom_flags: InfiniteAmmo
# Settings for the CustomFlags. You can remove any unused settings.
flag_settings:
# Sets the custom data type the item will use.
custom_item_type: Weapon
# Specifies the modifications the custom item will have.
custom_data:
  damage: 2.75
  max_ammo: 150
  max_magazine_ammo: 150
  max_barrel_ammo: 100
  penetration: 1.24
  inaccuracy: 1.24
  aiming_inaccuracy: 1.24
  damage_falloff_distance: 1
  attachments: DotScope
  enable_friendly_fire: False
```
