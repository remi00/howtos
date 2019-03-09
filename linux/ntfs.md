## NTFS

After months of trying UDF, ext4 for Windows etc, finally NTFS seem to be supported best across various OSes. With `/etc/fstab` entries and doing setuid-root for ntfs-3g it's also possible to mount nicely in home directory.

```shell
chown root $(which ntfs-3g)
chmod 4755 $(which ntfs-3g)
```

### `/etc/fstab` entries

```shell
UUID=CAFEBABE123465 /home/user/windows ntfs-3g uid=user,gid=users,dmask=022,fmask=133 0 0
```
- [NTFS-3G Arch Linux](https://wiki.archlinux.org/index.php/NTFS-3G)
- [NTFS 3G Tuxera FAQ](https://www.tuxera.com/community/ntfs-3g-faq/)

