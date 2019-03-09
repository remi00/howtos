## ZSH

### Recursively do something

Unzip all .zip files in directory with just basename as folder names.

```
for FILE in  *.zip; do unzip $FILE -d ${FILE:r}; done
```
