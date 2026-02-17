---
icon: cloud-check
---

# Backup

**Description**\
Backup your CustomItems to the UCI API.

**Command / Invocation**\
`uci backup <upload|download>`

**Visible args**\
`<type>` — `upload`, or `download`.

**Required permission**\
`uci.backup`

**Aliases**\
`back`

**Example usage**\
`uci backup download` — Downloads the latest uploaded CustomItems to the backup directory.\
`uci backup upload` — Uploads all the Customitem files in the UncomplicatedCustomItems directory.
