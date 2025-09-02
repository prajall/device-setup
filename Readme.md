

# Install git

```bash
sudo apt install git
```
# ThunderBird
```bash
sudo apt install thunderbird
```

# Mattermost
Download amd .deb file for mattermost  https://github.com/mattermost/desktop/releases/tag/v5.13.0
```bash
cd ~/Downloads
sudo dpkg -i ./mattermost-desktop_5.13.0-1_amd64.deb
```


# Install Zsh shell

```bash
sudo apt install zsh -y
chsh -s $(which zsh)
```
open terminal and choose option 0 to create empty .zshrc file

install oh-my-zsh
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
configure zsh
```bash
nano ~/.zshrc
```
paste the configuration.
```bash
# Path to your Oh My Zsh installation.
export ZSH="$HOME/.oh-my-zsh"


ZSH_THEME="itchy"

plugins=(zsh-autosuggestions)

source $ZSH/oh-my-zsh.sh
export PATH="$PATH:/opt/nvim/"

``` 

to change zsh theme goto: https://github.com/ohmyzsh/ohmyzsh/wiki/themes
and write name of theme in the .zshrc file


# Kitty Terminal

```bash
sudo apt install Kitty
```
copy the configuration to correct path:
```bash
git clone https://github.com/prajall/kitty-config.git ~/.config/kitty
```
set kitty as default terminal
```bash
sudo update-alternatives --install /usr/bin/x-terminal-emulator x-terminal-emulator /usr/bin/kitty 50
sudo update-alternatives --config x-terminal-emulator
```


# Neovim

First install curl and nodejs:
```bash
sudo apt install curl
sudo apt install nodejs npm -y
```

Download .AppImage file for neovim and make it executable
```bash
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux-x86_64.appimage
chmod u+x nvim-linux-x86_64.appimage
```

To make vim expose globally
```bash
mkdir -p /opt/nvim
mv nvim-linux-x86_64.appimage /opt/nvim/nvim
```
```bash
export PATH="$PATH:/opt/nvim/"
```

Nvim is ready, now setup packages and configurations:


```bash
# Install GCC and luarocks
sudo apt install build-essential gcc make unzip git curl
sudo apt install lua5.1 liblua5.1-0-dev luarocks
```
```bash
git clone https://github.com/prajall/nvim-config.git ~/.config/nvim
```
to enable yanking and pasting to system clipboard, install xclip:
```bash
sudo apt install xclip
``` 


# Chrome
```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo apt install ./google-chrome-stable_current_amd64.deb
```

# Popshell
```bash
sudo apt install git node-typescript make gnome-shell-extension-prefs
```
```bash
git clone https://github.com/pop-os/shell.git
cd shell
git checkout master_jammy
```
build the package
```bash
make local-install
```
you need add your gnome version in the metadata.json's shell-version array.
```bash
# check your gnome version
gnome-shell --version
# edit metadata.json
nano metadata.json
# add your gome version eg:"48"
```
finally restart your pc

