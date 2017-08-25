# Laclede's LAN Game Servers

## Dockerized Game Servers
When feasible we ["dockerize"](https://hub.docker.com/u/lacledeslan) our game servers utilizing [Docker Cloud](https://cloud.docker.com/app/lacledeslan/) for automated builds and use [Snippet-Generator](https://github.com/LacledesLAN/Snippet-Generator) to generate the launch strings.

### Image Catalog

#### Builder Image
We use [docker image "SteamCMD"](https://github.com/LacledesLAN/SteamCMD) to build most of our game servers. In addition to including [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD) this image provides common tools such as `bzip2`, `curl`, `git`, `tar`, and `wget`. This lets us use these tools without including them in final images or needing to use a common base image in all of our game servers (thanks to [Docker multi-stage builds](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)).

#### Game Servers
Base images on the left with derivative images to the right.

| 1 ►                                                                         | 2         |
| --------------------------------------------------------------------------- | ------------- |
| [gamesvr-7daystodie](https://github.com/LacledesLAN/gamesvr-7daystodie)     | [gamesvr-7daystodie-freeplay](https://github.com/LacledesLAN/gamesvr-7daystodie-freeplay) |
| [gamesvr-blackmesa](https://github.com/LacledesLAN/gamesvr-blackmesa)       | [gamesvr-blackmesa-freeplay](https://github.com/LacledesLAN/gamesvr-blackmesa-freeplay)   |
| [gamesvr-csgo](https://github.com/LacledesLAN/gamesvr-csgo)                 | [gamesvr-csgo-freeplay](https://github.com/LacledesLAN/gamesvr-csgo-freeplay)             |
|                                                                             | [gamesvr-csgo-test](https://github.com/LacledesLAN/gamesvr-csgo-test)                     |
|                                                                             | [gamesvr-csgo-tourney](https://github.com/LacledesLAN/gamesvr-csgo-tourney)               |
| [gamesvr-cssource](https://github.com/LacledesLAN/gamesvr-cssource)         | [gamesvr-cssource-freeplay]()                                                             |
| [gamesvr-dods](https://github.com/LacledesLAN/gamesvr-dods)                 | [gamesvr-dods-freeplay](https://github.com/LacledesLAN/gamesvr-dods-freeplay)             |
| [gamesvr-factorio]()                                                        | [gamesvr-factorio-freeplay]()                                                             |
| [gamesvr-garrysmod](https://github.com/LacledesLAN/gamesvr-garrysmod)       | [gamesvr-garrysmod-freeplay](https://github.com/LacledesLAN/gamesvr-garrysmod-freeplay)   |
| [gamesvr-gesource](https://github.com/LacledesLAN/gamesvr-gesource)         | [gamesvr-gesource-freeplay](https://github.com/LacledesLAN/gamesvr-gesource-freeplay)     |
| [gamesvr-goldsource](https://github.com/LacledesLAN/gamesvr-goldsource)     | [gamesvr-goldsource-cstrike](https://github.com/LacledesLAN/gamesvr-goldsource-cstrike)   |
|                                                                             | [gamesvr-goldsource-dmc](https://github.com/LacledesLAN/gamesvr-goldsource-dmc)           |
|                                                                             | [gamesvr-goldsource-hldm](https://github.com/LacledesLAN/gamesvr-goldsource-hldm)         |
|                                                                             | [gamesvr-goldsource-tfc](https://github.com/LacledesLAN/gamesvr-goldsource-tfc)           |
| [gamesvr-hl2dm](https://github.com/LacledesLAN/gamesvr-hl2dm)               | [gamesvr-hl2dm-freeplay]()                                                                |
| [gamesvr-hldms]()                                                           | [gamesvr-hldms-freeplay](https://github.com/LacledesLAN/gamesvr-hl2dm-freeplay)           |
| [gamesvr-killingfloor](https://github.com/LacledesLAN/gamesvr-killingfloor) |                                                                                           |
| [gamesvr-minecraft](https://github.com/LacledesLAN/gamesvr-minecraft)       |                                                                                           |
| [gamesvr-svencoop](https://github.com/LacledesLAN/gamesvr-svencoop)         | [gamesvr-svencoop-freeplay](https://github.com/LacledesLAN/gamesvr-svencoop-freeplay)     |
| [gamesvr-tf2](https://github.com/LacledesLAN/gamesvr-tf2)                   | [gamesvr-tf2-blindfrag](https://github.com/LacledesLAN/gamesvr-tf2-blindfrag)             |
|                                                                             | [gamesvr-tf2-freeplay](https://github.com/LacledesLAN/gamesvr-tf2-freeplay)               |
|                                                                             | [gamesvr-tf2-ware](https://github.com/LacledesLAN/gamesvr-tf2-ware)                       |
| [gamesvr-ut2k4]()                                                           | []()                                                                                      |


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
