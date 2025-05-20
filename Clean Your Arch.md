
## 1. Package Cleansing :

### Clear Package Cache :

* List packages
```
sudo ls /var/cache/pacman/pkg/ | wc -l
```
* Check disk space used by cache folder
```
du -sh /var/cache/pacman/pkg/
```


### Remove Orphaned or Unused Packages :

* To list packages 
```
sudo pacman -Qtdq
```

* To remove everything that is listed 
```
sudo pacman -Rns $(pacman -Qtdq)
```
  
* Want to remove only particular package 
```
pacman -Rns 'package'
```

### Remove AUR builds :


* Clean build cache and keep no older or unused versions, here yay, or you can use paru too
```
yay -Scc
```

* Clean just the build files but not package cache 
```
yay -Sc
```


## 2. System Cache & Temp Files :

* Remove /home Cache :

  ```
  
  ```
  
* Remove duplicates, empty files, empty directories and broken symlinks :

  ```
  rmlint
  ```

  

## 3. Logs & Journals :


## 4. Manually remove stuffs :

**Want to remove bin files?**
- Located in ./local/bin and /usr/share/bin

