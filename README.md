# Dotfiles

## Prerequisites

- i3-wm
- picom
- alacritty
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

## bashrc

Add this

```bash
# useful functions
function mkcd(){
mkdir $1
cd $1
}

function td(){
directory=$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1)
mkdir /tmp/$directory
cd /tmp/$directory
}

function tf(){
file=tf-$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 5 | head -n 1)
vim /tmp/$file
echo $file
}

function cl() {
    DIR="$*";
        # if no DIR given, go home
        if [ $# -lt 1 ]; then
                DIR=$HOME;
    fi;
    builtin cd "${DIR}" && \
    # use your preferred ls command
        ls
}

export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
export TZ='Europe/Paris'
export PATH="$HOME/.poetry/bin:$HOME/.local/bin/:$HOME/.dotfiles/bin:$HOME/.cargo/bin/:$PATH"
export PROMPT_COMMAND='history -a'

source $HOME/.dotfiles/bash/bash_completion
```

## Backup

- conf i3 (~/.config/i3)
- conf tmux (~/.tmux.conf)
- conf inputrc (~/.inputrc)
- conf aliases
- conf bashrc
- conf i3blocks (~/.config/i3blocks/config)
- conf alacritty (~/.config/alacritty)

```
sudo ln -sn $HOME/.dotfiles/i3 .config/i3
sudo ln -sn $HOME/.dotfiles/i3blocks/ .config/i3blocks
sudo ln -sfn $HOME/.dotfiles/alacritty/ .config/alacritty
sudo ln -sfn $HOME/.dotfiles/bash/inputrc .inputrc
sudo ln -sfn $HOME/.dotfiles/tmux/tmux.conf .tmux.conf
sudo ln -sfn $HOME/.dotfiles/bash/bash_aliases .bash_aliases
```

## Todo

Un tool d'import/export de dotfiles, vis a vis d'un fichier yaml
-> Import : si les fichiers ne sont pas présent sur le disque, les deposes, sinon, verification de checksum/edit date, et on avise
-> Export : exporte la liste des fichiers dans le fichier de conf. Si y'a des conflits, on fait par rapport aux derniers edit date, avec une optiond de confirmation