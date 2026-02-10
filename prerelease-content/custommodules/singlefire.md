---
icon: circle-1
---

# SingleFire

The `SingleFire` custom module enforces single-shot behavior for firearms. It prevents players from reloading more than one round at a time, ensures that only one round is chambered after reloading, and resets the magazine to empty after firing.

### Configuration

| Value  | Description                                           |
| ------ | ----------------------------------------------------- |
| `Name` | The name of the custom module, which is "SingleFire". |

### Example

```yaml
custom_modules:
  SingleFire: []
```
