## NodeJS environment

### NVM

Install:

```sh
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
```

This should also add to `.zshrc`:

```sh
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```


### Nodenv

Install:

```sh
git clone https://github.com/nodenv/nodenv.git ~/.nodenv
cd ~/.nodenv && src/configure && make -C src
echo 'export PATH="$HOME/.nodenv/bin:$PATH"' >> ~/.zshrc
~/.nodenv/bin/nodenv init

type nodenv # => "nodenv is a function"
```

Node build plugin:

```sh
git clone https://github.com/nodenv/node-build.git $(nodenv root)/plugins/node-build
```
