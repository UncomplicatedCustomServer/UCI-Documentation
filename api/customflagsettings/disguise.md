# Disguise

## CustomFlag: Disguise

**Description:** Disguises the player as another role (recommended for armor). Options include reveal on damage and custom info string.

**Parameters:**

* `reveal_when_damaged` — If `true`, disguise is removed when player is damaged.
* `role_id` — Role to disguise as (e.g., `NtfSpecialist`).
* `disguise_message` — Message shown to the disguised player.
* `custom_info` — Custom information string (optional).

**Example Yaml context:**

```yaml
flag_settings:
  disguise_settings:
  - reveal_when_damaged: false
    role_id: NtfSpecialist
    disguise_message: 'Your are disguised as an NtfSpecialist!'
    custom_info: ''
```
