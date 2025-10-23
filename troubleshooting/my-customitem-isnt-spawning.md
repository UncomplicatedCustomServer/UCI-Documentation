---
icon: triangle-exclamation
---

# My CustomItem isn't spawning!

It can be frustrating when a CustomItem you've configured doesn't appear for players. This guide provides a step-by-step process to diagnose and fix the most common issues.

***

#### Step 1: Check the Console for Errors

The first place to look for problems is your server console, especially during server startup or after running the `uci reload` command.

* **YAML Syntax Errors**: The framework will log an error if it cannot parse your `.yml` file. This is often due to incorrect indentation, a missing colon, or a typo. The error message will usually point to the problematic line.
* **Validation Warnings**: Even if the YAML is valid, the CustomItem might fail validation. The framework logs warnings for issues like:
  * A CustomItem `Id` is already in use by another CustomItem.
  * The data in `custom_data` doesn't match the specified CustomItem (e.g., trying to use `damage` in a `Painkillers` CustomItem).

> **Tip:** For more detailed logs, open the plugin's config file and set `Debug: true`. This will provide much more information in the console to help you diagnose the problem.

***

#### Step 2: Use the `uci list` Command

This is the most important diagnostic command. Run it in your server console and check the output.

* **✔ CustomItem is listed with a green check:** This means your setting was successfully loaded and registered. The problem is not with the file itself. **Proceed to Step 3.**
* **❌ CustomItem is listed with a red cross:** This means the setting was loaded but failed validation and was not registered. The console errors from Step 1 will tell you exactly what is wrong. Check for mismatches between your `CustomData` and the fields you provided.
* **Your CustomItem is not listed at all:** This means the framework did not find or could not read your file.
  * Ensure your file is in the correct directory: `configs/UncomplicatedCustomItems/`.
  * Make sure the file name ends with `.yml`.
  * Double-check for a critical syntax error in your YAML that prevents the file from being read entirely.

***

#### Step 3: Validate Spawn Configuration

If your `CustomItem` is correctly registered (**✔** green checkmark) but **not spawning in-game**, the problem is almost always due to misconfigured `spawn_data` in your YAML file. Use this checklist to debug:

#### DoSpawn

Make sure `do_spawn` is set to `true` in your YAML config. If it's `false`, the item will **never** spawn.

#### Count

Confirm the `count` value is set to at least `1`. If this is `0`, nothing will spawn.

**Spawn Location Settings**

Only **one** of the following spawn methods will be used, based on what is defined (in order of priority):

1. **PedestalSpawn**
   * If `pedestal_spawn` is `true`, your item will attempt to **replace an item in a SCP pedestal.**
   * If `replace_items_in_pedestals` is `false`, it won’t replace existing pedestal items.
2. **Coords**
   * If `coords` is not empty, the item will spawn at the listed **fixed world positions**.
   * Make sure the coordinates are valid for the map you're using.
3. **DynamicSpawn**
   * If `coords` is empty and `dynamic_spawn` is defined, it will try spawning in one of the listed **rooms** (e.g., `Lcz914`, `HczArmory`, etc.), based on their individual `chance` values.
4. **Zones**
   * If `coords` and `dynamic_spawn` are empty, the item will spawn randomly in the listed **zones** (e.g., `Entrance`, `HeavyContainment`).

**Pickup Replacement Settings**

* `replace_existing_pickup`: If `true`, the item will **replace an existing pickup** in the chosen spawn location.
  * If `force_item` is also `true`, it will **only replace pickups that match the item’s original `ItemType`.**
  * If `force_item` is `false`, it can replace any item randomly.

***

#### Step 4: Inspect the Loaded Data with `uci get`

You can see exactly how the framework has interpreted your YAML file by using the `uci get <ID>` command. This will display all the loaded properties for that CustomItem. It's a great way to confirm that all your values were parsed correctly and that there are no unexpected `null` or default values.

If you are still stuck after following these steps, it's best to ask for help. Provide your YAML file, your server log with debug enabled, and the output of the `uci list` command.
