# HealOnKill

## CustomFlag: HealOnKill

**Description:** Heals the user when they kill another player. Optionally converts heal to AHP (aux HP) if full.

**Parameters:**

* `heal_amount` — Amount of health restored on kill.
* `convert_to_ahp_if_full` — If `true`, convert heal to AHP if player's HP is full.

**Example Yaml context:**

```yaml
flag_settings:
  heal_on_kill_settings:
  - heal_amount: 1
    convert_to_ahp_if_full: false
```
