# Laclede's LAN Game Servers

> Related resource: * [Recommended Tools for Game Server Admins](RecommendedTools.md)

## Dockerized Game Servers
When feasible we ["dockerize"](https://hub.docker.com/u/lacledeslan) our game servers utilizing [Docker Cloud](https://cloud.docker.com/app/lacledeslan/) for automated builds and use [Snippet-Generator](https://github.com/LacledesLAN/Snippet-Generator) to generate the launch strings. For an overview of our best-practices and experiences using Docker at Laclede's LAN events see ["Using Docker for Game Servers"](DockerAndGameServers.md).

### Image Catalog

#### Builder Image
We use [docker image "SteamCMD"](https://github.com/LacledesLAN/SteamCMD) to build most of our game servers. In addition to including [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD) this image provides common tools such as `bzip2`, `curl`, `tar`, and `wget`.

#### Game Servers
Stock images on the left with derivative "flavor" images to the right.

| Stock Image                                                                 | Derived "flavor" Image                                                  | Description                                                   |
| --------------------------------------------------------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------- |
| [gamesvr-7daystodie](https://github.com/LacledesLAN/gamesvr-7daystodie)     |                                                                         | 7 Days to Die Server                                          |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-7daystodie-freeplay) | &nbsp;&nbsp;└─ LL 7 Days to Die Freeplay Server               |
| [gamesvr-blackmesa](https://github.com/LacledesLAN/gamesvr-blackmesa)       |                                                                         | Black Mesa Server                                             |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-blackmesa-freeplay)  | &nbsp;&nbsp;└─ LL Black Mesa Freeplay Server                  |
| [gamesvr-csgo](https://github.com/LacledesLAN/gamesvr-csgo)                 |                                                                         | Counter-Strike GO Server                                      |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-csgo-freeplay)       | &nbsp;&nbsp;├─ LL Counter-Strike GO Freeplay Server           |
|                                                                             | [-test](https://github.com/LacledesLAN/gamesvr-csgo-test)               | &nbsp;&nbsp;├─ LL Counter-Strike GO Client Test Server        |
|                                                                             | [-tourney](https://github.com/LacledesLAN/gamesvr-csgo-tourney)         | &nbsp;&nbsp;└─ LL Counter-Strike GO Tournament Server         |
| [gamesvr-cssource](https://github.com/LacledesLAN/gamesvr-cssource)         |                                                                         | Counter-Strike Source Server                                  |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-cssource-freeplay)   | &nbsp;&nbsp;└─ LL Counter-Strike Source Freeplay Server       |
| [gamesvr-dods](https://github.com/LacledesLAN/gamesvr-dods)                 |                                                                         | Day of Defeat Source Server                                   |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-dods-freeplay)       | &nbsp;&nbsp;└─ LL Day of Defat Source Server                  |
| [gamesvr-factorio](https://github.com/LacledesLAN/gamesvr-factorio)         |                                                                         | Factorio Server                                               |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-factorio-freeplay)   | &nbsp;&nbsp;└─ LL Factorio Freeplay Server                    |
| [gamesvr-garrysmod](https://github.com/LacledesLAN/gamesvr-garrysmod)       |                                                                         | Garry's Mod Server                                            |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-garrysmod-freeplay)  | &nbsp;&nbsp;└─ LL Garry's Mod Freeplay Server                 |
| [gamesvr-gesource](https://github.com/LacledesLAN/gamesvr-gesource)         |                                                                         | GoldenEye: Source Server                                      |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-gesource-freeplay)   | &nbsp;&nbsp;└─ LL GoldenEye: Source Freeplay Server           |
| [gamesvr-goldsource](https://github.com/LacledesLAN/gamesvr-goldsource)     |                                                                         | GoldSource Server                                             |
|                                                                             | [-cstrike](https://github.com/LacledesLAN/gamesvr-goldsource-cstrike)   | &nbsp;&nbsp;├─ LL Counter-Strike 1.6 Freeplay Server          |
|                                                                             | [-dmc](https://github.com/LacledesLAN/gamesvr-goldsource-dmc)           | &nbsp;&nbsp;├─ LL Deatmatch Classic Freeplay Server           |
|                                                                             | [-hldm](https://github.com/LacledesLAN/gamesvr-goldsource-hldm)         | &nbsp;&nbsp;├─ LL Half-Life Deathmatch Freeplay Server        |
|                                                                             | [-tfc](https://github.com/LacledesLAN/gamesvr-goldsource-tfc)           | &nbsp;&nbsp;└─ LL Team Fortress Classic Freeplay Server       |
| [gamesvr-hl2dm](https://github.com/LacledesLAN/gamesvr-hl2dm)               |                                                                         | Half-Life 2: Deathmatch Server                                |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-hl2dm-freeplay)      | &nbsp;&nbsp;└─ LL Half-Life 2: Deathmatch Freeplay Server     |
| [gamesvr-hldms](https://github.com/LacledesLAN/gamesvr-hldms)               |                                                                         | Half-Life Deathmatch: Source                                  |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-hldms-freeplay)      | &nbsp;&nbsp;└─ LL Half-Life Deathmatch Source Freeplay Server |
| [gamesvr-killingfloor](https://github.com/LacledesLAN/gamesvr-killingfloor) |                                                                         | Killing Floor Server                                          |
| [gamesvr-minecraft](https://github.com/LacledesLAN/gamesvr-minecraft)       |                                                                         | Minecraft Server                                              |
| [gamesvr-svencoop](https://github.com/LacledesLAN/gamesvr-svencoop)         |                                                                         | Sven Co-op Server                                             |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-svencoop-freeplay)   | &nbsp;&nbsp;└─ LL Sven Co-Op Freeplay Server                  |
| [gamesvr-tf2](https://github.com/LacledesLAN/gamesvr-tf2)                   |                                                                         | Team Fortress 2 Server                                        |
|                                                                             | [-blindfrag](https://github.com/LacledesLAN/gamesvr-tf2-blindfrag)      | &nbsp;&nbsp;├─ LL Team Fortress 2 Blind-Frag Server           |
|                                                                             | [-freeplay](https://github.com/LacledesLAN/gamesvr-tf2-freeplay)        | &nbsp;&nbsp;├─ LL Team Fortress 2 Freeplay Server             |
|                                                                             | [-ware](https://github.com/LacledesLAN/gamesvr-tf2-ware)                | &nbsp;&nbsp;└─ LL Team Fortress 2 "TF2-Ware" Server           |
| [gamesvr-ut2k4](https://github.com/LacledesLAN/gamesvr-ut2k4)               |                                                                         | Unreal Tournament 2004 Server                                 |
|                                                                             |                                                                         |                                                               |

### Our Standards

#### Docker Images
* Image names for game servers start with `gamesvr`.
* Derived images names are appended with `-description` where "description" describes function.
* All binaries and content are nested in `/app/`.
* Images are given their own USER to indicate what the application of the image is.
  * This prevents running image contents under `root`.
  * Derived images change the username to reflect the current image (e.g. user `CSGO` becomes `CSGOTourney`).

#### Source Repos
* Content meant for `/app/` (inside the image) are stored in `/dist/`.
  * Any Linux specific content is stored in `/dist.linux/`.
  * Any Windows specific content is stored in `/dist.windows/`.

### Build Triggers
We use a running instance of [API Reactor](https://github.com/dudleycodes/APIReactor) to monitor steam games for updates; when an update is detected (or 21 days w/o an update pass) it triggers build of ['watchers' on Docker Hub](https://hub.docker.com/u/llgameserverbot/). Corresponding [automated builds](https://hub.docker.com/u/lacledeslan/) have repository links connected which triggers builds.

### Notes on Source Dedicated Servers (SRCDS)

* The Linux version of `SRCDS` prints directly to /dev/ttyN instead of stdout. This careless decision by Valve breaks piping and redirection. As such many of our SRCDS based docker images include the [`screen`](https://www.gnu.org/software/screen/manual/screen.html) utility for included automated tests.
* We heavily rely on [Meta Mod](http://metamodsource.net/) and [Source Mod](http://www.sourcemod.net/) in all of our source servers to extend functionality. In addition to being familiar with the [SRCDS wiki](https://developer.valvesoftware.com/wiki/Source_Dedicated_Server) read over [Meta Mod / Source Mod Wiki](https://wiki.alliedmods.net/Main_Page) and the corresponding [community forums](https://forums.alliedmods.net/index.php).
