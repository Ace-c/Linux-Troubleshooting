# Fixing Pop Sound in Linux Audio  

* Do Change the value of this config from 1 to 0.
sudo nano /sys/module/snd_hda_intel/parameters/power_save

* Do change the value to Y to N to this location
sudo nano /sys/module/snd_hda_intel/parameters/power_save_controller


Now, make the changes permanent:

1. Create File -
cd /etc/modprobe.d
sudo nano audio_disable_powersave.conf

2. Add the following line to newly created:
options snd_hda_intel power_save=0

3. Save the file and exit, then apply the changes by rebooting your system:
sudo reboot
