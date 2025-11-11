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

**UncomplicatedCustomItems (UCI) is an open-source plugin for EXILED & LabAPI that allows you to configure custom items entirely via YAML**, without writing C# code. You can define damage values, behaviors, crafting, and more, all from config files.

[GitHub Repository](https://github.com/UncomplicatedCustomServer/UncomplicatedCustomItems)

[UCSC Discord](https://discord.gg/5StRGu8EJV)

***

### Installation

1. Go to the [latest release](https://github.com/UncomplicatedCustomServer/UncomplicatedCustomItems/releases) and download `UncomplicatedCustomItems-FRAMEWORK.dll`.
2. Place the DLL into your server’s `EXILED/Plugins` / `LabAPI/Plugins` folder.
3. Restart your SCP:SL server to load the plugin.

***

### Initial Setup

* UCI uses **its own config files**, separate from EXILED's or LabApi's main config.
* Find a folder like `Config/UncomplicatedCustomItems` and add your custom items as `.yml` files.

#### Example Config

{% code expandable="true" %}
```yaml
# Sets the ID of the custom item. Custom items cannot share IDs.
id: 2
# Sets the name of the custom item.
name: FunnyGun
# Sets the description of the custom item. This is shown as part of a hint when the item is equipped or picked up.
description: A FRMG0 that has a shotgun-like bullet spread
# The extended description of the custom item. Used by the `.customiteminfo` command
extended_description: ''
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
  spawn_settings:
  - chance: 30
    # Custom coordinates where the custom item will spawn.
    coords:
      x: 0
      y: 0
      z: 0
    # The rotation of the CustomItem when spawned
    rotation:
      x: 0
      y: 0
      z: 0
      w: 0
    locker_settings:
      enable: false
      locker_type: RifleRack
      room: HczWarhead
      zone: HeavyContainment
      chamber: 0
      offset:
        x: 0
        y: 0
        z: 0
    # The room(s) where the custom item can spawn.
    dynamic_spawn:
    - room: Lcz914
      coords:
        x: 1
        y: 1
        z: 1
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
custom_flags: WorkstationBan
# Settings for the CustomFlags. You can remove any unused settings.
flag_settings:
# Sets the settings for the ItemGlow flag.
  item_glow_settings:
  - glow_color: '#00FF00'
    intensity: 1
    range: 2
  # Sets the settings for the LifeSteal flag.
  life_steal_settings:
  - life_steal_amount: 8
    # Sets the percentage of health regenerated if the item has the LifeSteal custom flag. HealedAmount = Amount * Percentage
    life_steal_percentage: 0.5
  # Sets the settings for the Effect flags.
  effect_settings:
  - effect_event: EffectWhenUsed
    # Sets the effect that the custom item will apply.
    effect: Flashed
    # Sets the intensity of the effect applied by the custom item.
    effect_intensity: 1
    # Sets the duration of the effect applied by the custom item.
    effect_duration: 1
    # If true when the effect is applied while the current effect is active it will add the duration to the current effect duration
    add_duration_if_active: true
    clear_on_unequip: true
  # Sets the settings for the CustomSound flag.
  audio_settings:
  - audio_path: ~.config/SCP Secret Laboratory/LabAPI/configs/UncomplicatedCustomItems/Example.ogg
    # Sets the distance that the audio will be heard for.
    audible_distance: 20
    # Sets the volume percent of the audio.
    sound_volume: 20
  # Sets the settings for the ExplosiveBullets flag.
  explosive_bullets_settings:
  - damage_radius: 1
  # Sets the settings for the SpawnItemWhenDetonated flag.
  spawn_item_when_detonated_settings:
  -
  # Set this to UCI, ECI, or Normal.
    item_type: Normal
    item_id: 1
    time_till_despawn: 6
    chance: 100
    pickupable: false
  cluster_settings:
  - item_to_spawn: KeycardJanitor
    amount_to_spawn: 6
    scp_damage_multiplier: 5
    fuse_time: 5
  switch_role_on_use_settings:
  - delay: 6
    # Set this to UCR or Normal.
    role_type: Normal
    # Set this to the RoleTyped if Normal or customrole id for UCR or ECR.
    role_id: 0
    # This can be set to None, AssignInventory, UseSpawnpoint, or All. Use this only if the role_type is Normal
    spawn_flags: None
    # Change this if your role_type is UCR
    keep_location: true
  die_on_drop_settings:
  - death_message: Dropped %name%
    vaporize: true
  cant_drop_settings:
  - hint_or_broadcast: hint
    message: You cant drop %name%!
    duration: 10
  # This is recommended to only be applied to armor.
  disguise_settings:
  - reveal_when_damaged: false
    role_id: NtfSpecialist
    disguise_message: Your are disguised as an NtfSpecialist!
    custom_info: ''
  craftable_settings:
  - knob_setting: Coarse
    original_item: Adrenaline
    chance: 100
  die_on_use_settings:
  - death_message: Killed by %name%
    vaporize: false
  heal_on_kill_settings:
  - heal_amount: 1
    convert_to_ahp_if_full: false
  hume_shield_settings:
  - regen_rate: 2
    max_hume_shield: 90
    regen_cool_down: 1
  mer_spawn_settings:
  - locker_spawning: false
    replace_primitive: false
    schematic_name: Test
    object_name: ''
  ammo_regen_settings:
  - regen_delay: 5
    regen_interval: 1
    ammo_per_interval: 1
arguments:
  OnChangedItem: after 5s then Player::Damage(1, "Test", 'AIMING')
  OnShotWeapon: action Example
  OnAimedWeapon: Player::Damage(10, "Test", 'AIMING')
# Sets the custom data type the item will use.
custom_item_type: Weapon
# Specifies the modifications the custom item will have.
custom_data:
  damage: 2.75
  max_ammo: 150
  max_magazine_ammo: 150
  max_barrel_ammo: 100
  penetration: 1.24000001
  inaccuracy: 1.24000001
  aiming_inaccuracy: 1.24000001
  damage_falloff_distance: 1
  attachments: DotSight
  enable_friendly_fire: false

```
{% endcode %}
