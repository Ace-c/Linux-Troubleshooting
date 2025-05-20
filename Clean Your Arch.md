
## 1. Package Cleansing :

### Clear Package Cache :
  
```
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

Clean yay -
```
yay -Scc
```
For Paru -
```
paru -Scc
```

To remove Manually -
```
rm -rf ./*/ 
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

