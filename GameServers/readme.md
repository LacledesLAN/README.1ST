# Laclede's LAN Game Servers

Be sure to check out our list of [recommended tools](RecommendedTools.md)! If you're new to LL or Docker see ["Docker at Laclede's LAN"](AboutDocker.md).

## Dockerized Game Servers
When feasible we ["dockerize"](https://hub.docker.com/u/lacledeslan) our game servers utilizing [Docker Cloud](https://cloud.docker.com/app/lacledeslan/) for automated builds and use [Snippet-Generator](https://github.com/LacledesLAN/Snippet-Generator) to generate the launch strings.

### Image Catalog

#### Builder Image
We use [docker image "SteamCMD"](https://github.com/LacledesLAN/SteamCMD) to build most of our game servers. In addition to including [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD) this image provides common tools such as `bzip2`, `curl`, `git`, `tar`, and `wget`. This lets us use these tools without including them in final images or needing to use a common base image in all of our game servers (thanks to [Docker multi-stage builds](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)).

#### Game Servers
Base images on the left with derivative images to the right.

| 1 ►                                                                         | 2                                                                       | Description                                   |
| --------------------------------------------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------- |
| [gamesvr-7daystodie](https://github.com/LacledesLAN/gamesvr-7daystodie)     |                                                                         | 7 Days to Die Server                          |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-7daystodie-freeplay) | └─ LL 7 Days to Die Freeplay Server           |
| [gamesvr-blackmesa](https://github.com/LacledesLAN/gamesvr-blackmesa)       |                                                                         | Black Mesa Server                             |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-blackmesa-freeplay)  | └─ LL Black Mesa Freeplay Server              |
| [gamesvr-csgo](https://github.com/LacledesLAN/gamesvr-csgo)                 |                                                                         | Counter-Strike GO Server                      |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-csgo-freeplay)       | ├─ LL Counter-Strike GO Freeplay Server       |
|                                                                             | [-test](https://github.com/LacledesLAN/gamesvr-csgo-test)               | ├─ LL Counter-Strike GO Client Test Server    |
|                                                                             | [-tourney](https://github.com/LacledesLAN/gamesvr-csgo-tourney)         | └─ LL Counter-Strike GO Tournament Server     |
| [gamesvr-cssource](https://github.com/LacledesLAN/gamesvr-cssource)         |                                                                         | Counter-Strike Source Server                  |
|                                                                             | [-freeplay]()                                                           |                                               |
| [gamesvr-dods](https://github.com/LacledesLAN/gamesvr-dods)                 |                                                                         | Day of Defeat Source Server                   |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-dods-freeplay)       | └─ LL Day of Defat Source Server              |
| [gamesvr-factorio]()                                                        |                                                                         | Factorio Server                               |
|                                                                             | [-freeplay]()                                                           | └─ LL Factorio Freeplay Server                |
| [gamesvr-garrysmod](https://github.com/LacledesLAN/gamesvr-garrysmod)       |                                                                         | Garry's Mod Server                            |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-garrysmod-freeplay)  | └─ LL Garry's Mod Freeplay Server             |
| [gamesvr-gesource](https://github.com/LacledesLAN/gamesvr-gesource)         |                                                                         |                                               |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-gesource-freeplay)   |                                               |
| [gamesvr-goldsource](https://github.com/LacledesLAN/gamesvr-goldsource)     |                                                                         |                                               |
|                                                                             | [-cstrike](https://github.com/LacledesLAN/gamesvr-goldsource-cstrike)   |                                               |
|                                                                             | [-dmc](https://github.com/LacledesLAN/gamesvr-goldsource-dmc)           |                                               |
|                                                                             | [-hldm](https://github.com/LacledesLAN/gamesvr-goldsource-hldm)         |                                               |
|                                                                             | [-tfc](https://github.com/LacledesLAN/gamesvr-goldsource-tfc)           |                                               |
| [gamesvr-hl2dm](https://github.com/LacledesLAN/gamesvr-hl2dm)               |                                                                         | Half-Life 2: Deathmatch Server                |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-hl2dm-freeplay)      | └─ LL Half-Life 2: Deathmatch Freeplay Server |
| [gamesvr-hldms]()                                                           |                                                                         |                                               |
|                                                                             |                                                                         |                                               |
| [gamesvr-killingfloor](https://github.com/LacledesLAN/gamesvr-killingfloor) |                                                                         |                                               |
|                                                                             |                                                                         |                                               |
| [gamesvr-minecraft](https://github.com/LacledesLAN/gamesvr-minecraft)       |                                                                         |                                               |
|                                                                             |                                                                         |                                               |
| [gamesvr-svencoop](https://github.com/LacledesLAN/gamesvr-svencoop)         | [-freeplay](https://github.com/LacledesLAN/gamesvr-svencoop-freeplay)   |                                               |
|                                                                             |                                                                         |                                               |
| [gamesvr-tf2](https://github.com/LacledesLAN/gamesvr-tf2)                   |                                                                         | Team Fortress 2 Server                        |
|                                                                             | [-blindfrag](https://github.com/LacledesLAN/gamesvr-tf2-blindfrag)      | ├─ LL Team Fortress 2 Blind-Frag Server       |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-tf2-freeplay)        | ├─ LL Team Fortress 2 Freeplay Server         |
|                                                                             | [-ware](https://github.com/LacledesLAN/gamesvr-tf2-ware)                | └─ LL Team Fortress 2 "TF2-Ware" Server       |
| [gamesvr-ut2k4]()                                                           | []()                                                                    |                                               |
|                                                                             |                                                                         |                                               |


### Standards we Follow
#### Naming
* Game-servers start with `gamesvr`.
* Derived images names are appended with `-description` where "description" describes that the layer adds.
#### Images
* Apps are placed in `/app/`.
* Apps are placed in to their own image, without configuration changes, to allow for easy testing (column 1).
* Images are given their own USER to indicate what the application of the image is. This prevents running image contents as `root` as well as giving an indication of the image being used when shelled in.
  * Child images change the USER name to reflect the current image (e.g. user `CSGO` becomes `CSGOTourney`).

#### Repos
* Content meant for `/app/` (inside the image) are stored in `/dist/`.
  * Any Linux specific content is stored in `/dist.linux/`.
  * Any Windows specific content is stored in `/dist.windows/`.

### Build Triggers
We use a running instance of [API Reactor](https://github.com/dudleycodes/APIReactor) to monitor steam games for updates; when an update is detected (or 21 days w/o an update pass) it triggers build of ['watchers' on Docker Hub](https://hub.docker.com/u/llgameserverbot/). Corresponding [automated builds](https://hub.docker.com/u/lacledeslan/) have repository links connected which triggers builds.

Anyone is welcome to link their builds to these watchers.

### Notes on Source Dedicated Servers (SRCDS)
We heavily rely on [Meta Mod](http://metamodsource.net/) and [Source Mod](http://www.sourcemod.net/) in all of our source servers to extend functionality. In addition to being familiar with the [SRCDS wiki](https://developer.valvesoftware.com/wiki/Source_Dedicated_Server) read over [Meta Mod / Source Mod Wiki](https://wiki.alliedmods.net/Main_Page) and the corresponding [community forums](https://forums.alliedmods.net/index.php).
