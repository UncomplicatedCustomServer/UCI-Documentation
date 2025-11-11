# Errors

**Description**\
Gets any errors that occurred when loading a CustomItem and provides helpful YAML-related suggestions where possible.

**Command / Invocation**\
`uci errors [id]`&#x20;

**Visible args**\
`[id]` — optional, filter results to a specific custom item id or name.

**Required permission**\
`uci.errors`

**Aliases**\
`er`

**Example usage**\
`uci errors` — lists all current load errors.\
`uci errors 42` — lists load errors for ID `42`.\
`uci errors MyItemName` — lists load errors for `MyItemName`.

**Behavior notes**

* If no errors exist, returns a friendly message.
* If an `id` is supplied it filters and returns only errors matching that `id` (numeric or string).
* Outputs helpful metadata (file name, YAML line/column when available) and a suggested fix based on the exception message.
* Suggestions are heuristics mapped from common `YamlException` messages.
