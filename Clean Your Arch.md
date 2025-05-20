
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
* Clean old versions while keeping the most recent ones
```
sudo pacman -Sc
```
* Remove all packages from the cache
```
sudo pacman -Scc
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
sudo pacman -Rns 'package'
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


## 2. Cleaning User Cache :

* Check size of the home cache directory 

```
du -sh ~/.cache/
```

* Delete all the cache from .cache
```
rm -rf ~/.cache/*
```

> Is it safe to delete .cache?
> Yes, It's generally safe but not when you storing something unusual, also close all apps before cleaning

* Use Bleachbit, It'll clean caches and junk files for specific apps as you want
```
sudo pacman -S bleachbit
```


## 3. Temp Files :

* Remove duplicates, empty files, empty directories and broken symlinks :

```
rmlint
```


## 4. System Logs & Journals :


## 5. Manually remove stuffs :

**Remove bin files?**
- Located in ./local/bin and /usr/share/bin

