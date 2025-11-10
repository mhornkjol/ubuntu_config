# Setup ubuntu

## Install must have packages

`sudo apt update && sudo apt upgrade` \
reboot \
`sudo apt install git make gcc gnome-tweaks curl whois`

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

## Install Obsidian

`sudo snap install obsidian --classic`
