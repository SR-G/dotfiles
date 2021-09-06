# dotfiles

Personal set of linux dotfiles / configuration files, handled through [chezmoi](https://www.chezmoi.io/docs/quick-start/)

## Regular commands

- **Initial installation** : 

```bash
# Manual installation
cd /home/
sh -c "$(curl -fsLS git.io/chezmoi)"

# OS installation
pacman -S chezmoi
apt-get install -y chezmoi

# Setup (manual) + retrieve online files from github.com/<user>/dotfiles/
sh -c "$(curl -fsLS git.io/chezmoi)" -- init --apply SR-G

```

- **Download dotfiles on a new server** : 

```bash
chezmoi init --apply SR-G
```

- **Add files** : 

```bash
chezmoi add <filename>
chezmoi add --encrypt <filename>
chezmoi edit <filename>
```

- **Init remote URL (after init)** : 

```bash
git remote add origin https://github.com/SR-G/dotfiles
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

## TODO

- [ ] abcde configuration
- [ ] eclipse configuration + plugins ?
- [ ] .m2 maven configuration
- [ ] geany / notepadqq configuration
- [x] ssh config
- [ ] task configuration and aliases
- [ ] terminator configuration ?
- [ ] micro configuration https://micro-editor.github.io/
- [x] rclone safe configuration

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

### Extra tools

- chezmoi : https://github.com/twpayne/chezmoi
- STOW : https://github.com/aspiers/stow
- yadm : 
  - https://yadm.io/#
  - https://github.com/TheLocehiliosan/yadm
- dotenv (npm...) : https://github.com/motdotla/dotenv
- dotfilehub : https://github.com/knoebber/dotfile

### Extra links

- Dotfiles examples : 
  - https://yadm.io/docs/examples
  - https://github.com/vastbinderj/dotfiles
  - https://github.com/vsouza/dotfiles

- Discussions : 
  - Comparisons : https://www.chezmoi.io/docs/comparison/
  - dotfile : https://www.reddit.com/r/golang/comments/jt9yp7/dotfile_version_control_system_for_single_files/
  - using git : https://www.atlassian.com/git/tutorials/dotfiles
  - GNU Stow : https://medium.com/@waterkip/managing-my-dotfiles-with-gnu-stow-262d2540a866
  - discussion : https://news.ycombinator.com/item?id=11071754


