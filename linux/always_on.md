## Always on - disable suspend

### Logind

```sh
# /etc/systemd/logind.conf

HandleLidSwitch=ignore
HandleLidSwitchExternalPower=ignore
HandleLidSwitchDocked=ignore
HandleSuspendKey=ignore
HandleHibernateKey=ignore
HandlePowerKey=ignore
```

```sh
sudo systemctl restart systemd-logind
```

### GNOME Settings

```sh
sudo apt install dbus-x11
dbus-launch gsettings set org.gnome.settings-daemon.plugins.power sleep-inactive-ac-type 'nothing'
sudo dbus-launch gsettings set org.gnome.settings-daemon.plugins.power sleep-inactive-ac-type 'nothing'
```
