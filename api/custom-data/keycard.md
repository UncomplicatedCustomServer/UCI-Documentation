---
description: >-
  The 'KeycardData' class is used for custom items of type `Keycard`. It allows
  you to customize the properties of keycards.
icon: credit-card
---

# Keycard

**Properties**

| Property           | Type     | Description                                                             |
| ------------------ | -------- | ----------------------------------------------------------------------- |
| `Containment`      | `int`    | The containment access level (0-3).                                     |
| `Armory`           | `int`    | The armory access level (0-3).                                          |
| `Admin`            | `int`    | The admin/management access level (0-3).                                |
| `TintColor`        | `string` | The main background color of the keycard (hex code).                    |
| `PermissionsColor` | `string` | The color of the permission indicators (hex code).                      |
| `Name`             | `string` | The primary name displayed on the keycard.                              |
| `Label`            | `string` | The secondary label displayed on the keycard.                           |
| `SerialNumber`     | `string` | The serial number displayed on the keycard (12 digits).                 |
| `WearDetail`       | `byte`   | The wear detail of the keycard.                                         |
| `LabelColor`       | `string` | The color of the label text (hex code).                                 |
| `Rank`             | `int`    | The rank shown on the card.                                             |
| `OneTimeUse`       | `bool`   | Whether the keycard is consumed after one use.                          |
| `OneTimeUseHint`   | `string` | The hint shown after the keycard is consumed (if `OneTimeUse` is true). |

**Example:**

```yaml
CustomItemType: Keycard
CustomData:
  containment: 2
  armory: 1
  admin: 3
  tint_color: "#0000FF"
  permissions_color: "#FFFFFF"
  name: "Dr. Bright"
  label: "Site Director"
  serial_number: "123456789012"
  wear_detail: 0
  label_color: "#FFFF00"
  rank: 5
  one_time_use: false
  one_time_use_hint: "Your keycard has been deactivated."
```
