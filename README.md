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

sudo zypper in openssh
sudo zypper in git



<a id="databases"></a>
**Databases Clients**
```
sudo zypper -n install mysql-clients
sudo zypper -n install postgresql-libs
```

<a id="terminal"></a>
**Terminal**
```
sudo zypper -n install tmux
```

<a id="browser"></a>
**Browsers**
```shell
sudo zypper -S lynx
```


<a id="games"></a>
**Games**
```shell
sudo zypper -n install snex9x
wget https://github.com/stella-emu/stella/releases/download/6.5.3/stella-6.5.3-2.x86_64.rpm -O stella.rpm
```
