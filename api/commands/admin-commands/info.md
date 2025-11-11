# Info

**Description**\
Get detailed info on a registered custom item. Includes spawn configuration, active custom flags and their settings, spawn counts, and formatted property output.

**Command / Invocation**\
`uci info <Item Id>`

**Visible args**\
`<Item Id>`

**Required permission**\
`uci.info`

**Aliases**\
`info`

**Example usage**\
`uci info 42`

**Behavior notes**

* Validates the custom item exists.
* Builds a formatted string with: name, id, item type, scale/weight, spawn info (does it spawn? spawn coords/dynamic/zones and counts), custom flags, and detailed settings for the active flags.
* Processes flag settings reflectively: looks at properties in the `FlagSettings` object and prints properties with icons and friendly display names.
* Handles lists vs single-value settings and tries to map property names to icons and colors (e.g., `GlowColor` sets a color variable used for ItemGlow sections).
