# Use

**Description:**\
Runs the "use" action for the currently held custom item. If the custom item contains a command string that requires arguments, the command will substitute `#` placeholders with provided arguments before invoking the item's `ItemEvents.Command` handler.

**Command:**\
`.use`

**Behavior / logic summary:**

* Must be executed in-game (a `Player` must be available).
* Validates the player is holding a `CustomItem` of type `CustomItemType.Item`.
* Iterates `IItemData.Data` entries to find any `Command` strings that contain `#` placeholders.
* Counts the number of `#` placeholders and ensures the player supplied at least that many arguments; if not, returns an error showing required vs provided argument counts.
* Replaces each `#` with the corresponding argument (`#` are processed left-to-right).
* After substitution, the command reassigns the modified data and triggers the item
