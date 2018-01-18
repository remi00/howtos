## NFS

### Client

Install:

```sh
sudo apt-get install portmap nfs-common # Ubuntu
```

Check endpoints:
```sh
showmount -e nas # Where nas is the IP address of your server
```

Automount - add to `/etc/fstab`:

```sh
server_ip_address:/nfs /mnt/nas nfs user,rsize=8192,wsize=8192,bg,timeo=14,intr 0 0
```

Better automount with `systemd` - add to `/etc/fstab`:

```sh
server_ip_address:/nfs /mnt/nas nfs noauto,noatime,nodiratime,x-systemd.automount,x-systemd.device-timeout=5min,timeo=14,x-systemd.idle-timeout=1min 0 0
```

References:
 - https://wiki.archlinux.org/index.php/NFS
 - https://ubuntuforums.org/showthread.php?t=2247237
 - https://ubuntuforums.org/showthread.php?t=2247242
 - https://ubuntuforums.org/showthread.php?t=2247242&page=2
