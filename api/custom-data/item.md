---
description: >-
  The `ItemData` class is used for custom items of type `Item`. It allows you to
  define custom actions and messages for items.
icon: pencil
---

# Item

**Properties**

| Property            | Type         | Description                                                    |
| ------------------- | ------------ | -------------------------------------------------------------- |
| `Event`             | `ItemEvents` | The event that triggers the item's action.                     |
| `Command`           | `string`     | The command to be executed when the event is fired.            |
| `CoolDown`          | `float`      | The delay after the event is fired.                            |
| `ConsoleMessage`    | `string`     | The message to be sent to the console when the event is fired. |
| `BroadcastMessage`  | `string`     | The message to be broadcast when the event is fired.           |
| `BroadcastDuration` | `ushort`     | The duration of the broadcast.                                 |
| `HintMessage`       | `string`     | The message to be shown as a hint when the event is fired.     |
| `HintDuration`      | `float`      | The duration of the hint.                                      |
| `DestroyAfterUse`   | `bool`       | Whether the item should be destroyed after use.                |

**Example:**

```yaml
CustomItemType: Item
CustomData:
CustomItemType: Item
CustomData:
- event: Use
  command: "say A custom item was used!"
  cool_down: 5.0
  console_message: "Custom item used by a player."
  broadcast_message: "A special item has been activated!"
  broadcast_duration: 3
  hint_message: "You used the special item."
  hint_duration: 2.5
  destroy_after_use: true
```
