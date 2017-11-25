# Recommended Tools for Game Server Ops

## Working with Repositories

### Git Client

The majority of our configs and custom tools are stored in Git repositories hosted on [GitHub](https://github.com/LacledesLAN).

You'll need a git client to obtain ("clone") and update ("fetch") local copies of these repos. If you're new to git **we recommend using the [GitHub Desktop Client](https://desktop.github.com/)**. If you're experienced you may prefer the [git command line tools](https://git-scm.com/) or more advanced clients like [GitKraken](https://www.gitkraken.com/).

To learn Git/GitHub check out [Crash Course For Beginners (video)](https://www.youtube.com/watch?v=SWYqp7iY_Tc), [Learn Git Branching](https://learngitbranching.js.org/), [Official Git Docs](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control).

To contribute to our repos you should be familiar with the ["GitHub Flow"](https://guides.github.com/introduction/flow/).

## Text Editor

We recommend [Visual Studio Code](https://code.visualstudio.com/); many of our repos use its features such as "tasks". We recommend installing the plugins [Docker Support for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker), [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig), and [VSCode Great Icons](https://marketplace.visualstudio.com/items?itemName=emmanuelbeziat.vscode-great-icons).

Alternatives:
* [Atom Editor](https://atom.io/)
* [Notepad++](https://notepad-plus-plus.org/) (Windows only)

## Working with Linux

### SSH
A SSH client is needed to remotely connect to our Linux servers. The choice of client can be a contentious topic but we've enjoyed using [Token2Shell/MD for Windows 10](https://www.microsoft.com/store/apps/9NBLGGH2NCX9). Some free alternatives are:
* [Bitvise SSH Client](https://www.bitvise.com/ssh-client-download) (includes SFTP support)
* [putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)

### SFTP Client
To transfer files to an from a linux server you'll want a [SFTP Client](https://en.wikipedia.org/wiki/Category:SFTP_clients). Our recommendations are:
* [Bitvise](https://www.bitvise.com/ssh-client-download) - includes SSH support recommended by @dudleycodes
* [WinSCP](http://winscp.net/) - can launch putty for ssh support; recommended by @JustinBenedick

## Working with SRCDS (Source Dedicated Server)

Once a dedicated Source server is running there are three ways to issues commands:
* In the sever's terminal window (not practical with our Docker setup)
* Connecting a game client and use rcon (can't be done with our tournament servers)
* **Using a 3rd-party, remote tool** (recommended)

There are really only two viable 3rd-party tools:

* [HLSW](http://www.hlsw.org/hlsw/download/) (depreciated but feature-full)
  * We recommend running the latest beta version "1.4.05"
  * [Read over the fixes list](https://hlswfixes.com/#about)

* [Source Admin Tool](https://users.alliedmods.net/~drifter/SAT/) (relatively new and light on features)
  * [Additional Info](https://forums.alliedmods.net/showthread.php?t=289370)

You're going to want both tools readily available as your work with SRCDS servers. Both tools work the same way: put in the server <ip>:<port> and rcon password and hit "get log".

## Working with Web-Tools

### An Alternative Web Browser

During the hustle and bustle of an event we recommend using a unique web browser for web-tools such as [Snippet Generator](https://github.com/LacledesLAN/Snippet-Generator). This makes the tool easy to find in your taskbar/dock and prevents accidentally closing the wrong tab as your use your normal browser(s) to navigate the web.

Some lesser-used alternative browsers include:
* [Brave](https://brave.com/)
* [Microsoft Edge](https://www.microsoft.com/en-us/windows/microsoft-edge)
* [Opera](http://www.opera.com/)