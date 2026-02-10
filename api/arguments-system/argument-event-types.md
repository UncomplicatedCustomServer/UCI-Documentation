# Argument Event Types

The `ArgumentType` enum serves as a comprehensive map for all player-related events in the framework. Each member of this enum corresponds to a specific event.

This provides a clear and strongly-typed way to work with a wide variety of player actions and state changes.

> **Key Concept: Pre-events vs. Post-events** You will notice a common pattern in the enum names: `...ing` vs. `...ed`.
>
> * **`On...ing` (e.g., `OnHurting`)**: These are **pre-events**. They are fired _before_ an action occurs. They are often cancellable (e.g., you can prevent a player from taking damage) and allow you to modify the outcome.
> * **`On...ed` (e.g., `OnHurt`)**: These are **post-events**. They are fired _after_ an action has already completed. You cannot cancel the action at this point, but you can react to it (e.g., log the damage, give the player an effect).

### Player Connection & State

Events related to a player's connection status, identity, and core state.

| Enum Member           | Associated Event Arguments Class   |
| --------------------- | ---------------------------------- |
| `OnJoined`            | `PlayerJoinedEventArgs`            |
| `OnLeft`              | `PlayerLeftEventArgs`              |
| `OnPreAuthenticating` | `PlayerPreAuthenticatingEventArgs` |
| `OnPreAuthenticated`  | `PlayerPreAuthenticatedEventArgs`  |
| `OnChangingNickname`  | `PlayerChangingNicknameEventArgs`  |
| `OnChangedNickname`   | `PlayerChangedNicknameEventArgs`   |
| `OnGroupChanging`     | `PlayerGroupChangingEventArgs`     |
| `OnGroupChanged`      | `PlayerGroupChangedEventArgs`      |
| `OnChangingRole`      | `PlayerChangingRoleEventArgs`      |
| `OnChangedRole`       | `PlayerChangedRoleEventArgs`       |
| `OnSpawning`          | `PlayerSpawningEventArgs`          |
| `OnSpawned`           | `PlayerSpawnedEventArgs`           |
| `OnEscaping`          | `PlayerEscapingEventArgs`          |
| `OnEscaped`           | `PlayerEscapedEventArgs`           |
| `OnChangedSpectator`  | `PlayerChangedSpectatorEventArgs`  |

### Player Moderation & Reporting

Events for administrative actions like banning, kicking, and muting, as well as player reporting.

| Enum Member          | Associated Event Arguments Class  |
| -------------------- | --------------------------------- |
| `OnBanning`          | `PlayerBanningEventArgs`          |
| `OnBanned`           | `PlayerBannedEventArgs`           |
| `OnKicking`          | `PlayerKickingEventArgs`          |
| `OnKicked`           | `PlayerKickedEventArgs`           |
| `OnMuting`           | `PlayerMutingEventArgs`           |
| `OnMuted`            | `PlayerMutedEventArgs`            |
| `OnUnmuting`         | `PlayerUnmutingEventArgs`         |
| `OnUnmuted`          | `PlayerUnmutedEventArgs`          |
| `OnReportingCheater` | `PlayerReportingCheaterEventArgs` |
| `OnReportedCheater`  | `PlayerReportedCheaterEventArgs`  |
| `OnReportingPlayer`  | `PlayerReportingPlayerEventArgs`  |
| `OnReportedPlayer`   | `PlayerReportedPlayerEventArgs`   |

### Health, Damage & Effects

Events related to a player's health, taking damage, and status effects.

| Enum Member                | Associated Event Arguments Class        |
| -------------------------- | --------------------------------------- |
| `OnDying`                  | `PlayerDyingEventArgs`                  |
| `OnDeath`                  | `PlayerDeathEventArgs`                  |
| `OnHurting`                | `PlayerHurtingEventArgs`                |
| `OnHurt`                   | `PlayerHurtEventArgs`                   |
| `OnUpdatingEffect`         | `PlayerEffectUpdatingEventArgs`         |
| `OnUpdatedEffect`          | `PlayerEffectUpdatedEventArgs`          |
| `OnDamagingShootingTarget` | `PlayerDamagingShootingTargetEventArgs` |
| `OnDamagedShootingTarget`  | `PlayerDamagedShootingTargetEventArgs`  |
| `OnDamagingWindow`         | `PlayerDamagingWindowEventArgs`         |
| `OnDamagedWindow`          | `PlayerDamagedWindowEventArgs`          |

