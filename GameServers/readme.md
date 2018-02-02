# Laclede's LAN Game Servers

## Related Documents

* [Using Docker for Game Servers](DockerAndGameServers.md)
* [Recommended Tools for Game Server Admins](RecommendedTools.md)
* [Working with our Game Server Repos](WorkingWithOurRepos.md)

## Dockerized Game Servers

When feasible we ["dockerize"](https://hub.docker.com/u/lacledeslan) our game servers utilizing [Docker Cloud](https://cloud.docker.com/app/lacledeslan/) for automated builds and use [Snippet-Generator](https://github.com/LacledesLAN/Snippet-Generator) to generate the launch strings. For an overview of our best-practices and experiences using Docker at Laclede's LAN events see ["Using Docker for Game Servers"](DockerAndGameServers.md).

### Image Catalog

#### Builder Image

We use [docker image "SteamCMD"](https://github.com/LacledesLAN/SteamCMD) to build most of our game servers. In addition to including [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD) this image provides common tools such as `bzip2`, `curl`, `tar`, and `wget`.

#### Game Servers

Stock images on the left with derivative "flavor" images to the right.

| Stock Image                                                                                       | Build Status                                                                                                                                                      | Description                                    |
| ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| [gamesvr-7daystodie](https://github.com/LacledesLAN/gamesvr-7daystodie)                           |                                                                                                                                                                   | 7 Days to Die Server                           |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─freeplay](https://github.com/LacledesLAN/gamesvr-7daystodie-freeplay) |                                                                                                                                                                   | LL 7 Days to Die Freeplay Server               |
| [gamesvr-blackmesa](https://github.com/LacledesLAN/gamesvr-blackmesa)                             |                                                                                                                                                                   | Black Mesa Server                              |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─freeplay](https://github.com/LacledesLAN/gamesvr-blackmesa-freeplay)  |                                                                                                                                                                   | LL Black Mesa Freeplay Server                  |
| [gamesvr-csgo](https://github.com/LacledesLAN/gamesvr-csgo)                                       |                                                                                                                                                                   | Counter-Strike GO Server                       |
| &nbsp;&nbsp;&nbsp;&nbsp;├─[─freeplay](https://github.com/LacledesLAN/gamesvr-csgo-freeplay)       |                                                                                                                                                                   | LL Counter-Strike GO Freeplay Server           |
| &nbsp;&nbsp;&nbsp;&nbsp;├─[─test](https://github.com/LacledesLAN/gamesvr-csgo-test)               |                                                                                                                                                                   | LL Counter-Strike GO Client Test Server        |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─tourney](https://github.com/LacledesLAN/gamesvr-csgo-tourney)         |                                                                                                                                                                   | LL Counter-Strike GO Tournament Server         |
| [gamesvr-cssource](https://github.com/LacledesLAN/gamesvr-cssource)                               | [![Build Status](https://travis-ci.org/LacledesLAN/gamesvr-cssource.svg?branch=master)](https://travis-ci.org/LacledesLAN/gamesvr-cssource)                       | Counter-Strike Source Server                   |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─freeplay](https://github.com/LacledesLAN/gamesvr-cssource-freeplay)   | [![Build Status](https://travis-ci.org/LacledesLAN/gamesvr-cssource-freeplay.svg?branch=master)](https://travis-ci.org/LacledesLAN/gamesvr-cssource-freeplay)     | LL Counter-Strike Source Freeplay Server       |
| [gamesvr-dods](https://github.com/LacledesLAN/gamesvr-dods)                                       | [![Build Status](https://travis-ci.org/LacledesLAN/gamesvr-dods.svg?branch=master)](https://travis-ci.org/LacledesLAN/gamesvr-dods)                               | Day of Defeat Source Server                    |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─freeplay](https://github.com/LacledesLAN/gamesvr-dods-freeplay)       | [![Build Status](https://travis-ci.org/LacledesLAN/gamesvr-dods-freeplay.svg?branch=master)](https://travis-ci.org/LacledesLAN/gamesvr-dods-freeplay)             | LL Day of Defeat Source Freeplay Server        |
| [gamesvr-garrysmod](https://github.com/LacledesLAN/gamesvr-garrysmod)                             |                                                                                                                                                                   | Garry's Mod Server                             |
| &nbsp;&nbsp;&nbsp;&nbsp;├─[─deathrun](https://github.com/LacledesLAN/gamesvr-garrysmod-deathrun)  |                                                                                                                                                                   | LL Gmod Deathrun Server                        |
| &nbsp;&nbsp;&nbsp;&nbsp;├──murder                                                                 |                                                                                                                                                                   | planned                                        |
| &nbsp;&nbsp;&nbsp;&nbsp;├──prophunt                                                               |                                                                                                                                                                   | planned                                        |
| &nbsp;&nbsp;&nbsp;&nbsp;├──sandbox                                                                |                                                                                                                                                                   | planned                                        |
| &nbsp;&nbsp;&nbsp;&nbsp;├──ttt                                                                    |                                                                                                                                                                   | planned                                        |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─zombie](https://github.com/LacledesLAN/gamesvr-garrysmod-zombie)      |                                                                                                                                                                   | LL Gmod Zombies Server                         |
| [gamesvr-gesource](https://github.com/LacledesLAN/gamesvr-gesource)                               |                                                                                                                                                                   | GoldenEye: Source Server                       |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─freeplay](https://github.com/LacledesLAN/gamesvr-gesource-freeplay)   |                                                                                                                                                                   | LL GoldenEye: Source Freeplay Server           |
| [gamesvr-goldsource](https://github.com/LacledesLAN/gamesvr-goldsource)                           |                                                                                                                                                                   | GoldSource Server                              |
| &nbsp;&nbsp;&nbsp;&nbsp;├─[─cstrike](https://github.com/LacledesLAN/gamesvr-goldsource-cstrike)   |                                                                                                                                                                   | LL Counter-Strike 1.6 Freeplay Server          |
| &nbsp;&nbsp;&nbsp;&nbsp;├─[─dmc](https://github.com/LacledesLAN/gamesvr-goldsource-dmc)           |                                                                                                                                                                   | LL Deatmatch Classic Freeplay Server           |
| &nbsp;&nbsp;&nbsp;&nbsp;├─[─hldm](https://github.com/LacledesLAN/gamesvr-goldsource-hldm)         |                                                                                                                                                                   | LL Half-Life Deathmatch Freeplay Server        |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─tfc](https://github.com/LacledesLAN/gamesvr-goldsource-tfc)           |                                                                                                                                                                   | LL Team Fortress Classic Freeplay Server       |
| [gamesvr-hl2dm](https://github.com/LacledesLAN/gamesvr-hl2dm)                                     |                                                                                                                                                                   | Half-Life 2: Deathmatch Server                 |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─freeplay](https://github.com/LacledesLAN/gamesvr-hl2dm-freeplay)      |                                                                                                                                                                   | LL Half-Life 2: Deathmatch Freeplay Server     |
| [gamesvr-hldms](https://github.com/LacledesLAN/gamesvr-hldms)                                     |                                                                                                                                                                   | Half-Life Deathmatch: Source                   |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─freeplay](https://github.com/LacledesLAN/gamesvr-hldms-freeplay)      |                                                                                                                                                                   | LL Half-Life Deathmatch Source Freeplay Server |
| [gamesvr-minecraft](https://github.com/LacledesLAN/gamesvr-minecraft)                             |                                                                                                                                                                   | Minecraft Server                               |
| [gamesvr-svencoop](https://github.com/LacledesLAN/gamesvr-svencoop)                               |                                                                                                                                                                   | Sven Co-op Server                              |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─freeplay](https://github.com/LacledesLAN/gamesvr-svencoop-freeplay)   |                                                                                                                                                                   | LL Sven Co-Op Freeplay Server                  |
| [gamesvr-tf2](https://github.com/LacledesLAN/gamesvr-tf2)                                         |                                                                                                                                                                   | Team Fortress 2 Server                         |
| &nbsp;&nbsp;&nbsp;&nbsp;├─[─blindfrag](https://github.com/LacledesLAN/gamesvr-tf2-blindfrag)      |                                                                                                                                                                   | LL Team Fortress 2 Blind-Frag Server           |
| &nbsp;&nbsp;&nbsp;&nbsp;├─[─freeplay](https://github.com/LacledesLAN/gamesvr-tf2-freeplay)        |                                                                                                                                                                   | LL Team Fortress 2 Freeplay Server             |
| &nbsp;&nbsp;&nbsp;&nbsp;└─[─ware](https://github.com/LacledesLAN/gamesvr-tf2-ware)                |                                                                                                                                                                   | LL Team Fortress 2 "TF2-Ware" Server           |
| [gamesvr-ut2004](https://github.com/LacledesLAN/gamesvr-ut2004)                                   |                                                                                                                                                                   | Unreal Tournament 2004 Server                  |
|                                                                                                   |                                                                                                                                                                   |                                                |

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
