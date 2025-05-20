# Fixing Pop Sound in Linux 


* Change the value of this config, from 1 to 0
```
sudo nano /sys/module/snd_hda_intel/parameters/power_save
```

* Change the value " Y to N " to this config 
```
sudo nano /sys/module/snd_hda_intel/parameters/power_save_controller
```

### Now, make the changes permanent:

* Create File in this location **/etc/modprobe.d**
```
sudo nano audio_disable_powersave.conf
```
* Add the following line to newly created:
```
options snd_hda_intel power_save=0
```

* Save the file and exit, then apply the changes by rebooting your system:
sudo reboot
