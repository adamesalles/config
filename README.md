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