### Item & Inventory Management

Events for all interactions involving items, including picking up, dropping, and using them.

| Enum Member             | Associated Event Arguments Class     |
| ----------------------- | ------------------------------------ |
| `OnChangingItem`        | `PlayerChangingItemEventArgs`        |
| `OnChangedItem`         | `PlayerChangedItemEventArgs`         |
| `OnDroppingAmmo`        | `PlayerDroppingAmmoEventArgs`        |
| `OnDroppedAmmo`         | `PlayerDroppedAmmoEventArgs`         |
| `OnDroppingItem`        | `PlayerDroppingItemEventArgs`        |
| `OnDroppedItem`         | `PlayerDroppedItemEventArgs`         |
| `OnPickingUpAmmo`       | `PlayerPickingUpAmmoEventArgs`       |
| `OnPickedUpAmmo`        | `PlayerPickedUpAmmoEventArgs`        |
| `OnPickingUpArmor`      | `PlayerPickingUpArmorEventArgs`      |
| `OnPickedUpArmor`       | `PlayerPickedUpArmorEventArgs`       |
| `OnPickingUpItem`       | `PlayerPickingUpItemEventArgs`       |
| `OnPickedUpItem`        | `PlayerPickedUpItemEventArgs`        |
| `OnPickingUpScp330`     | `PlayerPickingUpScp330EventArgs`     |
| `OnPickedUpScp330`      | `PlayerPickedUpScp330EventArgs`      |
| `OnSearchingAmmo`       | `PlayerSearchingAmmoEventArgs`       |
| `OnSearchedAmmo`        | `PlayerSearchedAmmoEventArgs`        |
| `OnSearchingArmor`      | `PlayerSearchingArmorEventArgs`      |
| `OnSearchedArmor`       | `PlayerSearchedArmorEventArgs`       |
| `OnSearchingPickup`     | `PlayerSearchingPickupEventArgs`     |
| `OnSearchedPickup`      | `PlayerSearchedPickupEventArgs`      |
| `OnThrowingItem`        | `PlayerThrowingItemEventArgs`        |
| `OnThrewItem`           | `PlayerThrewItemEventArgs`           |
| `OnThrowingProjectile`  | `PlayerThrowingProjectileEventArgs`  |
| `OnThrewProjectile`     | `PlayerThrewProjectileEventArgs`     |
| `OnUsingItem`           | `PlayerUsingItemEventArgs`           |
| `OnUsedItem`            | `PlayerUsedItemEventArgs`            |
| `OnCancellingUsingItem` | `PlayerCancellingUsingItemEventArgs` |
| `OnCancelledUsingItem`  | `PlayerCancelledUsingItemEventArgs`  |

### Weapon Handling

Events specific to interacting with weapons, such as shooting, reloading, and changing attachments.

| Enum Member                 | Associated Event Arguments Class         |
| --------------------------- | ---------------------------------------- |
| `OnAimedWeapon`             | `PlayerAimedWeaponEventArgs`             |
| `OnDryFiringWeapon`         | `PlayerDryFiringWeaponEventArgs`         |
| `OnDryFiredWeapon`          | `PlayerDryFiredWeaponEventArgs`          |
| `OnReloadingWeapon`         | `PlayerReloadingWeaponEventArgs`         |
| `OnReloadedWeapon`          | `PlayerReloadedWeaponEventArgs`          |
| `OnShootingWeapon`          | `PlayerShootingWeaponEventArgs`          |
| `OnShotWeapon`              | `PlayerShotWeaponEventArgs`              |
| `OnUnloadingWeapon`         | `PlayerUnloadingWeaponEventArgs`         |
| `OnUnloadedWeapon`          | `PlayerUnloadedWeaponEventArgs`          |
| `OnChangingAttachments`     | `PlayerChangingAttachmentsEventArgs`     |
| `OnChangedAttachments`      | `PlayerChangedAttachmentsEventArgs`      |
| `OnSendingAttachmentsPrefs` | `PlayerSendingAttachmentsPrefsEventArgs` |
| `OnSentAttachmentsPrefs`    | `PlayerSentAttachmentsPrefsEventArgs`    |

### Player Actions & Movement

Events triggered by specific player actions and changes in movement or location.

