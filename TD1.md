# TD1/9: Use basic Linux commands 

## Exercise 1: Move around 

1. Go to the root directory     
```
$ cd /
```
  
2. Display the content of the current (root) directory  
  
```
$ ls
```  

3. Check your current location

```
$ pwd
```  

4. Try to create a directory named test  

```
$ mkdir test
```
Permission got denied. The directory haven't been created

5. Go to the general home directory (should contain folders named after each user)  

We can not do this one as we are not using VE

6. Go to your home directory
```
$ cd C:/Users
```

7. Go back to the general home directory (located "just above")
```
$ cd ..
```

8. Go again "just above", you should be back to the root directory
```
$ cd ..
```

9. Go directly to your home directory (named after you). It should be a
very simple command, which take no name as parameter of the path

```
$ cd
```

10. Try to create a directory named test
```
$ mkdir test
```

11. Go into this new directory
```
$ cd test
```

12. Check your current location
```
$ pwd
```  


## Exercise 2: Create, Rename, copy, delete

1. Go to your home directory (should be named after you, you might be
there by default)
```
$ cd 
```

2. Check your current location
```
$ pwd
```

3. Create a folder linux_ex_1
```
$ mkdir linux_ex_1
```

4. Go into this folder
```
$ cd linux_ex_1
```

5. Create an empty text file named [first_name]_[last_name].txt (e.g. alexis_bogroff.txt)
```
$ touch adrien.lemasne.txt
```

6. Create a folder notes
```
$ mkdir notes
```

7. Move your text file into this folder
```
mv adrien_lemasne.txt notes
```

8. Rename the text file by appending the current year [first_name]_[last_name]_[current_year].txt
```
mv adrien_lemasne.txt adrien_lemasne_2023.txt
```

9. Make a copy of this folder, name it notes_2023
```
cp -r notes notes_2023 
```

10. Delete the first folder (notes) using the verbose option

It didn't work with -v so I used -r
```
rm -r notes
```

## Exercise 3 : Create and run a script

1. Create a script script_1.sh in the folder linux_ex_1
```
nano script_1.sh
```

2. In the script, write the commands that would output the following :
Script running please wait ...
Done.

```
#!/bin/bash

echo "Script running please wait ..."
echo "Done."
```

3. Quit editing and save the script

CTRL + X
CTRL + Y


4. Display the content of the script (using a command, not from an editor)
```
echo -e "Script running please wait ...\nDone."
```

5. Run the script
```
$ chmod +x script_1.sh
$ ./script_1.sh
```

## Exercise 4: Accessing or modifying a file : permissions and root privilege

### Exercise 4:.1 Change the rights for accessing or modifying a file  

1. Create a file credentials in the folder linux_ex_1
  (a) Write any kind of (fake) personal information within the file
```
$ touch credentials.txt 
$ echo "Je suis né en Novembre" > credentials.txt
```

  (b) Display the file content
```
$ cat credentials.txt
```
  
  (c) Display the current permissions
```
$ ls -lah credentials.txt
```

2. Change the current permissions to : read only for all users

Notes for myself
The output of ls -la filename shows the permission. The first character indicates if it is a file (-), a directory (d) or a link (l)
Then it is followed by r or w or x or a combinaison of those, it indicates the rights of the owner

To change directory permissions for everyone, use “u” for users, “g” for group, “o” for others, and “ugo” or “a” (for all).

There are three kinds of file permissions in Linux:
  Read (r): Allows a user or group to view a file.
  Write (w): Permits the user to write or modify a file or directory.
  Execute (x): A user or grup with execute permissions can execute a file or view a directory.
  
For example : 
  chmod ugo+rwx foldername to give read, write, and execute to everyone.
  chmod a=r foldername to give only read permission for everyone.
  ...
  
  (a) Display the new permissions
```
$ chmod a=r credentials.txt
$ ls -lah credentials.txt
```

  (b) Modify and save the file
```
$ echo "Modified file" > credentials.txt
```
*Permission denied
  
  (c) Display the file content
```
$ vim credentials.txt
```

3. Change the permissions back to read and write for all users  
  (a) Display the new permissions
```
$ chmod ugo+rw credentials.txt
$ ls -la credentials.txt
```
  
  (b) Modify and save the file
```
$ vi credentials.txt 

press i to access the insertion mode. 
Write what you want
Press Esc to access the normal mode
Write :wq + Enter to save and exit
```

  (c) Display the file content
```
$ cat credentials.txt
```
