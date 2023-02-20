# Exercice 1:

1) Go to the root directory

```
cd \
```
2) Display the content of the current (root) directory

```
ls
```

3) Check your current location

```
pwd
```

4) Try to create a directory named test

```
mkdir test
```


5) Go to the general home directory (should contain folders named after each user)

```
cd /home/
```

6) Go to your home directory

```
cd ~
```
7) Go back to the general home directory (located "just above")
```
cd ..
```
8) Go again "just above", you should be back to the root directory
```
cd ..
```
9) Go directly to your home directory (named after you). It should be a very simple command, which take no name as parameter of the path
```
cd ~
```
10) Try to create a directory named test
```
mkdir test
```
11) Go into this new directory
```
cd test
```
12) Check your current location
```
pwd
```

# Exercice 2:

1)Go to your home directory (should be named after you, you might be there by default)
```
cd
```
2)Check your current location
```
pwd
```
3) Create a folder linux_ex_1
```
mkdir linux_ex_1
```
4)Go into this folder
```
cd linux_ex_1
```
5)Create an empty text file named [first_name]_[last_name].txt (e.g. alexis_bogroff.txt)
```
touch antoine.letort.txt
```
6)Create a folder notes
```
mkdir notes
```
7)Move your text file into this folder
```
mv antoine_letort.txt notes
```
8)Rename the text file by appending the current year [first_name][last_name][current_year].txt
```
mv antoine_letort.txt antoine_letort.txt
```
9)Make a copy of this folder, name it notes_2023
```
cp -r notes notes_2023 
```
10)Delete the first folder (notes) using the verbose option

```
rm -r notes
```

# Exercice 3

1)Create a script script_1.sh in the folder linux_ex_1
```
cd ~/linux_ex_1
touch script_1.sh
```
2)In the script, write the commands that would output the following : Script running please wait ... Done.
```
nano script_1.sh
echo "Script running please wait..."
echo "Done."
```
3)Quit editing and save the script
```
Ctrl + X
```
4)Display the content of the script (using a command, not from an editor)
```
cat script_1.sh
```
5)Run the script
```
sh script_1.sh
```


# Exercice 4

# Exercise 4.1 : 

1) Create a file credentials in the folder linux_ex_1 
(a) Write any kind of (fake) personal information within the file
```
echo "Secret Password: password" > credentials
``
(b) Display the file content
```
cat credentials
```
(c) Display the current permissions
```
ls -l credentials
``
2)Change the current permissions to : read only for all users 
(a) Display the new permissions
```
chmod 444 credentials
ls -l credentials
```
(b) Modify and save the file (can't modify with new permissions)
```
echo "Some more informations..." >> credentials
```
(c) Display the file content (didn't change)
```
cat credentials
``
3)Change the permissions back to read and write for all users 
(a) Display the new permissions
```
chmod 666 credentials
ls -l credentials
```
(b) Modify and save the file (it modified this time)
```
echo "Some more informations..." >> credentials
```
(c) Display the file content
``
cat credentials

On the same file :

Add the execute permission to the owner (a) Display the new permissions
chmod u+x credentials
ls -l credentials
Remove the read permission to other users (a) Display the new permissions
chmod o-r credentials
ls -l credentials
Change the permissions to read, write and execute for all users (a) Display the new permissions
chmod 777 credentials
ls -l credentials
Exercise 4.2 : Access root files

Go to the root folder
cd /
Create a file in root user mode named .private_file (a) Write some information in the file
sudo su
echo "Some informations..." > .private_file
(b) Display the file content

cat .private_file
(c) Display all the files in the folder including hidden files

ls -a
Modify the file in normal user mode (a) Write some new information in the file
sudoedit .private_file
"More informations..."
(b) Display the file content

cat .private_file
Change permissions to read, write and execute for all users (a) Modify the file content in normal user mode
sudo chmod 777 .private_file
(b) Display the file content

cat .private_file
