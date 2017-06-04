## Laclede's LAN Game Servers
Wherever feasible we build/deploy our game servers as [Docker](https://www.docker.com/) containers and use [Snippet-Generator](https://github.com/LacledesLAN/Snippet-Generator) to generate the launch strings.

### Image Catalogue
Base images on the left with derivative images to the right.

| 0 ►                                               | 1 ►                                                           | 2 ►                                                                        | 3                                                                             |
|---------------------------------------------------|---------------------------------------------------------------|----------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| [ubuntu:latest](https://hub.docker.com/_/ubuntu/) | [gamesvr-srcds](https://github.com/LacledesLAN/gamesvr-srcds) | [-7daystodie](https://github.com/LacledesLAN/gamesvr-srcds-7daystodie)     | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-7daystodie-freeplay) |
|                                                   |                                                               | [-blackmesa](https://github.com/LacledesLAN/gamesvr-srcds-blackmesa)       | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-blackmesa-freeplay)  |
|                                                   |                                                               | [-csgo](https://github.com/LacledesLAN/gamesvr-srcds-csgo)                 | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-csgo-freeplay)       |
|                                                   |                                                               |                                                                            | [-test](https://github.com/LacledesLAN/gamesvr-srcds-csgo-test)               |
|                                                   |                                                               |                                                                            | [-tourney](https://github.com/LacledesLAN/gamesvr-srcds-csgo-tourney)         |
|                                                   |                                                               | [-cssource](https://github.com/LacledesLAN/gamesvr-srcds-cssource)         |                                                                               |
|                                                   |                                                               | [-dods](https://github.com/LacledesLAN/gamesvr-srcds-dods)                 | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-dods-freeplay)       |
|                                                   |                                                               | [-hl2dm](https://github.com/LacledesLAN/gamesvr-srcds-hl2dm)               | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-hl2dm-freeplay)      |
|                                                   |                                                               | [-garrysmod](https://github.com/LacledesLAN/gamesvr-srcds-garrysmod)       | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-garrysmod-freeplay)  |
|                                                   |                                                               | [-gesource](https://github.com/LacledesLAN/gamesvr-srcds-gesource)         |                                                                               |
|                                                   |                                                               | [-goldsource](https://github.com/LacledesLAN/gamesvr-srcds-goldsource)     |                                                                               |
|                                                   |                                                               | [-killingfloor](https://github.com/LacledesLAN/gamesvr-srcds-killingfloor) |                                                                               |
|                                                   |                                                               | [-svencoop](https://github.com/LacledesLAN/gamesvr-srcds-svencoop)         | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-svencoop-freeplay)   |
|                                                   |                                                               | [-tf2](https://github.com/LacledesLAN/gamesvr-srcds-tf2)                   | [-blindfrag](https://github.com/LacledesLAN/gamesvr-srcds-tf2-blindfrag)      |
|                                                   |                                                               |                                                                            | [-freeplay](https://github.com/LacledesLAN/gamesvr-srcds-tf2-freeplay)        |
|                                                   |                                                               |                                                                            | [-ware](https://github.com/LacledesLAN/gamesvr-srcds-tf2-ware)                |

### Standards we Follow
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
