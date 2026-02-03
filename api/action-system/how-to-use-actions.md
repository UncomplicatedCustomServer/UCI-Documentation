---
description: 'Note: The properties shown here may not be real properties'
---

# How to use Actions

## Using the Action System

{% hint style="warning" %}
The Action System is based on LabApi, regardless of whether you're using the Exiled version of UCI.
{% endhint %}

The UncomplicatedCustomItems (UCI) plugin includes a powerful, text-based action system that allows you to create complex and dynamic behaviors for your custom items and events without writing any C# code. This guide will walk you through the syntax and features of this system.

### Introduction

At its core, the action system executes a series of commands defined as simple strings. These strings can be used in your custom item configurations or within custom action definitions.

An action is defined in a YAML file like this:

```yaml
Id: 101
Name: Super Heal Potion
Description: A potion that heals you and tells everyone.
Actions:
  - 'if {Player.Health} < 100 then Heal {Player.UserId} 25 & Broadcast 5 "{Player.DisplayName} used a Super Heal Potion!"'
  - '{Player.StaminaRemaining} += 50.0'
```

Each string in the `Actions` list is a command that will be executed in order. Let's break down the features.

***

### Core Concepts

#### 1. Placeholders

Placeholders allow you to get dynamic data from the game state at the moment the action is executed. They are always enclosed in curly braces `{}`.

You can access properties of objects available in the current event context (like `Player`, `Item`, `Target`, etc.).

**Syntax:** `{Object.Property.SubProperty}`

**Examples:**

* `{Player.Health}`: Gets the current health of the player who triggered the action.
* `{Player.Position}`: Gets the player's current world position.
* `{Item.Serial}`: Gets the serial number of the custom item.

#### 2. Collection Operations

If a placeholder resolves to a collection of objects (like a list of all players), you can perform operations on it.

**Syntax:** `{Collection.Operation}`

**Supported Operations:**

* `.Random`: Gets a random element from the collection.
* `.First`: Gets the first element.
* `.Last`: Gets the last element.
* `.Count`: Gets the number of elements in the collection.
* `.Any`: Returns `true` if the collection has any elements, `false` otherwise.

**Example:**

* `{Player.ReadyList.Random.DisplayName}`: Gets the display name of a random player on the server.
* `{Player.ReadyList.Count}`: Gets the total number of players.

#### 3. Collection Indexing & Predicates

You can select a specific item from a collection by its index or by a property value.

**Syntax:**

* By index: `{Collection[index]}`
* By property match: `{Collection[PropertyName="Value"]}`

**Examples:**

* `{Player.ReadyList[0].DisplayName}`: Gets the name of the first player in the list.
* `{Player.ReadyList[RoleType="Scp173"].UserId}`: Gets the User ID of the first player who is SCP-173.

***

### Conditional Logic (`if`/`unless`)

You can execute actions only when certain conditions are met using `if` and `unless`.

**Syntax:**

* `if <condition> then <action>`
* `if <condition> then <action> else <another_action>`
* `unless <condition> then <action>` (Executes if the condition is false)

To chain multiple actions within a `then` or `else` block, separate them with an ampersand `&`.

#### Supported Operators

| Operator   | Description                              | Example                                      |
| ---------- | ---------------------------------------- | -------------------------------------------- |
| `==`       | Equal to                                 | `{Player.Role} == Scp173`                    |
| `!=`       | Not equal to                             | `{Player.Health} != 100`                     |
| `>`        | Greater than                             | `{Server.Players.Count} > 5`                 |
| `<`        | Less than                                | `{Player.Health} < 50`                       |
| `>=`       | Greater than or equal to                 | `{Player.Ammo[AmmoType.Nato9]} >= 30`        |
| `<=`       | Less than or equal to                    | `{Player.Stamina} <= 10.0`                   |
| `contains` | Checks if a string contains a substring. | `{Player.DisplayName} contains "Admin"`      |
| `is`       | Checks the type of an object.            | `{Target} is Player`                         |
| `equals`   | Case-insensitive string equality.        | `{Player.CurrentRoom.Name} equals "HCZ_106"` |

#### Examples

**Simple `if`:**

```yaml
Actions:
  - 'if {Player.Health} < 25 then Heal {Player.UserId} 50'
```

**`if/else` with Chained Actions:**

```yaml
Actions:
  - 'if {Player.Zone} == HeavyContainment then Broadcast 5 "You are in the right zone!" & AddItem {Player.UserId} KeycardO5 else Broadcast 5 "You are in the wrong zone!" & Damage {Player.UserId} 10 "Magic"'
```

***

### Modifying Properties (Assignments)

You can directly change the properties of objects using assignment operators.

**Syntax:** `{Object.Property} <operator> <value>`

#### Supported Operators

