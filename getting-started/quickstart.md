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

{% hint style="info" %}
As of version 4.0.0, UncomplicatedCustomItems (UCI) is fully based on LabAPI. The Exiled version only uses properties from Exiled when needed.
{% endhint %}

### Installation

1. Get the [latest release](https://github.com/UncomplicatedCustomServer/UncomplicatedCustomItems/releases) and download `UncomplicatedCustomItems-FRAMEWORK.dll`.
2. Place the DLL into your server’s `EXILED/Plugins` / `LabAPI/Plugins` folder.
3. Restart your SCP:SL server to load the plugin.

***

### Initial Setup

* UCI uses **its own config files**, separate from EXILED's or LabApi's main config.
* Find a folder like `Config/UncomplicatedCustomItems` and add your custom items as `.yml` files.

#### Example Config

{% code title="funnygun.yml" expandable="true" %}
```yml
id: 2
name: FunnyGun
description: A weapon that has a shotgun-like bullet spread
extended_description: ''
badge_name: FunnyGun
badge_color: pumpkin
weight: 2
item: GunFRMG0
scale:
  x: 1
  y: 1
  z: 1
spawn:
  do_spawn: true
  count: 1
  spawn_settings:
  - chance: 100
    locker_settings:
      enable: true
      locker_type: RifleRack
      room: HczWarhead
      zone: HeavyContainment
      chamber: MainChamber
      offset:
        x: 0
        y: 0
        z: 0
  - chance: 100
    locker_settings:
      enable: true
      locker_type: RifleRack
      room: Hcz049
      zone: HeavyContainment
      chamber: MainChamber
      offset:
        x: 0
        y: 0
        z: 0
custom_modules:
  InfiniteAmmo: []
  ItemGlow:
  - GlowColor: '#00FF00'
    range: 5
    intensity: 2
  DistruptorTracer: []
  PickupHintOverride:
  - hint: 'This is a funny gun!'
    duration: 5
  EquipHintOverride:
  - hint: 'You have equipped the funny gun!'
    duration: 5
arguments:
  OnShotWeapon: action Example
  OnAimedWeapon: Player::Damage(10, "Test", 'AIMING')
custom_item_type: Weapon
custom_data:
  damage: 2.75
  max_ammo: 150
  max_magazine_ammo: 150
  max_barrel_ammo: 15
  penetration: 1.24000001
  inaccuracy: 1.24000001
  aiming_inaccuracy: 1.24000001
  damage_falloff_distance: 1
  attachments: DotSight
  enable_friendly_fire: false
```
{% endcode %}
