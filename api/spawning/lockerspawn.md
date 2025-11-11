# LockerSpawn

**Description**\
Controls behavior for placing a custom item inside a map locker (e.g., rifle rack). When enabled, the spawn system will target a locker of the configured type/room/zone or offset relative to a locker.

**Parameters**

* `enable` — `bool` — Whether to attempt locker-based spawning.
* `locker_type` — [`LockerType`](../enums/internal/lockertype.md) — Which locker/rack type to use (e.g., `RifleRack`).
* `room` — `string` — Preferred room name where the locker is located. Default: `"HczWarhead"`.
* `zone` — [`FacilityZone`](../enums/external/facilityzone.md) (enum) — Preferred zone where the locker exists. Default: `HeavyContainment`.
* `chamber` — `int` — Chamber/index within the locker (if applicable).
* `offset` — `Vector3` — An extra offset applied to the chosen locker position.

**Example Yaml context**

```yaml
spawn:
  spawn_settings:
  - chance: 20
    locker_settings:
      enable: true
      locker_type: RifleRack
      room: HczWarhead
      zone: HeavyContainment
      chamber: 0
      offset:
        x: 0
        y: 0
        z: 0
```
