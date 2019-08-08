# Members

## ResetPlayerGuiOnSpawn
Globally controls the resetting behavior of
[LayerCollectors](class:LayerCollector) under the [PlayerGui](class:PlayerGui).

When ResetPlayerGuiOnSpawn is true (the default), a LayerCollector under the
PlayerGui will reset if its [ResetOnSpawn](class:LayerCollector/ResetOnSpawn)
property is also true. When ResetPlayerGuiOnSpawn is false, LayerCollectors will
never reset, regardless of their ResetOnSpawn property.

ResetPlayerGuiOnSpawn is deprecated. To suppress the resetting behavior of a
LayerCollector, its ResetOnSpawn property should explicitly be set to false.
