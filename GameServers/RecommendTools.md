## Recommended Tools for Game Server Operators

### GIT Client

Our game server repositories and custom tools (such as [Snippet Generator](https://github.com/LacledesLAN/Snippet-Generator)) are stored in [GitHub](https://github.com/LacledesLAN).

You'll need a GIT client to obtain ("clone") and update ("fetch") the latest versions. If you're a pro you can use the [git command line tools](https://git-scm.com/) or a more advanced GIT client like [GitKraken](https://www.gitkraken.com/).

If you're new to GIT or don't need advanced features **we recommend using the [GitHub Desktop Client](https://desktop.github.com/)**.

### An Alternative Web Browser

When using a webtool (such as [Snippet Generator](https://github.com/LacledesLAN/Snippet-Generator)) we recommend keeping it open in a browser you don't use for anything else. This will make it fast to find in your taskbar and make sure you don't accidentally close it as you navigate the web in your normal browser. Some alternative browers include [Brave](https://brave.com/), [Opera](http://www.opera.com/), or event [Microsoft Edge](https://www.microsoft.com/en-us/windows/microsoft-edge).

### SSH
You'll need an SSH client to connect to our Linux servers running Docker. This can be a pretty contested subject but we've enjoyed using [Token2Shell/MD for Winodws 10](https://www.microsoft.com/store/apps/9NBLGGH2NCX9). Some alternatives are:
* [putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
* [bitvise](https://www.bitvise.com/ssh-client-download) - Dudley's prefered backup client; includes SFTP support.
* [SecureCRT](https://www.vandyke.com/products/securecrt/index.html) - Paid; 30-day trial availabl (see below)

### SFTP Client
To transfer files to an from a linux server you'll need a SFTP Client. Some recommendations are:
* [bitvise](https://www.bitvise.com/ssh-client-download) - Dudley's recommendation.
* [WinSCP](http://winscp.net/) - BEan's recommendation; can launch Putty terminal


### Text Editor
For text editing we recommend [Visual Studio Code](https://code.visualstudio.com/) as we are updating all of your game server repos to use its features. To take full advantage of our setup install the plugins [Docker Support for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker), [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig), and [VSCode Great Icons](https://marketplace.visualstudio.com/items?itemName=emmanuelbeziat.vscode-great-icons).

Alternatives:
* [Notepad++](https://notepad-plus-plus.org/) (Windows
* TextEdit (Apple; included with Mac OS)

### Source Server Remote Tools
Once a dedicated Source server is running there are three ways to issues commands:
* In the sever's terminal window (not practical with our Docker setup)
* Connecting a game client and use rcon (can't be done with our tournament servers)
* **Using a 3rd-party, remote tool** (recommended)

There are really only two viable 3rd-party tools:

* [HLSW](http://www.hlsw.org/hlsw/download/) (depreciated)
  * We recommend running the latest beta version "1.4.05"
  * [Read over the fixes list](https://hlswfixes.com/#about)

* [Source Admin Tool](https://users.alliedmods.net/~drifter/SAT/) (relatively new and under active development
  * [Additional Info](https://forums.alliedmods.net/showthread.php?t=289370)

Both tools work the same way. Put in the server <ip>:<port> and rcon password and hit "get log".
