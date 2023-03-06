# TD6/9: Git Filesystem & Commits
All these exercises should be done using only the command-line in your Linux shell

## Exercise 1: Configure Git
1. Check that Git is installed on your environment.
```
git --version
```
2. Configure your name and e-mail globally.
```
git config --global user.name "adrien"
git config --global user.email "...@gmail.com"
```
3. Check that Git has correctly recorded these two pieces of information.
hint : All Git commands have a -h flag to display the corresponding help.
Look there for the option of the git config command that lists all Git
configuration.
```
git config --list
```
## Exercise 2: Basic workflow with a single file

1. Create a git repository
```
git init Test
```
2. Check that git has correctly initiliazed a repository by displaying the files wihtin your current folder
```
ls 
```

3. Check the current git status
```
cd Test
git status
```
4. Create a text file named “readme.md” whose content is “# Test repository”
```
nano readme.md

# Test repository
```
5. Check the current git status
```
git status 
```

6. Stage the file
```
git add readme.md
```
7. Check the current git status
```
git status 
```

8. Commit the file
```
git commit
```
9. Check the current git status
```
git status 
```
10. Check the git logs
```
git log
```
11. Which informations are displayed ?
  
commit commit.name 
Author: user.name <user.email>
Date:   Mon Mar 6 14:17:23 2023

## Exercise 3: Basic workflow with multiple files treated separately  

1. Create two empty python files named “main.py” and “functions.py”
```
touch main.py
touch function.py
```
2. Check the current git status
```
git status 
```
3. Stage only the file “main.py”
```
git add main.py
```
4. Check the current git status
```
git status 
```
5. Commit the file with an appropriate message
```
git commit 

only main.py
```
6. Check the current git status
```
git status 
```
7. Now stage and commit the file “functions.py”
```
git add function.py
git commit
```
8. Check the current git status
```
git status 
```
9. Check the git logs
```
git log 
```

## Exercise 4: Basic workflow with multiple files treated all at once

1. Create three empty files named “requirements.txt”, “.gitignore” and “.private”
```
touch requirements.txt, .gitignore, .private
```
2. Check the current git status
```
git status
```
3. Stage all the files at once
 ```
  git add -A
  ```
4. Check the current git status
```
git status
```
5. Commit the current staged files
```
git commit 
```
6. Check the current git status
```
git status
```
7. Check the git logs where each log is displayed on a single line
```
git log 
```

## Exercise 5: Private files
Files can be private in two ways :
— being a temporary file (like an open Excel would produce or Python
Jupyter Notebook would produce). This would happen to anyone using
your project.
— being a personal file (personal notes, etc.)

1. Emulate a temporary empty file by creating a file named “temp.ipynb”
```
touch temp.ipynb
```
2. Check the current git status
```
git status
```
3. Add an instruction to .gitignore to prevent git from tracking this temp file
```
echo "temp.ipynb" >> .gitignore
```
4. Check the current git status 
```
git status
```
5. Create other temporary files named “temp.aux” and “temp.log”
```
touch temp.aux, temp.log
```
6. Check the current git status
```
git status
```
7. Change your instruction in .gitignore to prevent git from tracking any file which name starts with “temp”
```
echo "temp.*" >> .gitignore
```
8. Check the current git status
```
git status
```
9. Now let’s consider your personal notes will be added to the “.private” folder. Use the “exclude” git file to prevent git from tracking this “.private” folder

## Exercise 6: Difference between versions
1. Add a online description of your repository in the “readme.md” file
```
echo "This is my readme" >> readme.md
```
2. Stage your “readme.md” file
```
git add -A
```
3. Display the changes in your root directory since the last commit (not just the current status)
```
git diff HEAD
```
4. Commit your change
```
git commit
```
5. Display the changes since the last commit
```
git diff HEAD
```
6. Display again the changes in your root directory since the last commit

7. Change some words in the description of the “readme.md”
```
echo "Add this" >> readme.md
```
8. Display the changes since the last commit 
```
git diff HEAD
```
