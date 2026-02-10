---
icon: volume-high
---

# CustomAudio

This module allows custom items to play a specified audio clip whenever a configured player event occurs. It provides precise control over the audio file, volume, and audible distance, making custom items more interactive based on player actions.

### Configuration

| Value             | Description                                                                                                                                 |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `Trigger`         | Defines the player event(s) that will cause the audio to play. This is a flags enum, meaning multiple events can be combined (e.g., \`OnUse |
| `AudioPath`       | The relative path to the audio file that should be played. This path is relative to the `UncomplicatedCustomItems` plugin's data directory. |
| `AudibleDistance` | A floating-point number specifying the maximum distance in meters from the player's position at which the audio can be heard.               |
| `SoundVolume`     | A floating-point number representing the volume of the audio clip. A value of `1.0` is full volume.                                         |

### Example

```yaml
custom_modules:
  CustomAudio:
  - Trigger: OnUse | OnDropped
     AudioPath: CustomItems/Sounds/MysteriousSound.ogg # Path to your audio file
     AudibleDistance: 20.0 # Can be heard up to 20 meters away
     SoundVolume: 0.7 # Plays at 70% volume
```
