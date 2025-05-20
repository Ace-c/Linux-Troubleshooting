# Fixing Irritating Pop Sound in Linux 


* Change the value from 1 to 0, to this config file :
```
sudo nano /sys/module/snd_hda_intel/parameters/power_save
```

* Also, Change the value " Y to N " to this one too
```
sudo nano /sys/module/snd_hda_intel/parameters/power_save_controller
```

### Now, make the changes permanent:

* Create File to this location **/etc/modprobe.d**
```
sudo nano audio_disable_powersave.conf
```
* Add the following line to it:
```
options snd_hda_intel power_save=0
```

* Save the file and exit.
* Reboot your system, to check wheather it's working or not.
