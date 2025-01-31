# Guide to restore boot entry in Arch Linux

Boot Into live Envirnoment -

You can use arch iso 
or whatever other linux iso availabe to you

Mount Necessary Partitions :

Find your partition 
lsblk

Mounting root partition (You have put your parition there In which your distro was Inst.)
mount /dev/sda6 /mnt

Mouting EFI partition
mount /dev/sda5 /mnt/boot

Bind System Directories 
mount --bind /dev /mnt/dev
mount --bind /proc /mnt/proc
mount --bind /sys /mnt/sys
mount --bind /run /mnt/run

Chroot Into The System :
arch-chroot /mnt

Reinstall GRUB and Add Boot Entries :
grub-install --target=x86_64-efi --bootloader-id=ArchLinux --efi-directory=/boot/efi

Update grub
grub-mkconfig -o /boot/grub/grub.cfg

Exit And Reboot The System 
exit
umount -l /mnt
reboot
