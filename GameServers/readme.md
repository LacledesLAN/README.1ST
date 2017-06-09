# Laclede's LAN Game Servers

## Dockerized Game Servers
When feasible we ["dockerize"](https://hub.docker.com/u/lacledeslan) our game servers and use [Snippet-Generator](https://github.com/LacledesLAN/Snippet-Generator) to generate the launch strings.

### Image Catalog
Base images on the left with derivative images to the right.

| 1 ►                                                                   | 2 ►                                                                        | 3                                                                             |
|-----------------------------------------------------------------------|----------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| [gamesvr-minecraft](https://github.com/LacledesLAN/gamesvr-minecraft) |                                                                            |                                                                               |
| [gamesvr-srcds](https://github.com/LacledesLAN/gamesvr-srcds)         | [-7daystodie](https://github.com/LacledesLAN/gamesvr-srcds-7daystodie)     | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-7daystodie-freeplay) |
|                                                                       | [-blackmesa](https://github.com/LacledesLAN/gamesvr-srcds-blackmesa)       | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-blackmesa-freeplay)  |
|                                                                       | [-csgo](https://github.com/LacledesLAN/gamesvr-srcds-csgo)                 | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-csgo-freeplay)       |
|                                                                       |                                                                            | [-test](https://github.com/LacledesLAN/gamesvr-srcds-csgo-test)               |
|                                                                       |                                                                            | [-tourney](https://github.com/LacledesLAN/gamesvr-srcds-csgo-tourney)         |
|                                                                       | [-cssource](https://github.com/LacledesLAN/gamesvr-srcds-cssource)         |                                                                               |
|                                                                       | [-dods](https://github.com/LacledesLAN/gamesvr-srcds-dods)                 | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-dods-freeplay)       |
|                                                                       | [-hl2dm](https://github.com/LacledesLAN/gamesvr-srcds-hl2dm)               | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-hl2dm-freeplay)      |
|                                                                       | [-garrysmod](https://github.com/LacledesLAN/gamesvr-srcds-garrysmod)       | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-garrysmod-freeplay)  |
|                                                                       | [-gesource](https://github.com/LacledesLAN/gamesvr-srcds-gesource)         |                                                                               |
|                                                                       | [-goldsource](https://github.com/LacledesLAN/gamesvr-srcds-goldsource)     | [-cstrike](https://github.com/LacledesLAN/gamesvr-srcds-goldsource-cstrike)   |
|                                                                       |                                                                            | [-dmc](https://github.com/LacledesLAN/gamesvr-srcds-goldsource-dmc)           |
|                                                                       |                                                                            | [-hldm](https://github.com/LacledesLAN/gamesvr-srcds-goldsource-hldm)         |
|                                                                       |                                                                            | [-tfc](https://github.com/LacledesLAN/gamesvr-srcds-goldsource-tfc)           |
|                                                                       | [-killingfloor](https://github.com/LacledesLAN/gamesvr-srcds-killingfloor) |                                                                               |
|                                                                       | [-svencoop](https://github.com/LacledesLAN/gamesvr-srcds-svencoop)         | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-svencoop-freeplay)   |
|                                                                       | [-tf2](https://github.com/LacledesLAN/gamesvr-srcds-tf2)                   | [-blindfrag](https://github.com/LacledesLAN/gamesvr-srcds-tf2-blindfrag)      |
|                                                                       |                                                                            | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-tf2-freeplay)        |
|                                                                       |                                                                            | [-ware](https://github.com/LacledesLAN/gamesvr-srcds-tf2-ware)                |
| [gamesvr-ut2004](https://github.com/LacledesLAN/gamesvr-ut2004)       |                                                                            |                                                                               |
| [gamesvr-ut4](https://github.com/LacledesLAN/gamesvr-ut4)             |                                                                            |                                                                               |

### Standards we Follow
#### Naming
* Game-servers start with `gamesvr`.
* Derived images names are appended with `-description` where "description" describes that the layer adds.
* The `latest` tag is only used for local test builds. The `linux` and `windows` tags are used for production.
#### Images
* Apps are placed in `/app/bin/`.
* Apps are placed in to their own image, without configuration changes, to allow for easy testing.
* Images (at the app level or lower) are given their own USER to indicate what the application of the image is. This prevents running image contents as `root` as well as giving an indication of the image being used when shelled in.
  * Child images change the USER name to reflect the current image (e.g. user `CSGO` becomes `CSGOTourney`).
* Support tools are installed to `/app/` and never nested inside of `/app/bin`.
#### Repos
* Content meant for `/app/bin/` (inside the image) are stored in `/dist/`.
  * Any Linux specific content is stored in `/dist.linux/`.
  * Any Windows specific content is stored in `/dist.windows/`.

### Build Triggers
We use a running instance of [API Reactor](https://github.com/dudleycodes/APIReactor) to monitor steam games for updates; when an update is detected (or 21 days w/o an update pass) it triggers build of ['watchers' on Docker Hub](https://hub.docker.com/u/llgameserverbot/). Corresponding [automated builds](https://hub.docker.com/u/lacledeslan/) have repository links connected which triggers builds.

Anyone is welcome to link their builds to these watchers.