# diskord-zifpau | a Chat Client for Lojbanistan

**diskord-zifpau** is a special configuration of
[BetterDiscord](https://betterdiscord.net/home/) which is a
customizable front-end for the [Discord](https://discordapp.com/) chat client.

## Installation Instructions for Ubuntu Linux

### Remove Any Existing Discord Installation

We're going to install Discord (in a particular way) and
BetterDiscord. If you have any existing Discord installation, you best
get rid of it and any traces of it! Configuration files included! **To
remove an existing Discord installation installed through a package
manager, you can try:**

```
apt-get purge discord
```

If you don't already have Discord installed, no worries! Just skip
this step and move on.

### Installing Dependencies

Make sure you have all of the dependencies installed you'll need.

```
sudo apt update
sudo apt install npm nodejs-legacy
```

### Installing Discord, the Compatible Way

We are going to install Discord through our installation of
BetterDiscord. BetterDiscord works to modify the CSS/HTML/JavaScript
of Discord.

Let's make a directory to put our installation in!

```
mkdir discord
cd discord
```

We're going to install Discord (not through the package manager!). First,
use `wget` to get __Discord Canary__, the beta Linux build of Discord,
from the Internet.

```
wget "https://discordapp.com/api/download/canary?platform=linux&format=tar.gz" -O discord-canary.tar.gz
```

Let's unpack that tar-ball, i.e. decompress the compressed folder.

```
tar -xzvf discord-canary.tar.gz
```

Now that we have the Discord executable, let's do some copying and
symbolic linking.

```
sudo cp -r DiscordCanary /opt/
sudo ln -s /opt/DiscordCanary/DiscordCanary /usr/bin/discord
```

### Installing diskord-zifpau

Let's grab BetterDiscord using `git`.

```
git clone https://github.com/diskord-zifpau/BetterDiscordApp.git
```

Move some stuff around.

```
mv BetterDiscordApp BetterDiscord
cp BetterDiscord/Installers/Node/* .
cp BetterDiscord/splice .
```

Let's install! Finally!

```
npm install asar wrench
sudo ./install.sh
```

### Uninstalling diskord-zifpau

```
sudo rm -f $(which discord)
sudo rm -rf /opt/DiscordCanary/
```

## Installation Instructions for Mac OSX

I don't own a Mac, but you can try to install this and then add the
configuration files by hand.

```
https://github.com/iVEnoVaLue/BetterPlugins/blob/master/app/OSX/Installer/BetterDiscord.pkg
```

## Installation Instructions for Windows

I don't have Windows, but install through their main website since
Windows is officially supported and add the configuration files by
hand.

```
https://github.com/Jiiks/BetterDiscordApp/releases/download/0.2.82/BD0.2.82Windows.zip
```