| Operator | Description                      | Example                    |
| -------- | -------------------------------- | -------------------------- |
| `=`      | Assign                           | `{Player.Health} = 100`    |
| `+=`     | Add (or concatenate for strings) | `{Player.Health} += 25`    |
| `-=`     | Subtract                         | `{Player.Health} -= 10`    |
| `*=`     | Multiply                         | `{Player.Hint} *= 2`       |
| `/=`     | Divide                           | `{Player.Stamina} /= 1.5`  |
| `%=`     | Modulo                           | `{Player.CustomInfo} %= 5` |

#### Example

```yaml
Actions:
  - '{Player.Health} = {Player.MaxHealth}' # Sets health to its maximum value
  - '{Player.StaminaRemaining} += 50' # Adds 50 stamina
  - '{Player.DisplayName} = "The Chosen One"' # Changes the player's display name
```

***

### Advanced Features

#### 1. Calling C# Methods

This is one of the most powerful features. You can call almost any public C# method on an object or a static class.

**Syntax:** `TargetObject::MethodName(parameter1, parameter2, ...)`

* `TargetObject`: Can be a placeholder (`{Player}`), a static class (`Server`), or even a newly created object.
* `MethodName`: The name of the method to call.
* `parameters`: The arguments to pass to the method. These can be strings, numbers, booleans, or other placeholders.

**Common Type Shortcuts:** The system has shortcuts for common game types, so you don't need to write the full namespace.

| Shortcut  | Full Type                         |
| --------- | --------------------------------- |
| `Player`  | `LabApi.Features.Wrappers.Player` |
| `Server`  | `LabApi.Features.Wrappers.Server` |
| `Map`     | `LabApi.Features.Wrappers.Map`    |
| `Vector3` | `UnityEngine.Vector3`             |
| `Timing`  | `MEC.Timing`                      |

**Examples:**

**Calling a method on a player:**

```yaml
# Kills the player with a custom damage reason
Actions:
  - '{Player}::Kill("You angered the gods")'
```

**Calling a static method:**

```yaml
# Announces a cassie message
Actions:
  - 'Cassie::Announce("pitch_0.5 .g7", false, true, true)'
```

**Creating a new object (`.new` syntax):**

```yaml
# Spawns a primitive object 10 units above the player
Actions:
  - 'Map::SpawnPrimitive(PrimitiveType.Cube, {Player.Position} + UnityEngine.Vector3.new(0, 10, 0), null, null, true)'
```

#### 2. Executing Other Custom Actions

You can trigger another `CustomAction` from within an action.

**Syntax:**

* `action <Action Name>`
* `action <Action ID>`

**Example:** Imagine you have another action defined with the name "Global Cooldown Effect".

```yaml
Actions:
  - 'Heal {Player.UserId} 100'
  - 'action "Global Cooldown Effect"'
```

#### 3. Local Variables

For complex action sequences, you can store values in temporary variables.

**Syntax:** `let <variable_name> = <value or placeholder>`

The variable can then be used in subsequent actions within the same execution sequence.

**Example:**

```yaml
Actions:
  - 'let savedPos = {Player.Position}'
  - 'after 5s then {Player}::SetPosition(savedPos)'
```

> _Note: The variable `savedPos` only exists for this specific trigger. It is not saved globally._

#### 4. Delayed Actions

You can delay the execution of an action.

**Syntax:** `after <duration> then <action>`

**Duration Suffixes:**

* `ms`: milliseconds
* `s`: seconds (default if no suffix)
* `m`: minutes

**Example:**

```yaml
Actions:
  - 'Broadcast 10 "A bomb has been planted!"'
  - 'after 30s then Map::Explode({Player.Position}, ExplosionType.Grenade, 10, true)'
```

***

### Putting It All Together: A Complex Example

Let's create a "Gambler's Medkit" that has a 50% chance to heal you and a 50% chance to hurt you.

**CustomAction Definition (`gambler_effect.yml`):**

```yaml
Id: 501
Name: Gambler Effect
Description: The core logic for the Gambler's Medkit.
Actions:
  - 'let randomNumber = UnityEngine.Random::Range(0, 2)' # Generates a random number: 0 or 1
  - 'if {randomNumber} == 0 then Heal {Player.UserId} 75 & Broadcast 5 "{Player.DisplayName} got lucky!" else Damage {Player.UserId} 25 "Bad luck" & Broadcast 5 "{Player.DisplayName} was unlucky!"'
```

**CustomItem Definition:**

```yaml
Id: 205
Name: Gambler's Medkit
Type: Medkit

Arguments:
  OnUsedItem: 'action "Gambler Effect"'
  
  # Multi-line example
  OnChangedItem: |
    after 250ms Player::Damage(1, "Recoil", "FunnyGun");
    Log FunnyGun equiped by {Player.Nickname};
```

When a player uses the "Gambler's Medkit", it triggers the `Used` event, which in turn executes the "Gambler Effect" action. This action then runs the conditional logic to either heal or damage the player.
