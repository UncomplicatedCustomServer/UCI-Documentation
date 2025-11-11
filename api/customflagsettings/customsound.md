# CustomSound

## CustomFlag: CustomSound

**Description:** Play a custom audio clip when used. Configure path, audible range, and volume.

**Parameters:**

* `audio_path` — Path to the audio file (relative or absolute).
* `audible_distance` — Distance (units) at which the audio can be heard.
* `sound_volume` — Volume percent (0–100 or plugin-defined scale).

**Example Yaml context:**

```yaml
flag_settings:
  audio_settings:
  - audio_path: '~/.config/SCP Secret Laboratory/LabAPI/configs/UncomplicatedCustomItems/Example.ogg'
    audible_distance: 20
    sound_volume: 20
```
