# Dotfiles

# Prerequisites

- i3-wm
- picom
- alacritty
- glava
- spotify
- feh
- i3lock
- i3bar
- i3blocks
- playerctl
- flameshot
- vim
- tmux
- fzf
- git
- virtualenv
- golang
- docker

# Backup

- conf i3 (~/.config/i3)
- conf tmux (~/.tmux.conf)
- conf inputrc (~/.inputrc)
- conf aliases 
- conf bashrc
- conf i3blocks (~/.config/i3blocks/config)
- conf alacritty (~/.config/alacritty)
- conf glava (~/.config/glava)

# Todo 
 
Un tool d'import/export de dotfiles, vis a vis d'un fichier yaml
-> Import : si les fichiers ne sont pas présent sur le disque, les deposes, sinon, verification de checksum/edit date, et on avise
-> Export : exporte la liste des fichiers dans le fichier de conf. Si y'a des conflits, on fait par rapport aux derniers edit date, avec une optiond de confirmation