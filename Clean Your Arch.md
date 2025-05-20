
## 1. Package Cleansing :

* **Clear Package Cache** -
  
  ```
  
  ```
* **Remove Orphaned and Unused Package** -

  To list packages :
  ```
  sudo pacman -Qtdq
  ```
  To remove everything that is listed :
  ```
  sudo pacman -Rns $(pacman -Qtdq)
  ```
  ```
  -R flag remove packages
  -n flag removes configuration files
  -s flag removes dependencies that aren't required by other packages
  ```
  
  Want to remove only particular package :
  ```
  pacman -Rns 'package'
  ```

* Remove AUR builds - 

  ```

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

