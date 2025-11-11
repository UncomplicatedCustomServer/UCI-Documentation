# List

**Description**\
Lists every registered CustomItem, API CustomItem, and CustomAction, along with unregistered items and counts.

**Command / Invocation**\
`uci list`

**Visible args**\
`(none)`

**Required permission**\
`uci.list`

**Aliases**\
`l`

**Example usage**\
`uci list`

**Behavior notes**

* Lists registered custom items with id and name.
* If there are unregistered custom items, lists them separately.
* Also lists API custom items and custom actions with counts.
* Returns a nicely formatted text block indicating how many items/actions are registered/unregistered.
