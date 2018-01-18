## Other software packages

### Chrome Beta

On Ubuntu:

```sh
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
sudo sh -c 'echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
sudo apt-get install google-chrome-beta
```

On Arch, just:

```sh
yaourt -S google-chrome-beta
```

### XnView

Best image management software that has Linux version.

Ubuntu: http://www.xnview.com/en/xnviewmp/#downloads

Arch:

```sh
yaourt -S xnviewmp
```

### Nethogs

Htop for network

```sh
yaourt -S nethogs
```


### Peek

Simple screen recorder with an easy to use interface

https://github.com/phw/peek

```sh
yaourt -S peek
```

