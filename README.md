## openSUSE after install
My setup after install openSUSE Leap 15.3


- [IDE's](#ides)
- [System](#system)
- [Security](#security)
- [Git](#git)
- [Games](#games)
- [Databases](#databases)
- [Languages](#languages)
- [Terminal](#terminal)
- [Browsers](#browser)
- [Video](#video)
- [Audio](#audio)
- [Docker](#docker)
- [Javascript packages](#jspackage)
- [Comumunicators](#communicators)
- [CLI's](#cli)


<a id="system"></a>
Update the system
```shell
sudo zypper ref && sudo zypper up
```

<a id="system"></a>
**System**
```shell
sudo zypper -n install cowsay fortune
sudo zypper -n install htop
sudo zypper -n install glances
sudo zypper -n install putty
sudo zypper -n install neofetch
sudo zypper -n install pv
sudo zypper -n install lsof
sudo zypper -n install net-tools
sudo zypper -n install dstat
sudo zypper -n install albert
```

**Login**

Hide user from login list using Gnome. 

Create the file /etc/dconf/profile/gdm
```
user-db:user
system-db:gdm
file-db:/usr/share/gdm/greeter.dconf-defaults
```

Create the directory:
```
sudo mkdir /etc/dconf/db/gdm.d
```

Create the file `/etc/dconf/db/gdm.d/00-login-screen`:
```
[org/gnome/login-screen]
# Do not show the user list
disable-user-list=true
```

Execute
```
$ sudo dconf update
```

**Turn off screen rotation**
```
sudo systemctl stop iio-sensor-proxy.service
sudo systemctl disable iio-sensor-proxy.service
sudo zypper remove iio-sensor-proxy
```

**External Repositories**
```
sudo zypper ar -cfp 90 'https://ftp.gwdg.de/pub/linux/misc/packman/suse/openSUSE_Leap_$releasever/' packman
sudo zypper dup --from packman --allow-vendor-change
```

<a id="system"></a>
**Git**
```
sudo zypper in openssh
sudo zypper in git
```

```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/vscode.repo'
sudo zypper refresh
sudo zypper -n install code
```


<a id="databases"></a>
**Databases Clients**
```
sudo zypper addrepo https://download.opensuse.org/repositories/server:/database/openSUSE_Leap_15.3/server:database.repo
sudo zypper refresh
sudo zypper -n install mysql-utilities
sudo zypper -n install postgresql12-devel
```

<a id="heroku"></a>
**Heroku**
```shell
sudo curl https://cli-assets.heroku.com/install.sh | sh
```

<a id="languages"></a>
**asdf**
Clone the repository
```
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.9.0
```

Add the following to `~/.bashrc`
```
. $HOME/.asdf/asdf.sh
. $HOME/.asdf/completions/asdf.bash
```

Update your current shell environment
```
source ~/.bashrc
```

<a id="terminal"></a>
**Terminal**
```
sudo zypper -n install tmux
```


<a id="ides"></a>
**Eclipse**
Dowload the package on https://www.eclipse.org/.
Extract the package and start the installer.
```
tar -xf eclipse-inst-jre-linux64.tar.gz
cd eclipse-installer
./eclipse-inst
```

And follow the instructions.

<a id="browser"></a>
**Browsers**
```shell
sudo zypper -n install lynx
sudo zypper -n install chromium
```

sudo zypper -n install vlc

<a id="games"></a>
**Games**
```shell
sudo zypper -n install steam

**snes9x**
zypper addrepo https://download.opensuse.org/repositories/home:mnhauke:games/openSUSE_Leap_15.2/home:mnhauke:games.repo
zypper refresh
sudo zypper -n install snes9x

**Stella**
wget https://github.com/stella-emu/stella/releases/download/6.5.3/stella-6.5.3-2.x86_64.rpm -O stella.rpm
sudo rpm -i stella.rpm
```

**Genesis**
```
sudo zypper in mednafen
```

<a id="docker"></a>
**Docker**
```shell
sudo zypper addrepo https://download.docker.com/linux/sles/docker-ce.repo
sudo zypper -n in docker
sudo zypper -n in docker
sudo systemctl start docker
sudo systemctl enable docker
sudo gpasswd -a "${USER}" docker
reboot
```

**Node**
Using _Node Version Manager_
```shell
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```

Execute  `source ~/.bashrc`

List the versions
```
nvm ls-remote
```

Choice the version to install
```
nvm install [x.x.x]
```

