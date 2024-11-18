## Setup
- login into cloud labs
- open powershell as adminstrator
- install ubuntu

```bash
> wsl --install -d Ubuntu
```
- create user
- exit
- [window] + run
```
Ubuntu
```



### PWD - print working directory
```
pwd		// print current working directory

pwd -L	// show logical path of the current working directory

pwd -P	// show phtsical path of the current working directory

--help
```

### cd - change directory
```
cd <dirname>
cd ~  or cd	// bring user to the home dir
cd .		// allow user to stay in the smilar directory they are in currently
cd ~username	// allow user to stay in user home directory
cd dir	// allow user to stay in user subdirectory
cd ..		// bring user one level up
cd - 		// will change user to the old directory
```

Demo
----
#1: cd command
```
mkdir demo1
mkdir demo2

ls
day1  demo1  demo2  new_dir

cd demo1

pwd
/home/varun/demo1

cd /home/varun/demo2

```

#2: change dir using absolute or relative path
absolute path - when we have to give full path		- cd /home/varun/demo1
relative path - we provide the dir name with complete path	- cd demo2

```
~$ cd demo1
~/demo1$ cd ..
~$ pwd
/home/varun

~$ cd /home/varun/demo2
~/demo2$ cd /home/varun/demo1
~/demo1$
```

#3: change to home directory
```
cd ~
```


#4: change the previous directory
```
cd -
```

#5: change the parent directory
```
cd ..
```

#6: change to the root directory
```
cd /
```


#7: change the user home directory
```
cd ~username
```


#8: create a directory having space in the name
```
mkdir 'another folder'
```

# Absolute and relative path

when we define path starting with '/' then root of the file is assumed 
but we dont put '/' the current directory is assumed to be starting point



# path complition
```
cd /<dir_name_starting_charcter> press tab		// to auto complete 
```
the path and it is case sensative



# ls

# display whole list of directory including hidden files, hidden files start with a dot (.)
```
ls -a

~$ ls -a
 .    .bash_history   .bashrc   .motd_shown   .sudo_as_admin_successful   another           day1    demo2    new_dir
 ..   .bash_logout    .local    .profile      .viminfo                   'another folder'   demo1   folder
```

