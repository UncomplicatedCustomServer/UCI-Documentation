# Summoned

**Description**\
List every currently summoned custom item (both plugin-defined and API-defined), including their serial, id, status (pickup vs item), name, and current owner (if any).

**Command / Invocation**\
`uci summoned`

**Visible args**\
`(none)`

**Required permission**\
`uci.summoned`

**Aliases**\
(none)

**Example usage**\
`uci summoned`

**Behavior notes**

* Iterates `SummonedCustomItem.List` and `SummonedAPICustomItem.List` and produces a table-like output.
* Useful for debugging and admin oversight of spawned/custom items at runtime.
