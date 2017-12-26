## Git Aliases

Useful set of aliases, stolen from [Tim Pettersen blogpost](https://hackernoon.com/lesser-known-git-commands-151a1918a60).

```sh
git config --global alias.please 'push --force-with-lease'
git config --global alias.commend 'commit --amend --no-edit'
git config --global alias.it '!git init && git commit -m “root” --allow-empty'
git config --global alias.stsh 'stash --keep-index'
git config --global alias.staash 'stash --include-untracked'
git config --global alias.staaash 'stash --all'
git config --global alias.shorty 'status --short --branch'
git config --global alias.grog 'log --graph --abbrev-commit --decorate --all --format=format:"%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(dim white) - %an%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n %C(white)%s%C(reset)"'
```
