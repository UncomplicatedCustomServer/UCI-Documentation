---
description: >-
  A example of how to setup a event to trigger a specific action for a
  CustomItem
---

# Event Example

```csharp
namespace Example.Events
{    
    public class EventHandler
    {
        public void OnOwnerDroppedItem(DroppedItemEventArgs ev)
        {
            if (!Utilities.TryGetSummonedCustomItem(ev.Item.Serial, out SummonedCustomItem item))
                return;
                
            if (item.CustomItem.Id == 1)
                item.AddAttachment("HoloSight");
        }
    }
}
```
