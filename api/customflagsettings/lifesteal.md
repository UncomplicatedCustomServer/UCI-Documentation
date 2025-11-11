# LifeSteal

## CustomFlag: LifeSteal

**Description:** When the item has the LifeSteal flag, picking it up will heal the player a set amount (optionally scaled by a percentage).

**Parameters:**

* `life_steal_amount` — Base amount used in healing calculation.
* `life_steal_percentage` — Percentage to apply to the amount to compute healed health.\
  &#xNAN;_&#x48;ealedAmount = life\_steal\_amount \* life\_steal\_percentage_

**Example Yaml context:**

```yaml
flag_settings:
  life_steal_settings:
  - life_steal_amount: 8
    life_steal_percentage: 0.5
```
