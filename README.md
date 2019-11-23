# Introduction
Welcome to my personal HowTo page!

## [Emacs-related recepies](https://github.com/nicodimuscanis/the-recepies/blob/master/using-emacs/README.md)

## [Vim-related recepies](https://github.com/nicodimuscanis/the-recepies/blob/master/using-vim/README.md)

## Set up WSL
Follow to the https://linuxhint.com/install_ubuntu_windows_10_wsl/
## Connect drive to WSL
```
sudo mkdir -p /mnt/<drive-name>
sudo mount -t drvfs <drive-letter>: /mnt/<drive-name>
```
## Connect network drive to WSL
```
sudo mkdir -p /mnt/<drive-name>
sudo mount -t drvfs '\\server\folder' /mnt/<drive-name>
```
