---
icon: circle-play
---

# Intro

Creating `CustomItems` in C# expands the capabilities of your custom content beyond what the **UncomplicatedCustomItems (UCI)** framework provides out of the box. By implementing your logic in C#, you gain full control over item behavior, interaction, and integration with other plugins or systems.

### Features:

#### Full Control

Use C# to fully control how your custom item behaves on pickup, drop, use, damage, death, etc.

#### Not Limited to CustomFlags

You are no longer limited to predefined `CustomFlags`.\
Implement your own logic by subscribing to Exiled Events and/or LabAPI Events.

### Getting Started:

To create a C# CustomItem:

1. Install [Visual Studio](https://visualstudio.microsoft.com/) or [Rider](https://www.jetbrains.com/rider/).
2. Reference UCI in your plugin project.
3. Create a class that implements `CustomItem`.
4. Add the `PluginCustomItem` Attribute.

### LabAPI/Exiled Events

You can hook into server events (like deaths, shooting, or player joins) using Exiled or LabAPI. This gives you fine-grained control over how your item reacts to gameplay events.



### Jump in

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h4><span data-gb-custom-inline data-tag="emoji" data-code="1f4cb">📋</span></h4></td><td><strong>Examples</strong></td><td>Examples to create your first C# CustomItem</td><td></td><td></td><td><a href="examples/">examples</a></td></tr></tbody></table>

