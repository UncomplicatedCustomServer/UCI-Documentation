---
icon: diamond-exclamation
---

# My custom item doesn't have the correct properties!

If your custom item appears in-game but doesn't have the correct properties (e.g., a weapon with incorrect damage, a keycard with the wrong access levels), check the following:

1. **Verify the `CustomItemType` and `Item` type**: The `CustomItemType` in your `.yml` file must match the base `Item` type. For example, if you set `CustomItemType` to `Weapon`, the `Item` must be a weapon (e.g., `GunCOM18`).
2. **Check your `CustomData` formatting**: The `CustomData` section of your `.yml` file must be correctly formatted for the specified `CustomItemType`. For instance, a `Weapon` requires properties like `damage`, `max_ammo`, etc., while a `Keycard` needs `containment`, `armory`, and `admin` levels.
3. **Inspect the `CustomData` properties**: Ensure that all the properties in your `CustomData` are spelled correctly and have the correct data types (e.g., `float` for damage, `int` for ammo, `string` for a keycard's name).
