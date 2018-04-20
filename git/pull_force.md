# Git pull --force equivalent

Missing forced pull just found:

```sh
git fetch remote branch
git reset --hard FETCH_HEAD

# optionally, if needed:
git clean -df

# alternative
git fetch --all
git reset --hard origin/other_branch
```

References:
- [Tecadmin blog](https://tecadmin.net/force-overwrite-local-files-git-pull/)
- [Snowfrog](http://www.snowfrog.net/2012/12/03/git-pull-f-git-force-pull/)
