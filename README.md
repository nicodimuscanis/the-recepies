# Introduction
Welcome to my personal HowTo page!

# [Emacs-related recepies](https://github.com/nicodimuscanis/the-recepies/blob/master/using-emacs/README.md)

# [Vim-related recepies](https://github.com/nicodimuscanis/the-recepies/blob/master/using-vim/README.md)

# Set up WSL
Follow this https://linuxhint.com/install_ubuntu_windows_10_wsl/

# Connect drive to WSL
```
sudo mkdir -p /mnt/<drive-name>
sudo mount -t drvfs <drive-letter>: /mnt/<drive-name>
```
# Connect network drive to WSL
```
sudo mkdir -p /mnt/<drive-name>
sudo mount -t drvfs '\\server\folder' /mnt/<drive-name>
```
# How to install Cygwin on Windows XP
Follow this http://cygwin-xp.portfolis.net/

Briefly:
- you need `setup-x86.exe` version 2.874.
- run `setup-x86.exe -X` to prevent signature verification
- add `http://cygwin-xp.portfolis.net/cygwin` to the mirror list

Note, lates versions of `setup-x86[_64].exe` don't work on XP, even though you run it with `--allow-unsupported-windows` option you will not able to install Cygwin, because mirrors list will be empty. If you try to add either normal `http://cygwin.mirror.constant.com` or mirror with old versions from above `http://cygwin-xp.portfolis.net/cygwin` installation will fails anyways.

# How to install Cygwin packages in Debian `apt-get` manner
Tested on WinXP
1. Make sure you have `wget` installed on Cygwin
2. Take `apt-cyg` bash script from [here](https://raw.githubusercontent.com/transcode-open/apt-cyg/master/apt-cyg) and store it in `/usr/local/bin`
3. Don't forget `chmod u+x apt-cyg`

You are ready to install a package now. For example:
- `apt-cyg install git` -- will install git from previously used mirror site.
- `apt-cyg list` -- will list all installed packeges
- `apt-cyg` -- usage help.

# How to enable semihosting on STM ARM processor
1. Add `-specs=rdimon.specs -lc -lrdimon` into linker options
2. Make sure linker options also contain `-u _printf_float` and/or `-u _scanf_float`
3. Remove `-specs=nano.specs` from linker options if any.
4. Add `extern void initialise_monitor_handles(void);` into the code where functions such `printf` or `scanf` will be used
5. Call `initialise_monitor_handles();` before calling `printf`, `scanf` etc.
6. Add `printf`, `scanf` etc. into the code
7. Command `mon arm semihosting enable` in GDB, or add it into your GDB script
8. Flash and run the SW from GDB -- output will appear in OpenOCD window.
