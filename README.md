# TODO: Figure out way to keep wsl docker container running in background 

# Arch setup
[Arch config](https://wsldl-pg.github.io/ArchW-docs/How-to-Setup/#setup-after-install)

### Set network mode to 'mirrored' in wsl settings

## Root user password
```
passwd
```
```
echo "%wheel ALL=(ALL) ALL" > /etc/sudoers.d/wheel
```
## User setup
```
useradd -m -G wheel -s /bin/bash {username}
```
```
passwd {username}
```
## Set default user
```
Arch.exe config --default-user {username}
```
## Pacman setup
```
sudo pacman-key --init
```
```
sudo pacman-key --populate
```
```
sudo pacman -Sy archlinux-keyring
```
```
sudo pacman -Su
```

## Install packages
```
sudo pacman -S git docker docker-compose htop wget neovim
```
## Setup script
```
./setup
```

# Post-Setup

## Start script
```
wsl --shell-type login startServer
```
## Stop script
```
wsl --shell-type login stopServer
```
## Add discord chat permission
```
lp group default permission set essentials.discord.receive.chat
```



## WSL Network slow fix
```
netsh winsock reset
```
```
netsh int ip reset all
```
```
netsh winhttp reset proxy
```
```
ipconfig /flushdns
```
