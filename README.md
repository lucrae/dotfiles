Dotfiles, setup based on [Šimon Tóth's simple approach](https://medium.com/@simontoth/best-way-to-manage-your-dotfiles-2c45bb280049).

# Setup

```sh
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
git clone --bare git@github.com:lucrae/dotfiles.git $HOME/.dotfiles
dotfiles config --local status.showUntrackedFiles no
dotfiles checkout
```

And all should be set up!

If there are already some of the dotfiles present, you will see this error:

```
error: The following untracked working tree files would be overwritten by checkout:
 .bashrc
Please move or remove them before you switch branches.
Aborting
```

Remove or back up any collisions and repeat the checkout:

```sh
mv ~/.bashrc ~/.bashrc_backup
dotfiles checkout
```

# Adding/updating files

Use `dotfiles` as an alias for `git`.

For example:

```sh
dotfiles add ~/.zshrc
dotfiles commit -m 'Description...'
dotfiles push
```

(If `dotfiles push` does not work try `dotfiles push -u origin main`)


