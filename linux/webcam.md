## Logitech webcam settings

### Install

```sh
yaourt -S v4l-utils
```

### List devices & controls

```sh
v4l2-ctl --list-devices
v4l2-ctl -d /dev/video0 --list-ctrls
```

### Minimum settings

```sh
v4l2-ctl -d /dev/video0 --set-ctrl=exposure_auto=1
v4l2-ctl -d /dev/video0 --set-ctrl=focus_auto=0

# byko mode
v4l2-ctl -d /dev/video0 --set-ctrl=white_balance_temperature_auto=0
v4l2-ctl -d /dev/video0 --set-ctrl=white_balance_temperature=4800
v4l2-ctl -d /dev/video0 --set-ctrl=sharpness=180
v4l2-ctl -d /dev/video0 --set-ctrl=gain=10
v4l2-ctl -d /dev/video0 --set-ctrl=zoom_absolute=110
```
