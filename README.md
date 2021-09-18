## openSUSE after install
My setup after install openSUSE


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

<a id="terminal"></a>
**Terminal**
```
sudo zypper -n install tmux
```

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

