Dotfiles setup for stuff I'd want saved somewhere for a new system, mainly shell setup/styling.

# Setup

Setup assuming fresh Ubuntu system.

## Install zsh

Install zsh and make default shell:

```sh
sudo apt install zsh
chsh -s $(which zsh)
```

Restart system, then confirm change:

```sh
echo $SHELL
```

## Install oh-my-zsh

Install oh-my-zsh (for easy zsh plugins/themes):

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Set up symlinks

Run symlink setup script, which runs through each file in this repo and creates a symlinked file of where the "actual" dotfile is in the system:

```sh
./setup.sh
```

Note that if any files already exist it will throw an error, where you can review/remove/back-up any existing files. Feel free to just run any specific lines from `setup.sh`.
