# dotfiles

Personal set of linux dotfiles / configuration files, handled through [chezmoi](https://www.chezmoi.io/docs/quick-start/)

## Regular commands

- **Initial installation** : 

```bash
cd /home/
sh -c "$(curl -fsLS git.io/chezmoi)"
```

- **Download dotfiles on a new server** : 

```bash
chezmoi init --apply SR-G
```

- **Add files** : 

```bash
chezmoi add <filename>
```

- **Commit added files** : 

```bash
chezmoi cd
git add . && git commit -m"Updates" && git push origin master
exit
```

- **Check, compare, apply** : 

```bash
chezmoi doctor
chezmoi diff
chezmoi -v apply
```

## Misc

### Git configuration

Reminder of manual GIT configuration

```bash
export VISUAL=vim
export EDITOR="$VISUAL"

git config --global user.name "SR-G"
git config --global user.email "serge.simon@gmail.com"

# Git cache on file (unencrypted)
git config --global credential.helper store

# Git cache in memory (with 1 year timeout (in seconds))
# git config --global credential.helper 'cache --timeout=31536000'
```

### yay install

```bash
pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```
