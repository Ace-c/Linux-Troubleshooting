
# Restoring GRUB Boot Entries

## Boot Into Live Environment
- You can use Arch ISO or any other Linux ISO available to you

## Mount Necessary Partitions

### 1. Find your partition
```bash
lsblk
```

### 2. Mount root partition
*Note: Replace `/dev/sda6` with your root partition*
```bash
mount /dev/sda6 /mnt
```

### 3. Mount EFI partition
*Note: Replace `/dev/sda5` with your EFI partition*
```bash
mount /dev/sda5 /mnt/boot
```

### 4. Bind System Directories
```bash
mount --bind /dev /mnt/dev
mount --bind /proc /mnt/proc
mount --bind /sys /mnt/sys
mount --bind /run /mnt/run
```

## Chroot Into The System
```bash
arch-chroot /mnt
```

## Reinstall GRUB and Add Boot Entries
```bash
grub-install --target=x86_64-efi --bootloader-id=ArchLinux --efi-directory=/boot/efi
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