# display files in long list format
```
ls -l

~$ ls -l
total 0
drwxr-xr-x 1 varun varun 4096 May  7 13:51  another
drwxr-xr-x 1 varun varun 4096 May  7 13:52 'another folder'
drwxr-xr-x 1 varun varun 4096 May  6 15:27  day1
drwxr-xr-x 1 varun varun 4096 May  7 13:48  demo1
drwxr-xr-x 1 varun varun 4096 May  7 14:20  demo2
drwxr-xr-x 1 varun varun 4096 May  7 13:51  folder
drwxr-xr-x 1 varun varun 4096 May  6 16:30  new_dir


colume 1 - indicates ifo regarding file permission
colume 2 - indicate the number of links to the file
colume 3 & 4 - indicates owner and group info
colume 5 - indicate size of the file in bytes
colume 6 - show date and time on which file was last modified
colume 7 - show file or dir name


# display the file size in a partilar format

> ls -l --block-size=M

K - kilobytes
M - megabytes
G - gigabytes


# display sub-directories excluding all other files
> ls -d */



# mkdir

> mkdir <dir_name>
> mkdir <dir_name1> <dir_name2> <dir_name3>

 
# add directory including its sub dir
> mkdir -p, -parent


varun@DESKTOP-GUDP1GO:~$ mkdir dir1
varun@DESKTOP-GUDP1GO:~$ ls
 another  'another folder'   day1   demo1   demo2   dir1   folder   new_dir
varun@DESKTOP-GUDP1GO:~$ mkdir dir2 dir3 dir4
varun@DESKTOP-GUDP1GO:~$ ls
 another  'another folder'   day1   demo1   demo2   dir1   dir2   dir3   dir4   folder   new_dir
varun@DESKTOP-GUDP1GO:~$ mkdir -p htdocs/html
varun@DESKTOP-GUDP1GO:~$ ls
 another  'another folder'   day1   demo1   demo2   dir1   dir2   dir3   dir4   folder   htdocs   new_dir
varun@DESKTOP-GUDP1GO:~$ cd htdocs/
varun@DESKTOP-GUDP1GO:~/htdocs$ ls



# print a messag for each created directory
> mkdir -v, verbose


# set access privilage
> mkdir -m -mode=MODE

read(r)
write(w)
execute(x)


# full access
> mkdir -m=rwx <file>   or    > mkdir -m 777 <file>

# read and write
> mkdir -m=rw <file>


# read only
> mkdir -m=r <file>

# write only
> mkdir -m=w <file>

# execute only
> mkdir -m=x <file>


permission are represented in two ways
alphanumeric and octal (0-7)
command are accesed into three different catregories
user, group and other

777 - user, group and other all theree access to the directory



# dir permission
execute - actually enter that folder but not able to read its content
read - able to read folder content
write - edit folder, dleete or create a new file/folder inside


# file permission
execute - if its script index.php run it to get data from it
read - if it text file like index.html or index.php able to read it
write - ability to change its data




# rmdir
this command is used to dleete a dir but will not able to delete a directory including a sub-dir
it meas a directory has to empty to be dleeted

> rmdir <dir_name>


# this command will dleete a dir including its sub-dir all at once
> rmdir -p



> ls -R


arun@DESKTOP-GUDP1GO:~$ ls -R
.:
 another  'another folder'   day1   demo1   demo2   dir1   dir2   dir3   dir4   folder   htdocs   new_dir

./another:

'./another folder':

./day1:

./demo1:
temp

./demo1/temp:

./demo2:
temp

./demo2/temp:

./dir1:

./dir2:

./dir3:

./dir4:

./folder:

./htdocs:
html  temp2  temp3

./htdocs/html:

./htdocs/temp2:

./htdocs/temp3:

./new_dir:
varun@DESKTOP-GUDP1GO:~$ rmdir -p htdocs/html
rmdir: failed to remove directory 'htdocs': Directory not empty
varun@DESKTOP-GUDP1GO:~$ rmdir -p demo2/temp/
varun@DESKTOP-GUDP1GO:~$
```




# Linux - users
list is a multi user operating system therefore we have several command for user

# system username
> whoami


# information about the users logged on the system
> who

# display the information about the current user only
> who am i



# create user
linux server allow us to create more then one user after installation
linux is a multi user system, which means more then one user can work in the same system at the same time

adding or rmoving a user is one of the basic task of a new linux server


there are 2 ways we can create a user
1. GUI
2. command line

> useradd [options] username


the useradd command perform following tasks
1. it edit the file for newly created user /etc/passwd, etc/shadow, etc/group and etc/shadow
2. it create and open a new home directory
3. it allow us to set ownership and permission to the home directory


username - length must be between 1 to 32 characters
password - are stored in etc/shadow file in an encrypted format


UID - user identification number which is unique for very user
GID - group identification number 
user info - it allow us to define some additional info about user like full name - optional
home directory - it is an absolute location for a user

Note:
in order execute useradd we need to log-in with root or sudo access



# create a new user and password
> sudo useradd john
> sudo passwd john

# create a user with home directory
> sudo useradd -m mark		// forcefull assign a home directory to a new user


# create a user with different home dir
> sudo useradd -m -d /paulhd paul


# create a user with an expiry data
> sudo useradd -d /home/test101 -e 2024-05-10 test101
this command will create a with specified expiry date, it will create a user test101 whiuch will be auto-deleted after expiry date

10 may 2024    // yyyy-mm-dd


# get the info about the user and what they are doing
> w



# run shell as another user
> su <username>
> su john


# to switch to root user
> su root


# root user can become any existing user without knowing the user password
> su -john


# if no name is mention it assume target user is root
> su -


# list of user
> more /etc/passwd





