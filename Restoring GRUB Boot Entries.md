
# Restoring GRUB Boot Entries

## Boot Into Live Environment
- You can use Arch ISO or any other Linux ISO available to you

## Mount Necessary Partitions

### 1. Find your partition
```bash
lsblk
```

### 2. Mount root and boot partition
```bash
mount /dev/sda1 /mnt
```
> Replace `/dev/sda1` with your root partition*

```bash
mount /dev/sda2 /mnt/boot
```
> Replace `/dev/sda2` with your /boot partition*


### 4. Bind System Directories
```bash
mount --bind /dev /mnt/dev
mount --bind /proc /mnt/proc
mount --bind /sys /mnt/sys
mount --bind /run /mnt/run
```

### 5. Chroot Into The System
```bash
arch-chroot /mnt
```

## Reinstall GRUB and Add Boot Entries :
1. For UEFI
```bash
grub-install --target=x86_64-efi --bootloader-id=ArchLinux --efi-directory=/boot/efi
```
2. For BIOS/Legacy
```
grub-install --target=i386-pc /dev/sda2
```
### Update GRUB
```bash
grub-mkconfig -o /boot/grub/grub.cfg
```

## Exit And Reboot The System
```bash
exit
umount -l /mnt
reboot
```