| Enum Member                 | Associated Event Arguments Class         |
| --------------------------- | ---------------------------------------- |
| `OnJumped`                  | `PlayerJumpedEventArgs`                  |
| `OnMovementStateChanged`    | `PlayerMovementStateChangedEventArgs`    |
| `OnCuffing`                 | `PlayerCuffingEventArgs`                 |
| `OnCuffed`                  | `PlayerCuffedEventArgs`                  |
| `OnUncuffing`               | `PlayerUncuffingEventArgs`               |
| `OnUncuffed`                | `PlayerUncuffedEventArgs`                |
| `OnEnteringPocketDimension` | `PlayerEnteringPocketDimensionEventArgs` |
| `OnEnteredPocketDimension`  | `PlayerEnteredPocketDimensionEventArgs`  |
| `OnLeavingPocketDimension`  | `PlayerLeavingPocketDimensionEventArgs`  |
| `OnLeftPocketDimension`     | `PlayerLeftPocketDimensionEventArgs`     |
| `OnFlippingCoin`            | `PlayerFlippingCoinEventArgs`            |
| `OnFlippedCoin`             | `PlayerFlippedCoinEventArgs`             |
| `OnRoomChanged`             | `PlayerRoomChangedEventArgs`             |
| `OnZoneChanged`             | `PlayerZoneChangedEventArgs`             |

### Environment Interaction

Events related to a player interacting with world objects like doors, generators, and hazards.

| Enum Member                 | Associated Event Arguments Class         |
| --------------------------- | ---------------------------------------- |
| `OnTriggeringTesla`         | `PlayerTriggeringTeslaEventArgs`         |
| `OnTriggeredTesla`          | `PlayerTriggeredTeslaEventArgs`          |
| `OnIdlingTesla`             | `PlayerIdlingTeslaEventArgs`             |
| `OnIdledTesla`              | `PlayerIdledTeslaEventArgs`              |
| `OnInteractingDoor`         | `PlayerInteractingDoorEventArgs`         |
| `OnInteractedDoor`          | `PlayerInteractedDoorEventArgs`          |
| `OnInteractingElevator`     | `PlayerInteractingElevatorEventArgs`     |
| `OnInteractedElevator`      | `PlayerInteractedElevatorEventArgs`      |
| `OnInteractingGenerator`    | `PlayerInteractingGeneratorEventArgs`    |
| `OnInteractedGenerator`     | `PlayerInteractedGeneratorEventArgs`     |
| `OnInteractingLocker`       | `PlayerInteractingLockerEventArgs`       |
| `OnInteractedLocker`        | `PlayerInteractedLockerEventArgs`        |
| `OnInteractingScp330`       | `PlayerInteractingScp330EventArgs`       |
| `OnInteractedScp330`        | `PlayerInteractedScp330EventArgs`        |
| `OnInteractingWarheadLever` | `PlayerInteractingWarheadLeverEventArgs` |
| `OnInteractedWarheadLever`  | `PlayerInteractedWarheadLeverEventArgs`  |
| `OnEnteringHazard`          | `PlayerEnteringHazardEventArgs`          |
| `OnEnteredHazard`           | `PlayerEnteredHazardEventArgs`           |
| `OnStayingInHazard`         | `PlayersStayingInHazardEventArgs`        |
| `OnLeavingHazard`           | `PlayerLeavingHazardEventArgs`           |
| `OnLeftHazard`              | `PlayerLeftHazardEventArgs`              |

### Miscellaneous

A collection of other specialized player events.

| Enum Member                | Associated Event Arguments Class        |
| -------------------------- | --------------------------------------- |
| `OnReceivingVoiceMessage`  | `PlayerReceivingVoiceMessageEventArgs`  |
| `OnSendingVoiceMessage`    | `PlayerSendingVoiceMessageEventArgs`    |
| `OnUsingIntercom`          | `PlayerUsingIntercomEventArgs`          |
| `OnUsedIntercom`           | `PlayerUsedIntercomEventArgs`           |
| `OnTogglingNoclip`         | `PlayerTogglingNoclipEventArgs`         |
| `OnToggledNoclip`          | `PlayerToggledNoclipEventArgs`          |
| `OnSpawningRagdoll`        | `PlayerSpawningRagdollEventArgs`        |
| `OnSpawnedRagdoll`         | `PlayerSpawnedRagdollEventArgs`         |
| `OnReceivedAchievement`    | `PlayerReceivedAchievementEventArgs`    |
| `OnRequestingRaPlayerList` | `PlayerRequestingRaPlayerListEventArgs` |
| `OnRequestedRaPlayerList`  | `PlayerRequestedRaPlayerListEventArgs`  |
