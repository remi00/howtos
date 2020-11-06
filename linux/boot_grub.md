# Boot & GRUB topics

## When Windows f*cks up the dualboot

```sh
sudo su -
mount /dev/efi/partition /mnt/esp
mount /dev/my/linux/partition /mnt/linux
grub-install --target=x86_64-efi --efi-directory=/mnt/esp --bootloader-id=antergos_grub --boot-directory=/mnt/linux/boot
```

## When Manjaro update f*cks up itself

### GRUB rescue

- Media installation USB stick might be needed
- Restoring GRUB is mostly about reinstalling it with doing `chroot` first:

```sh
# go root
su
# mount regular linux partition (the one to rescue)
mount /dev/sdyC /mnt

# mostly unnecessary - boot partition if present
mount /dev/sdyB /mnt/boot

# mount EFI partition - required
mount /dev/sdyA /mnt/boot/efi

# create the chroot environment and use bash as shell ✨🎩🪄
manjaro-chroot /mnt /bin/bash

# reinstall grub 💗
pacman -Syu grub # rather optional
# for EFI:
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=manjaro --recheck
# for BIOS it is: grub-install --force --target=i386-pc --recheck --boot-directory=/boot /dev/sdy

# configure it
grub-mkconfig -o /boot/grub/grub.cfg
```

### Something went wrong

When the update screwed up during the process, it might be the case that desktop environment or some other software doesn't work. It's worth to force full reinstall of all packages. First of all `CTRL` + `ALT` + `F1` opens the terminal. And here is the trick found for pacman:

```sh
# go root
su

# list all packages
pacman -Qqen > pkglist
# reinstall packages from the file
pacman -S $(< pkglist)

# same as above with dependencies
pacman -Qqdn > pkglist_deps
pacman --asdeps -S $(< pkglist_deps)
```

## Refs

- [GRUB @ Arch Wiki](https://wiki.archlinux.org/index.php/GRUB)
- [GNU GRUB Manual](https://www.gnu.org/software/grub/manual/grub/html_node/index.html)
- [GRUB/Bootloader rescue](https://wiki.manjaro.org/index.php?title=GRUB/Restore_the_GRUB_Bootloader)
