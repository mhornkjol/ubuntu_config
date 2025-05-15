# Setup ubuntu

## Install must have packages

`sudo apt update && sudo apt upgrade` \
reboot \
`sudo apt install git make gcc gnome-tweaks curl`

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
Create `/etc/keyd.default`

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

### Config

`config_files/settings.json`
