## Powersave tips


### HDparm

```sh
sudo apt update
sudo apt install hdparm

lsblk

sudo hdparm -y /dev/sdX

# The -B option sets the APM level, and the -S option sets the spin-down timeout.
sudo hdparm -B127 -S120 /dev/sdX
```

#### Automatic config

```sh
# /etc/hdparm.conf

/dev/sdX {
    apm = 127
    spindown_time = 120
}

# - apm = 127: This setting enables a moderate power-saving mode without being too aggressive. Ranges from 1 (aggressive power saving) to 254 (no power saving), with 255 disabling APM.
#	- spindown_time = 120: The time in 5-second intervals after which the drive will spin down (120 means 10 minutes). Ranges from 1 to 240, where each unit represents 5 seconds (so 240 means 20 minutes).

```
