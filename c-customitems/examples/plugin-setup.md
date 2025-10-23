---
description: An example of how to setup a Exiled plugin
---

# Plugin Setup

```csharp
using Exiled.API.Enums;
using Exiled.API.Features;
using System;
using System.IO;
using System.Threading.Tasks;
using System.Collections.Generic;
using UnityEngine;
using PlayerEvent = Exiled.Events.Handlers.Player;
using ServerEvent = Exiled.Events.Handlers.Server;

namespace Example
{
    public class Plugin : Plugin<Config>
    {
        public override string Name => "Example";

        public override string Prefix => "Ex";

        public override string Author => "Mr. Baguetter";

        public override Version RequiredExiledVersion { get; } = new(9, 6, 1);

        public override Version Version { get; } = new(1, 0, 0);

        internal Events.EventHandler Handler;

        public override PluginPriority Priority => PluginPriority.First;

        public static Plugin Instance { get; private set; }

        public override void OnEnabled()
        {
            Instance = this;
            PlayerEvent.DroppedItem += Handler.OnOwnerDroppedItem;
            base.OnEnabled();
        }

        public override void OnDisabled()
        {
            PlayerEvent.DroppedItem -= Handler.OnOwnerDroppedItem;
            base.OnDisabled();
        }
    }
}
```
