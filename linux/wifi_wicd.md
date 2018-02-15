# Wifi network management using Wicd

As `NetworkManager` pretty often causes problems, Wicd comes to the rescue. See [this Arch doc](https://wiki.archlinux.org/index.php/Wicd) for details.

```sh
yaourt -S wicd wicd-gtk notification-daemon python2-notify

# disable any wifi mgmt daemons, like netctl, netcfg, dhcpd, network
sudo systemctl stop NetworkManager
sudo systemctl disable NetworkManager

# enable wicd
sudo systemctl enable wicd.service
sudo systemctl start wicd.service
sudo systemctl status wicd.service
```
