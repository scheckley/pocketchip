### Flash the chip
https://github.com/Thore-Krug/Flash-CHIP
### Change password:
`passwd`
### Connect to wifi:
`nmtui`
### SSH the pocketchip from an other pc (because the colon is not accessible)
`ssh chip@192.168.1.xxx`
### Update repo:
in `/etc/apt/sources.list`
```diff
- deb http://opensource.nextthing.co/chip/debian/repo jessie main
+ deb http://chip.jfpossibilities.com/chip/debian/repo jessie main
```
http://chip.jfpossibilities.com/chip/debian/
### Update packages:
`sudo apt-get update`
### Upgrade packages:
`sudo apt-get upgrade`
### Install kbd zsh emacs git vim locales:
`sudo apt-get install zsh emacs git vim locales console-setup`
### install oh-my-zsh
`sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
### Reduce font size:
`sudo dpkg-reconfigure console-setup`
### Select utf8
`sudo dpkg-reconfigure locales`
select `en_US.UTF-8 UTF-8` then `en_US.UTF-8`
### get this repo:
`git clone https://github.com/apare/pocketchip.git`
### Allowed execute keymap:
`chmod +x ~/pocketchip/keymap.sh`
###  Setup keymap
Add `/usr/bin/loadkeys /home/chip/pocketchip/keymap.kmap` in `/etc/rc.local`

### Note:
The default key mapping (courtesy of /home/chip/.Xmodmap) maps the hyphen key as the numeric keypad hyphen. Apparently some software doesn't like that; when searching a man page via /, typing - would give screwy results (not fun if you're trying to search for a specific command-line switch). If you want to correct this, edit .Xmodmap and change these two lines (I'd recommend changing the + key as well), then run "xmodmap .Xmodmap" from the terminal: keycode 82 = minus underscore F11 minus ke…

### Add to `~/.zshrc`
```
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
export LANGUAGE=en_US.UTF-8

source ~/pocketchip/keymap.sh
clear
```
## Adding a ssh key
### generate a new ssh key
`ssh-keygen -t rsa -b 4096 -C "email.address"`
### show the public ssh key (you need to add it to github)
`cat ~/.ssh/id_rsa.pub`

### install nodejs
https://github.com/nodesource/distributions/blob/master/README.md#deb
don't forget to run `apt-get install -y build-essential` to have access to npm
