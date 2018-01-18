## Shell stuff

Start with making sure pip is the newest one:

```sh
pip install --upgrade pip
```


### ZSH

Install Oh My Zsh

```sh
chsh -s $(which zsh)
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Install Powerline-patched fonts

```sh
git clone https://github.com/powerline/fonts.git ~/powerline && cd ~/powerline && ./install.sh
```

Install Bullet-train theme

```sh
mkdir -p $ZSH_CUSTOM/themes && cd $ZSH_CUSTOM/themes
wget http://raw.github.com/caiogondim/bullet-train-oh-my-zsh-theme/master/bullet-train.zsh-theme
```

Update configuration in `.zshrc`

```sh
ZSH_THEME="bullet-train"

BULLETTRAIN_PROMPT_ORDER=(
  time
  dir
  git
  nvm
  status
)
```

### Tilix

Install:
```sh
yaourt -S tilix
```

Fix for VTE Terminal issue:

```sh
ln -s /etc/profile.d/vte-2.91.sh /etc/profile.d/vte.sh
```

And into `.zshrc`:
```sh
if [ $TILIX_ID ] || [ $VTE_VERSION ]; then
   source /etc/profile.d/vte.sh
fi
```


For Ubuntu additionally run:

```sh
ln -s /etc/profile.d/vte-2.91.sh /etc/profile.d/vte.sh
```
