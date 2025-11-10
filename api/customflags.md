---
icon: flag
---

# CustomFlags

### ItemGlowSettings

* **CustomFlag:** ItemGlow
* **Description:** Sets the settings for the ItemGlow flag. Controls the glow color and related glow behavior of the item.
* **Parameters:**
  * `GlowColor` — The color of the item's glow, represented as a hex color string (e.g., `#00FF00`).

***

### LifeStealSettings

* **CustomFlag:** LifeSteal
* **Description:** Sets the settings for the LifeSteal flag. Defines how much life is stolen from targets, both as a flat amount and a percentage.
* **Parameters:**
  * `LifeStealAmount` — The flat amount of health stolen per hit.
  * `LifeStealPercentage` — The percentage of the damage dealt converted to health.

***

### EffectSettings

* **CustomFlag:** EffectWhenUsed, EffectShot, EffectWhenEquiped
* **Description:** Sets the settings for the Effect flags. Controls the application of special effects triggered by item use, shooting, or equipping, including effect type, duration, and intensity.
* **Parameters:**
  * `EffectEvent` — The event that triggers the effect (e.g., "EffectWhenUsed").
  * `Effect` — The type of effect applied (e.g., `EffectType.AntiScp207`).
  * `EffectDuration` — Duration of the effect in seconds.
  * `EffectIntensity` — Intensity level of the effect.

***

### AudioSettings

* **CustomFlag:** CustomSound
* **Description:** Sets the settings for the CustomSound flag. Manages custom sounds played by the item, including sound file path, volume, and audible distance.
* **Parameters:**
  * `AudioPath` — Path to the audio file.
  * `SoundVolume` — Volume level of the sound.
  * `AudibleDistance` — Maximum distance at which the sound can be heard.

***

### ExplosiveBulletsSettings

* **CustomFlag:** ExplosiveBullets
* **Description:** Sets the settings for the ExplosiveBullets flag. Defines explosive bullet behavior such as damage radius.
* **Parameters:**
  * `DamageRadius` — Radius of damage caused by the explosive bullets.

***

### SpawnItemWhenDetonatedSettings

* **CustomFlag:** SpawnItemWhenDetonated
* **Description:** Sets the settings for the SpawnItemWhenDetonated flag. Configures spawning of items upon detonation, including item type, spawn chance, despawn time, and pickup properties.
* **Parameters:**
  * `ItemType` — Type of the item to spawn.
  * `ItemId` — Identifier of the item to spawn.
  * `Chance` — Percentage chance for the item to spawn.
  * `TimeTillDespawn` — Time in seconds before the spawned item despawns.
  * `Pickupable` — Whether the spawned item can be picked up.

***

### ClusterSettings

* **CustomFlag:** Cluster
* **Description:** Settings for cluster item spawning. Controls the number of items to spawn as a cluster and which item is spawned.
* **Parameters:**
  * `ItemToSpawn` — The item to spawn in the cluster.
  * `AmountToSpawn` — Number of items to spawn.

***

### SwitchRoleOnUseSettings

* **CustomFlag:** SwitchRoleOnUse
* **Description:** Settings for switching player roles when an item is used. Includes role type, spawn delay, spawn flags, and whether to keep player location during the switch.
* **Parameters:**
  * `RoleType` — Type of role to switch to.
  * `RoleId` — Specific role identifier.
  * `Delay` — Delay in seconds before the role switch occurs.
  * `SpawnFlags` — Flags controlling spawn behavior.
  * `KeepLocation` — Whether to keep the player's current location after switching roles.

***

### DieOnDropSettings

* **CustomFlag:** DieOnDrop
* **Description:** Settings that define behavior when the item is dropped. For example, causing the player to die with a custom death message and whether to vaporize the body.
* **Parameters:**
  * `DeathMessage` — Message shown on death caused by dropping the item.
  * `Vaporize` — Whether the player’s body vaporizes on death.

***

### CantDropSettings

* **CustomFlag:** CantDrop
* **Description:** Settings that prevent the player from dropping the item. Provides messages or hints when drop attempts are made and controls message duration.
* **Parameters:**
  * `HintOrBroadcast` — Whether to show a hint or broadcast message when drop is prevented.
  * `Message` — The message to display.
  * `Duration` — Duration in seconds for which the message is shown.

***

### DisguiseSettings

* **CustomFlag:** Disguise
* **Description:** Settings for disguising the player’s role or appearance. Recommended mainly for armor items, includes the disguise role and message shown to the player.
* **Parameters:**
  * `RoleId` — Role to disguise as.
  * `DisguiseMessage` — Message displayed to the player when disguised.

***

### CraftableSettings

* **CustomFlag:** Craftable
* **Description:** Settings related to crafting items. Controls crafting parameters like the crafting knob setting, original item type, and chance of success.
* **Parameters:**
  * `KnobSetting` — Crafting knob setting (e.g., coarse, fine).
  * `OriginalItem` — The original item type used in crafting.
  * `Chance` — Percentage chance of successful crafting.

***

### DieOnUseSettings

* **CustomFlag:** DieOnUse
* **Description:** Settings for causing death on item use. Allows customizing the death message and whether the player’s body vaporizes.
* **Parameters:**
  * `DeathMessage` — Message shown on death caused by using the item.
  * `Vaporize` — Whether the player’s body vaporizes on death.

***

### HealOnKillSettings

* **CustomFlag:** HealOnKill
* **Description:** Settings for healing the player upon making a kill. Defines the amount healed and whether to convert healing to auxiliary health points if the player is already full health.
* **Parameters:**
  * `HealAmount` — Amount of health restored on kill.
  * `ConvertToAhpIfFull` — Whether to convert healing to auxiliary health points if main health is full.

***

### Additional Flags Without Explicit Settings

#### DoNotTriggerTeslaGates

* **CustomFlag:** DoNotTriggerTeslaGates
* **Description:** Prevents the item from triggering Tesla gates.

***

#### InfiniteAmmo

* **CustomFlag:** InfiniteAmmo
* **Description:** Grants the item infinite ammunition.

***

#### WorkstationBan

* **CustomFlag:** WorkstationBan
* **Description:** Restricts the item from being used on workstations.

***

#### NoCharge

* **CustomFlag:** NoCharge
* **Description:** Disables charging mechanics for Jailbirds.

***

#### ToolGun

* **CustomFlag:** ToolGun
* **Description:** ToolGun.

***

#### VaporizeKills

* **CustomFlag:** VaporizeKills
* **Description:** Causes kills with this item to vaporize the victim's body.

***

#### ChangeAppearanceOnKill

* **CustomFlag:** ChangeAppearanceOnKill
* **Description:** Changes the player’s appearance to the person killed.

***

#### Capybara

* **CustomFlag:** Capybara
* **Description:** Makes the wearer into a Capybara

_Note:_\
&#x20;      This flag was made as a joke and is a tad buggy.

***

#### SingleFire

* **CustomFlag:** SingleFire
* **Description:** Forces the item’s firing mode to single shot only, disabling automatic or burst fire modes.
