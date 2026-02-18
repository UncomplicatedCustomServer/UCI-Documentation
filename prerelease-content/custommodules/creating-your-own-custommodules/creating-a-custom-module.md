---
icon: circle-play
---

# Creating a Custom Module

Custom Modules allow you to extend the behavior of Custom Items by hooking into game events and applying custom logic. This page will walk you through creating your own `CustomModuleBase` implementation and registering it with the plugin.

***

### Overview

A **Custom Module** is a class that inherits from `CustomModuleBase` and defines behavior to run when specific game events are fired. Each module is registered once globally and then instantiated per item when that item is summoned into the world.

Modules support:

* Declaring **required YAML arguments** to make them configurable
* Listening to **game events** via `RegisterEvents` / `UnregisterEvents`
* Running logic per-event via `Run(EventArgs)`
* Lifecycle hooks: `OnAdded`, `OnRegistered`, `OnDestroyed`

***

### Step 1: Create the Class

Create a new class that inherits from `CustomModuleBase`:

```csharp
using System;
using System.Collections.Generic;
using UncomplicatedCustomItems.API.CustomModuleAPI;
using UncomplicatedCustomItems.API.Features;

public class MyCustomModule : CustomModuleBase
{
    public override string Name => nameof(MyCustomModule);
}
```

The `Name` Property is the identifier used in YAML configuration to reference this module.

***

### Step 2: Declare Required Arguments

If your module needs configurable values, override `RequiredArguments`. These names map directly to the keys used in the item's YAML config:

```csharp
public override List<string> RequiredArguments =>
[
    "MyFloat",
    "MyInt",
];

public float MyFloat { get; set; }
public int MyInt { get; set; }
```

***

### Step 3: Parse Arguments in `OnAdded`

`OnAdded` is called once when the module is attached to a summoned item. Use it to parse and store your arguments:

```csharp
public override void OnAdded(SummonedCustomItem item)
{
    foreach (Dictionary<object, object> args in Arguments)
    {
        if (!args.TryGetValue<float>("MyFloat", out var myFloat))
        {
            LogManager.Warn($"{CustomItem.Name} - MyFloat is not a valid float!");
            return;
        }

        if (!args.TryGetValue<int>("MyInt", out var myInt))
        {
            LogManager.Warn($"{CustomItem.Name} - MyInt is not a valid int!");
            return;
        }

        MyFloat = myFloat;
        MyInt = myInt;
    }
}
```

> **Note:** Always validate and warn when an argument cannot be parsed. This helps server owners diagnose configuration mistakes quickly.

***

### Step 4: Register and Unregister Events

Override `RegisterEvents` and `UnregisterEvents` to subscribe your logic to game events:

```csharp
public override void RegisterEvents()
{
    PlayerEvents.ShotWeapon += Run;
}

public override void UnregisterEvents()
{
    PlayerEvents.ShotWeapon -= Run;
}
```

***

### Step 5: Implement `Run`

`Run(EventArgs eventArgs)` is your event handler. Always call `Check(eventArgs)` first — it verifies the event is relevant to the item this module instance belongs to:

```csharp
public override void Run(EventArgs eventArgs)
{
    if (!Check(eventArgs))
        return;

    // Your logic here
}
```

The `Check` method handles both `IPlayerEvent` and `IItemEvent` automatically. It returns `true` only if the event targets the correct item linked to this module instance.

***

### Step 6: Optional Lifecycle Hooks

You can also override the following for additional control:

| Method                        | When it's called                                        |
| ----------------------------- | ------------------------------------------------------- |
| `OnRegistered()`              | Once, when the module type is first registered globally |
| `OnAdded(SummonedCustomItem)` | Each time the module is attached to a spawned item      |
| `OnDestroyed()`               | When the item is despawned or destroyed                 |

***

### Step 7: Register Your Module

Modules are discovered automatically at startup if they are in a loaded plugin assembly. If you need to register manually (e.g. from your plugin's `OnEnabled`), use:

```csharp
CustomModuleManager.RegisterCustomModule<MyCustomModule>();
```

This is typically used when your module is defined in a separate plugin rather than the main assembly.

***

### Full Example

Below is a complete example of a module that regenerates ammo over time after the player fires:

{% code expandable="true" %}
```csharp
using System;
using System.Collections.Generic;
using LabApi.Events.Arguments.Interfaces;
using LabApi.Events.Handlers;
using LabApi.Features.Wrappers;
using UncomplicatedCustomItems.API.CustomModuleAPI;
using UncomplicatedCustomItems.API.Extensions;
using UncomplicatedCustomItems.API.Features;
using UncomplicatedCustomItems.API.Features.Helper;

public class AmmoRegen : CustomModuleBase
{
    public override string Name => "AmmoRegen";

    public override List<string> RequiredArguments =>
    [
        "RegenDelay",
        "RegenInterval",
        "AmmoPerInterval",
    ];

    public float RegenDelay { get; set; }
    public float RegenInterval { get; set; }
    public int AmmoPerInterval { get; set; }

    public override void OnAdded(SummonedCustomItem item)
    {
        foreach (Dictionary<object, object> args in Arguments)
        {
            if (!args.TryGetValue<float>("RegenDelay", out var regenDelay))
            {
                LogManager.Warn($"{CustomItem.Name} - RegenDelay is not a valid float!");
                return;
            }

            if (!args.TryGetValue<float>("RegenInterval", out var regenInterval))
            {
                LogManager.Warn($"{CustomItem.Name} - RegenInterval is not a valid float!");
                return;
            }

            if (!args.TryGetValue<int>("AmmoPerInterval", out var ammoPerInterval))
            {
                LogManager.Warn($"{CustomItem.Name} - AmmoPerInterval is not a valid int!");
                return;
            }

            RegenDelay = regenDelay;
            RegenInterval = regenInterval;
            AmmoPerInterval = ammoPerInterval;
        }
    }

    public override void Run(EventArgs eventArgs)
    {
        if (!Check(eventArgs))
            return;

        if (eventArgs is IItemEvent itemEvent)
        {
            if (!Utilities.TryGetSummonedCustomItem(itemEvent.Item.Serial, out var item))
                return;

            item.PauseAmmoRegen(itemEvent.Item as FirearmItem, RegenDelay);
        }
    }

    public override void RegisterEvents()
    {
        PlayerEvents.ShotWeapon += Run;
    }

    public override void UnregisterEvents()
    {
        PlayerEvents.ShotWeapon -= Run;
    }
}
```
{% endcode %}

***

### YAML Configuration

Once registered, your module can be referenced in any custom item's YAML config:

```yaml
CustomModules:
  AmmoRegen:
    - RegenDelay: 2.0
      RegenInterval: 0.5
      AmmoPerInterval: 1
```

The key must match the module's `Name` property exactly (case-insensitive).
