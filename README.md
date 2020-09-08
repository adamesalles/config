# My dotfiles and scripts on my DWM Arch config

---

![Eduardo](https://images7.memedroid.com/images/UPLOADED672/5eb5b3f19c9a8.jpeg)

> Eduardo

Listen to [this song](https://www.youtube.com/watch?v=lDLEsnXauwU) if you want to feel the meme.

## It's just for not losing all the time I've invested on this.

Visit me on my blog: [eduadame](https://eduadame.netlify.app)

---

## Vim Files

It's a combo that uses `Vim`, `LaTeX` and `Livepreview`

To get this to work, you just have to:

Install `LaTeX`
```bash
sudo pacman -S texlive-most
```
Install Vundle
```bash
mkdir ~/.vim/bundle/
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

Install zathura
```bash
sudo pacman -S zathura
```

Run on terminal
```bash
vim +PluginInstall +qall
```

---

## To install this config files on a local machine

Place this piece of code on `.bashrc` or `.zshrc`
```bash
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
```
And then:
```bash
echo ".cfg" >> .gitignore
git clone --bare github.com/adamesalles/config $HOME/.cfg
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
```
Backup your old dotfiles
```bash
mkdir -p .config-backup && \
config checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | \
xargs -I{} mv {} .config-backup/{}
```

```
config checkout
config config --local status.showUntrackedFiles no
```

This bash script may run:
```bash
git clone --bare https://bitbucket.org/durdn/cfg.git $HOME/.cfg
function config {
   /usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME $@
}
mkdir -p .config-backup
config checkout
if [ $? = 0 ]; then
  echo "Checked out config.";
  else
    echo "Backing up pre-existing dot files.";
    config checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | xargs -I{} mv {} .config-backup/{}
fi;
config checkout
config config status.showUntrackedFiles no
```
---

This is a fork of [my old repo](https://github.com/adamesalles/voidrice), the main difference is that this now is a bare repo.
