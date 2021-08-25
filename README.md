# dotfiles

Personal set of linux dotfiles / configuration files, handled through [chezmoi](https://www.chezmoi.io/docs/quick-start/)

## Regular commands

```bash
chezmoi add <filename>
```

```bash
chezmoi cd
git add . && git commit -m"Updates" && git push origin master
exit
```

## Misc

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
