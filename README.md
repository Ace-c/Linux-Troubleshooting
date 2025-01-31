

# Boot Into Live Environment

You can use Arch ISO or any other Linux ISO available to you.

## Mount Necessary Partitions

### Find your partition
```bash
lsblk

Mounting root partition

(Mount the partition where your distribution is installed)
bash
Copy

mount /dev/sda6 /mnt

Mounting EFI partition
bash
Copy

mount /dev/sda5 /mnt/boot

Bind System Directories
bash
Copy

mount --bind /dev /mnt/dev
mount --bind /proc /mnt/proc
mount --bind /sys /mnt/sys
mount --bind /run /mnt/run

Chroot Into The System
bash
Copy

arch-chroot /mnt

Reinstall GRUB and Add Boot Entries
bash
Copy

grub-install --target=x86_64-efi --bootloader-id=ArchLinux --efi-directory=/boot/efi

Update GRUB
bash
Copy

grub-mkconfig -o /boot/grub/grub.cfg

Exit And Reboot The System
bash
Copy

exit
umount -l /mnt
reboot
