# Generate

**Description**\
Generate a new custom item file/config in the plugin’s file system using the given parameters.

**Command / Invocation**\
`uci generate <id> <Name> <ItemType> <CustomItemType> <Description>`&#x20;

**Visible args**\
`Id, Name, ItemType, CustomItemType, Description`

**Required args / validation**\
Requires at least 5 arguments. The first argument must be a valid unsigned integer ID.

**Required permission**\
`uci.generate`

**Aliases**\
`gen`

**Example usage**\
`uci generate 999 "My Item" GunCOM15 Item "A generated test item"`

**Behavior notes**

* Validates the item id and the enum values for `ItemType` and `CustomItemType`.
* Calls the plugin FileConfig to actually create the new custom item.
* Returns success/failure with info about the generated item.
