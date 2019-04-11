# dotfiles-public-computers
The config files for public computers used in the Lab.


## Set up a computer using these dotfiles

A public lab (mac) computer should have a few software packages preinstalled. This is done by the use of homebrew and the dotmgr.
Use this guide as User ```fablabstaff```

The Brewfile is right now made for MacOS. But config files can also be useful for linux or BSD machines. For example configs for tmux, zsh, vi(m) and so on. So feel free to add dotfiles to this computer.
When your dotfiles are plattform specific use the "tags" from dotmgr to just apply (parts) of the configs depending on the used operating system.

### Installation

#### Install homebrew

Follow the instructions on https://brew.sh
(basically executing the following command in the terminal)
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

#### Make homebrew ready for multiuser usage
Guide inspired by: https://medium.com/@leifhanack/homebrew-multi-user-setup-e10cb5849d59

Create a group brew and add "Fab Lab Siegen"
One way to create a group brew is to open the System Preferences and select Users & Groups. Unlock this screen and press the lower left +. Select the account type Group and name it brew. After creating this group add all Fab Lab accounts on the computer.

Fab Lab Staff checks if he installed brew correctly
```
fablabstaff$ brew doctor
```

Change the group of homebrew installation directory

```
fablabstaff$ sudo chgrp -R brew $(brew --prefix)/*
Password:
```

```
fablabstaff$ ls -la $(brew --prefix)
```

Allow group members to write inside this directory

```
fablabstaff$ sudo chmod -R g+w $(brew --prefix)/*
fablabstaff$ ls -la $(brew --prefix)
```

"Fab Lab Siegen" checks if he can use homebrew

```
fablabsiegen$ brew doctor
Your system is raring to brew.
```

#### Install python3

```
brew install python
```


#### Install dotmgr
dotmgr from haggl can be found here https://gitlab.com/haggl/dotmgr

##### Installation
Installation instruction from dotmgr readme

It is important that you use the Python 3 version of pip. If in doubt, call pip3 explicitly:
```
pip3 install dotmgr
```

###### Initial run
Get the dotfiles from this repo
```
dotmgr -I https://github.com/FabLabSiegen/dotfiles-public-computers
```
Copy the dotfiles to your home
```
dotmgr -S
```

#### Install all packages listed in the Brewfile
brew bundle



