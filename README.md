# cmangos-deploy-patches

This repository contains patches for [CMaNGOS][cmangos] that are applied when
building the Docker images for [cmangos-deploy][cmangos-deploy].

The patches are strictly for:

+ Correcting problems that would cause build failures, runtime crashes, or
  database corruption
+ Making Docker-specific adjustments that would not be appropriate to include
  upstream

At no point will a patch be added that changes the behavior of the server or
otherwise alters its functionality.

Once a patch is no longer needed, it will be removed from this repository.
Therefore, there may be times when this repository contains no patches at all.

## Layout

CMaNGOS ships separate repositories per expansion. Patches are organized so
that the same source can be shared across all of them while still allowing
expansion-specific adjustments:

- `all/*.patch` is applied to every expansion's build
- `classic/*.patch` is applied only to the Classic build
- `tbc/*.patch` is applied only to the TBC build
- `wotlk/*.patch` is applied only to the WotLK build

The expansion-specific directories are optional; create them only when an
actual expansion-specific patch needs a home.

[cmangos]: https://github.com/cmangos
[cmangos-deploy]: https://github.com/mserajnik/cmangos-deploy
