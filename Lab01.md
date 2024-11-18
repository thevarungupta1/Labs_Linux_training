What is Unix ?
The Unix operating system is a set of programs that act as a link between the computer and the user.

The computer programs that allocate the system resources and coordinate all the details of the computer's internals is called the operating system or the kernel.

Users communicate with the kernel through a program known as the shell. The shell is a command line interpreter; it translates commands entered by the user and converts them into a language that is understood by the kernel.


# Unix Architecture
1. kernel
2. shell
3. commands and utlities
4. files and directories



# Kernel − The kernel is the heart of the operating system. It interacts with the hardware and most of the tasks like memory management, task scheduling and file management.


# Shell − The shell is the utility that processes your requests. When you type in a command at your terminal, the shell interprets the command and calls the program that you want. The shell uses standard syntax for all commands. 

# Commands and Utilities − There are various commands and utilities which you can make use of in your day to day activities. cp, mv, cat and grep, etc. are few examples of commands and utilities. 

# Files and Directories − all the data of unix is organized into files, all the files are then organized into the directries. these directories are further organized into a tree-like structure called the file system




# it is multi-programming, multi-user operating system, it means the same system can be used by different users with different access right and simulteneosly many application can run on it




# Characterstics
- it can work on different type of hardware, so it is portable
- linux is an open source, so it free to use and users can also work on enhancing features of the linux operating system
- it is multi user operating system
- linux is secure as it provide password protection and encryption of data
- linux is multi-programming as multiple application can be run at the same time





# Advantages
- linux is compatiable with large number of file formats
- linux is free of cost 
- it is enhancing day by day 
- linux system rarely crashes as they are very stable
- linux does not collect much user data, so it ensures privacy of the user
- no rebbot is needed thus incresing system speed
- no anti virus software is needed to be installed in linux



# Disadvantages
- linux does not provide some hardware drivers 
- command line interface of linux
- some graphic tools are not available for linux
- linux does not have standard version 





# Linux Distribution
- many linux distributions are available to meet just about any computing requirement you could have. most distribution are customized for  specific user group such as business user, graphic designer, gamer, software developers etc

the different linux distribution are often divided into 3 categories
- full core linux distribution - debian
- specialized linux distribution - CentOS, mint
- liveCD test distribution




# Linux vs Unix
Linux - it is an operating system it is an open source software that is completely free to use, it is used for computer hardware and software, game development, mainframes, etc. it can run various client programs

Unix - it is a portable multi-tasking, multi-user operting system developed by At&T, it is used in web servers, workstation and PCs, many busiess application are accessible on it, it is used widely for commercial use



# Setup
- Cloud
- VirtualBox or vmware
- Docker
- wsl - windows subsystem for linux


Open PowerShell as an adminstrator
```
> wsl --list --online
NAME                                   FRIENDLY NAME
Ubuntu                                 Ubuntu
Debian                                 Debian GNU/Linux
kali-linux                             Kali Linux Rolling
Ubuntu-18.04                           Ubuntu 18.04 LTS
Ubuntu-20.04                           Ubuntu 20.04 LTS
Ubuntu-22.04                           Ubuntu 22.04 LTS
Ubuntu-24.04                           Ubuntu 24.04 LTS
OracleLinux_7_9                        Oracle Linux 7.9
OracleLinux_8_7                        Oracle Linux 8.7
OracleLinux_9_1                        Oracle Linux 9.1
openSUSE-Leap-15.5                     openSUSE Leap 15.5
SUSE-Linux-Enterprise-Server-15-SP4    SUSE Linux Enterprise Server 15 SP4
SUSE-Linux-Enterprise-15-SP5           SUSE Linux Enterprise 15 SP5
openSUSE-Tumbleweed                    openSUSE Tumbleweed


> wsl --install -d Ubuntu
```
after install restart the system
> [Windows + R]
> Ubuntu


# Linux Set environment variables
the envirnment variables are dynamic values that are stored within system and used by application launched in shell or sub shell

these variables have a name and their respective values



# Common envirnment variables
- path
- user
- home
- editor
- env


# How to set environment variables in Linux
```run
export NAME=VALUE

export name=mark

echo $name

export path=$path:/home/jdk/bin/

> sudo mkdir <folder_name>
[password]

> sudo -i

> cd <folder_name>
> ls
> pwd
> env
```

# removing an envirnment variable
```
unset varibale_name
unset name
$echo name
```


# Linux export commands
```
export 
```


## Exercise 1:
```
export -f function_name

function hello
{
    echo hello
}

export -f hello
hello
```

```
function sayHello
{
    echo I am good
}

export -f sayHello
sayHello
I am good
```

## Exercise 2:
> a=100
> export a
> printenv a



## Exercise 3: Text Editor
```
vim
vi
nano
```

vim editor is the most widely used text editor for linux system, we can set the vim as default editor by using export command
```
export EDITOR=/usr/bin/vim

export | grep EDITOR

grep - global search for regular expression
```


# Linux commands
There are two type of shell command
1. build in shell commands
2. external / linux commands
default shell in linux is called bash


# directory commands
- pwd - print working directory
- ls - list of folder and files
- cd - change directory
- mkdir - make directory
- rmdir - remove directory


# Linux Home Directory
it is a directory for a particular user of the system and consists of individuals files, it is also referred as the login directory
- this is the first place occur after logging in the linux system
- it is automatically created as "/home" for each user in the directory
- it is a standard subdirectory of the root directory
- the root directory contains all other directories, sub-directories and files on the system
- it represent by "/"


/home/varun - all the individual user will have all rights under their directories
/home/paul
/home/mark

```
cd /home
ls


cd or  > cd ~   // we can get back to our home directory by executing these commands
> mkdir new_dir
> rmdir new_dir
```

# Root vs home directory
- the root directory is the topmost level of the system drive
- the home directory is a subdirectory of the root directory

```
root	"/"

/users/username	or   "~"
```

- the admin has access to make any changes in the file and settings
- no user other then root user can change the settings of the entire system

- admin can create a user
- any user having a home directory cannot create a user

- in linux file system everything come under the root directory
- the directory contains a particular user data





