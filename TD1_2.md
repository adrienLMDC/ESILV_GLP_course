# TD2/9: Fundamental Linux functionalities  

## Exercise 1: Access general computer informations  

1. Put system up to date
```
sudo apt update  
```

2. Display
  — Linux version
```
lsb_release -a
```  

  — Current processes and memory usage associated
 ```
 free
 ```
  
  — Display it in a more pleasant way ("more readable for humans")  
```
vmstat
```

  — Number of processors  
```
nproc
```

  — L1, L2 and L3 cache size  
```
lscpu
```
  
  — Disk space  
```
df -h
```

  — Monted devices  
```
mount
```

  — Connected usb devices  
```
lsusb
```

  — Hostname  
```
hostname
```


## Exercise 2: Shell - Variables and scripts scope
1. Create a variable x and assign it the short text piri pimpin
2. Display the value of this variable
3. Add to this value the following text piri pimpon
It should contain the following : piri pimpim piri pimpon
4. Create a folder named my_programs, then enter into that folder
5. Create a script named pilou that displays pilou pilou
6. Run this script
7. Make this script executable
8. Run the script by writting its name only
9. Programs called from the terminal are usually found thanks to a variable
named PATH
Display the content of the variable PATH
10. Add the path of your current location to the global variable PATH
11. When you are sure of the result, export it
12. Go to your home directory
13. Run your script by writting its name only
14. Change the value of the PATH in the .profile file in order to make it
permanent
15. Create a new shell and run your script using its name only
