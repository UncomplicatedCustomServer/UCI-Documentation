---
icon: square-exclamation
---

# My custom flags aren't working!

If your custom item's flags (e.g., `InfiniteAmmo`, `LifeSteal`) are not functioning as expected, consider the following:

1. **Correctly define the `CustomFlags`**: In your `.yml` file, make sure the `CustomFlags` are listed correctly. You can combine multiple flags using a comma-separated list (e.g., `CustomFlags: InfiniteAmmo, LifeSteal`).
2. **Configure the `FlagSettings`**: Some flags require additional configuration in the `FlagSettings` section. For example, the `LifeSteal` flag needs `LifeStealSettings` to define the amount of health stolen. If you don't provide these settings, the flag may not work correctly.
3. **Check for dependencies**: Some flags, like `CustomSound`, require additional plugins like `AudioPlayerApi` and `NVorbis` to be installed on your server. If these dependencies are missing, the flag will not work.
