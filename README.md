# Setup ubuntu

## Install must have packages

`sudo apt update && sudo apt upgrade` \
reboot \
`sudo apt install git make gcc gnome-tweaks curl pipx`

## Install fish

`sudo apt-add-repository ppa:fish-shell/release-3` \
`sudo apt-get update && sudo apt-get upgrade` \
`sudo apt-get install fish` \
Relog

## Install vim

`sudo apt install vim` \
Create `~/.vimrc`

## Install tmux

`sudo apt install tmux` \
Create `~/.tmux.conf`

### tmux catppuccin

`mkdir -p ~/.config/tmux/plugins/catppuccin` \
`git clone -b v2.1.3 https://github.com/catppuccin/tmux.git ~/.config/tmux/plugins/catppuccin/tmux` \
`git clone https://github.com/tmux-plugins/tmux-cpu ~/.config/tmux/plugins/tmux-plugins` \
`git clone https://github.com/tmux-plugins/tmux-yank ~/.config/tmux/plugins/tmux-plugins` \
Download a [nerdfont](https://www.nerdfonts.com/font-downloads) \
Unzip into ~/.fonts \
`fc-cache -fv`

## Catppuccin terminal

`curl -L https://raw.githubusercontent.com/catppuccin/gnome-terminal/v1.0.0/install.py | python3 -` \
`Edit -> Preferences -> Profile`

## Turn off terminal sound

`sudo vim /etc/inputrc`

Add line: \
set bell-style none \
under: \
`# do not bell on tab-completion`

## Keyd for caps -> esc

`git clone https://github.com/rvaiya/keyd` \
`cd keyd` \
`make && sudo make install` \
`sudo systemctl enable --now keyd` \
Create `/etc/keyd/default.conf`

## Install rust

`$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh`

## Install vsCode

Download [deb package](https://go.microsoft.com/fwlink/?LinkID=760868) \
`sudo apt install ./<file>.deb`

### Extensions

- davidanson.vscode-markdownlint
- eamodio.gitlens
- ms-python.black-formatter
- ms-python.debugpy
- ms-python.python
- ms-python.vscode-pylance
- vscodevim.vim
- rust-analyzer
- C/C++ Extension Pack

### Config

`config_files/settings.json`

### Keybindings

`config_files/keybindings.json`

## Python venv

`sudo apt install python3.12-venv` \
`python3 -m venv default` in `~/.virtualenvs`

## Install pwntools in venv

`source ~/.virtualenvs/default/bin/activate.fish` \
`python3 -m pip install pwntools`

## Install pwngdb

`curl -qsL 'https://install.pwndbg.re' | sh -s -- -t pwndbg-gdb`

## Install Ida

Install if necessary: \
`sudo apt install libxcb-xinerama0`

Download the installer from their [website](https://my.hex-rays.com/dashboard/download-center/installers/release). \
Download the license for their [website](https://my.hex-rays.com/dashboard/licenses).

Make the installer executable and run it.

Move the lisence file into the installation folder.

## Install uv

`curl -LsSf https://astral.sh/uv/install.sh | sh`

## Pentesting specific

### Install Obsidian

`sudo snap install obsidian --classic`

### Internet resources

- Netcraft - Info gathering for domains
- shodan - Internet scraping
- secutriy headers - Tests HTTP response
- SSL labs - Test SSL configuration

### Apt Packages

- `whois`
- `dnsenum`
- `freerdp2-x11`
- `nmap`
- `nbtscan` (NetNIOS enumeration)
- `onesixtyone` (SNMP enum)
- `snmp`
- `gobuster`
- `mysql-client-core-8.0`
- `hashcat`

### Snap packages

- `enum4linux` (SMB Enum. Potential bug in program when getting users)
- `powershell`

### Seclist

`wget -c https://github.com/danielmiessler/SecLists/archive/master.zip -O SecList.zip && unzip SecList.zip && rm -f SecList.zip`
`mv SecLists-master /usr/share`

### DNSRecon

```sh
git clone https://github.com/darkoperator/dnsrecon.git
cd dnsrecon
uv tool install dnsrecon
uv run dnsrecon / dnsrecon
```

Add DNSRecond folder to path.

### Nessus

Download from [website](https://www.tenable.com/downloads/nessus). Install the .deb file and follow instructions.

### Burb Suite

Download install script from website and run it. In firefox use localhost as proxy on port 8080 and socks proxy as localhost on 9060. In firefox go to about:config` and change `network.captive-portal-service.enabled` to false

### SQL

Install [impacket](https://github.com/fortra/impacket) for mssql.

```sh
python3 -m pipx install impacket
```

run with `mssqlclient.py`

Download [sqlmap](git clone --depth 1 https://github.com/sqlmapproject/sqlmap.git sqlmap-dev) and add to path. Change sqlmap.py to use python3 instead of python.

### Fuzzing

[fuff](https://github.com/ffuf/ffuf)

```sh
sudo apt install golang-go
git clone https://github.com/ffuf/ffuf
cd ffuf
go get
go build
```

Can just apt install it...

### Install metasploit

`curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall && chmod 755 msfinstall && ./msfinstall`

### wpscan

```sh
sudo apt install ruby-rubygems
sudo apt install ruby-dev
gem install wpscan
```
