# 🐀 Capybara

This custom module integrates with the `UncomplicatedCustomItems` system to dynamically manage a "CapybaraToy" instance in response to specific player actions. When a player uses an item or picks up an item, a large `CapybaraToy` is spawned near them, the player's own scale is modified, and a "Fade" visual effect is applied. Conversely, when a player drops an item or dies, the associated `CapybaraToy` is destroyed, the player's scale reverts to normal, and the "Fade" effect is removed. This module creates a unique visual and interactive effect tied to player item management.

#### Configuration

| Value | Description                                                     |
| ----- | --------------------------------------------------------------- |
| _N/A_ | This module does not expose any custom configurable properties. |

#### Example

Below is an example of how to include the `Capybara` module in your `UncomplicatedCustomItems` configuration. Since there are no custom properties for this module, you only need to specify its name.

```yaml
custom_modules:
  Capybara: []
```
