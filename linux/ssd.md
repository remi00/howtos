## SSD

Fstrim the SSD every day instead of weekly:

```sh
sudo mv -v /etc/cron.weekly/fstrim /etc/cron.daily
```

Don't update access time all the time, edit `/etc/fstab`:

```sh
UUID=xxxxx   /   ext4 noatime,errors=remount-ro   0   1
```
