# Boot & GRUB topics

## When Windows f*cks up the dualboot

```sh
sudo su -
mount /dev/efi/partition /mnt/esp
mount /dev/my/linux/partition /mnt/linux
grub-install --target=x86_64-efi --efi-directory=/mnt/esp --bootloader-id=antergos_grub --boot-directory=/mnt/linux/boot
```

## Refs

  - [GRUB @ Arch Wiki](https://wiki.archlinux.org/index.php/GRUB)
  - [GNU GRUB Manual](https://www.gnu.org/software/grub/manual/grub/html_node/index.html)
