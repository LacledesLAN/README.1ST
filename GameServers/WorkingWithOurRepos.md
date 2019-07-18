# Working with LL Game Server Repos

## About Git Submodules

While building our game servers we found ourselves frequently including the same files in multiple builds. Fortunately git has built-in support for linking and adding content from foreign repositories called [submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

Submodules on github are identifiable via the format `<folder-name> @ <commit-hash>` where the commit-hash shows which commit of the foreign git repo has been included.

![submodules on github](https://raw.githubusercontent.com/LacledesLAN/README.1ST/master/.images/github_submodule.png)



When you first clone a repo that includes submodules you'll find those folders empty. To fetch their contents use the command `git submodule update --recursive;`.

To update submodules to their latest commits use `git submodule foreach git pull origin master;`.

> Further reading: [github.com - Working with Submodules](https://github.com/blog/2104-working-with-submodules.png)

## Get Docker

Our game servers are built as Docker Images - you'll need Docker to build them as well. The free community edition on desktop will suffice. [Download Docker](https://www.docker.com/community-edition)

> Further reading:  [Using Docker for Game Servers](DockerAndGameServers.md)

## Using Visual Studio Code

Our game-server repositories are optimized for editing with [Visual Studio Code](https://code.visualstudio.com/), a cross-platform, open-source code editor. When working with these repos we *highly* recommend using it.

### Recommended Plugins

We *highly* recommend these plugins while working with our repositories in Visual Studio Code.

* [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker) - for syntax highlighting, hover tips, IntelliSense completion, and linting.
* [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) - Used to maintain consistent coding style and encoding.

### Helpful Plugins

You might find these plugins helpful as well.

* [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) - highlight syntax errors in markdown files
* [Spell Right](https://marketplace.visualstudio.com/items?itemName=ban.spellright) - lightweight spell checker
* [VSCode Great Icons](https://marketplace.visualstudio.com/items?itemName=emmanuelbeziat.vscode-great-icons) -

### Tasks

Common build/test operations are defined using [VSCode tasks](https://code.visualstudio.com/docs/editor/tasks) and can be executed via the Tasks.

![submodules on github](https://raw.githubusercontent.com/LacledesLAN/README.1ST/master/.images/vscode-tasks.gif)
