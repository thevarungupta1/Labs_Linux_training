# grep command

gerp filter searches a file for a particular pattern of characters and displays all lines that contain that pattern
the pattern that is searched in the file is referred to as the regular expression

grep - global search for regular expression


> grep [options] pattern [files]

[ options ]	there are command line flags that modify the behaviour of grep
[ pattern ]	this is the regular expression you want to search for
[ file ] 	this the name of the file you want to search within


-c	count of line
-h	match line
-i	case insenstive
-l	list
-v	line that do not match



> grep -i "LINUX" index.txt
> grep -c "linux" index.txt
> grep -l "linux" *




varun@DESKTOP-GUDP1GO:~/day4$ cat > index.txt
this is text file having some info on linux
linux is opearting system
Linux ^C
varun@DESKTOP-GUDP1GO:~/day4$ ls
index.txt
varun@DESKTOP-GUDP1GO:~/day4$ grep -i "LINUX" index.txt
this is text file having some info on linux
linux is opearting system
varun@DESKTOP-GUDP1GO:~/day4$ grep -c "LINUX" index.txt
0
varun@DESKTOP-GUDP1GO:~/day4$ grep -c "linux" index.txt
2
varun@DESKTOP-GUDP1GO:~/day4$ grep -l "linux" *
index.txt
varun@DESKTOP-GUDP1GO:~/day4$ touch hello.txt
varun@DESKTOP-GUDP1GO:~/day4$ ls
hello.txt  index.txt
varun@DESKTOP-GUDP1GO:~/day4$ cat > first.txt
linux is an os
^C
varun@DESKTOP-GUDP1GO:~/day4$ ls
first.txt  hello.txt  index.txt
varun@DESKTOP-GUDP1GO:~/day4$ grep -l "linux" *
first.txt
index.txt
varun@DESKTOP-GUDP1GO:~/day4$




# process control in linux


bg - put suspended process into backgroud
fg - bring process into forground
jobs - list process



# foreground process
every process when started runs in foreground by default, received input from keyword and send the output to the screen
> pwd


# background process
it runs in the backgrounbd without keyboard input and wait till keybord input is required

adding & along with the command starts it as a background process
> pwd &


# tracking ongoing process
> ps - can be used to list all running process

varun@DESKTOP-GUDP1GO:~/day4$ ps
  PID TTY          TIME CMD
   17 tty1     00:00:00 bash
   53 tty1     00:00:00 ps
[1]+  Done                    pwd


# more information
varun@DESKTOP-GUDP1GO:~/day4$ ps -f
UID        PID  PPID  C STIME TTY          TIME CMD
varun       17    16  0 13:46 tty1     00:00:00 -bash
varun       54    17  0 13:58 tty1     00:00:00 ps -f
varun@DESKTOP-GUDP1GO:~/day4$



# Stopping a process

> ps -f
> kill 17



# create a linux vm
# connect using SSH

# update packages
> sudo yum update -y

# install apache web server
> sudo yum install httpd -y

# start apache web server
> sudo systemctl start httpd

# configure apache to run on system boot
> sudo systemctl enable httpd

# check status
> sudo systemctl status httpd

# create a simple html web page

before we can test apache web server we need to change the permission of the 
/var/www/html   directory


> sudo chmod 777 /var/www/html


> sudo vi /var/www/html/index.html


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>Apache web server is running</h1>
</body>
</html>



:wq



test on browser

http://<public_ip>:80




> docker --version
> sudo yum update -y
> sudo yum install -y docker
> sudo service docker start
> sudo usermod -a -G docker ec2-user
> docker --version
> sudo -i
> docker ps
> docker run -d --name myapp -p 90:80 nginx

http://<public_id>:90






# Linux NFS
Network File Sharing is a protocol that allows you to share directories and files with other linux clients over network

shared directories are typically created on a file server, ruuning the NFS server components

User add files to them, which are then shared with other user who have the acces to the folder



# exercise: setting up an NFS server with an NFS share

> sudo apt-get update
> sudo apt install nfs-kernel-server


> yum -y install nfs-utils




# create root NFS directory
> sudo mkdir /mnt/myshareddir


# set permission 
> sudo chown nobody:nogroup /mnt/myshareddir      # no-one is owner

> sudo chmod 777 /mnt/myshareddir 		  # everyone can modify files



# define access for NFS client in export files

/etc/exports

edit file


# to enable access to a single client	

/mnt/myshareddir 
{clientIP} {rw, sync, no_subtre_check}


# to enable access to several client  	
/mnt/myshareddir 
{clientIP-1} {rw, sync, no_subtre_check}
{clientIP-2} {rw, sync, no_subtre_check}
{clientIP-3} {rw, sync, no_subtre_check}


# to enable access to an entire subnet
/mnt/myshareddir 
{subnetIP}/{subnetMask} {rw, sync, no_subtre_check}



# LVM - logical Volume Management 
it is a method used by linux to manage storage volumes accross different pyhical hasr disk


PV - Physical Volume
PP - Pysical Partion
VG - Volume Group
LV - Logical Volume



lsblk - it is great tool for getting disk information



# create a disk label
> parted /dev/sdb mklabel GBT

# create the partition on disk

> parted -a opt dev/sdb mkpart primary ext4 0% 100%



yum install system-storage-manager

/sdba1
/sdb1
/sdc1


ssm create -p NEW_POOL /sdba1 /sdb1 /sdc1
