# CantDrop

## CustomFlag: CantDrop

**Description:** Prevents the item from being dropped and optionally shows a hint or broadcast.

**Parameters:**

* `hint_or_broadcast` — `hint` or `broadcast` (how message is shown).
* `message` — Text shown to the player (supports placeholders like `%name%`).
* `duration` — Duration (seconds) for the message/hint.

**Example Yaml context:**

```yaml
flag_settings:
  cant_drop_settings:
  - hint_or_broadcast: hint
    message: "You cant drop %name%!"
    duration: 10
```
