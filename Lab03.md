# Linux Package Manager
it is a group of software tools
it automates the intallation process, upgrading process, configuration process amd removing process of the computer programs for an operting system of the computer in an efficient manner

every linuc distribution comes with a package manager by default

apt
apt-get
yum
deb

dpkg - debian linux family

apt and apt-get provides more user-friendly interface for package-manager

# apt is a powerfull tool used in debian based distribution such as Ubuntu, linux mint and many other
it makes the process of installing, updating and removing software packages simple

# updating package index
> sudo apt update

# upgrading packages
> sudo apt upgrade <package_name>
> sudo apt full-upgrade

# installing packages
> sudo apt install package_name
> sudo apt install package_name1 package_name2 package_name3

> sudo apt install /full/path/file.deb     // if you want install local deb file provides full path 					   otherwise cmmand will try to retrive and install from apt 
					   repositories


# removing packages
> sudo apt remove package_name
> sudo apt remove package_name1 package_name2 package_name3

Note: remove command will uninstall the given packages but it may leave some configuration behind

> sudo apt purge package_name		// remove package with all config



# listing packages
> sudo apt list

> sudo apt list | grep package_name		// filter
> sudo apt list --installed
> sudo apt list --upgradeable

# searching package
> sudo apt search package_name




# Find command in linux
the find command helps us to find a particular file within a directory
it is used to find the list of files for various conduition like permission, user ownership, modification, date/time, size and more


synatx
-----
find <location> <comparision-criteria> <search-term>


(.) : for current directory name
(/) : for the root directory


-name pattern
-type type
- print
-exec program [argument..]

# find files by name
> find . -name "*.txt"


varun@DESKTOP-GUDP1GO:~/day3$ ls
first.txt  index.html  index.ts  index.txt  second.txt  temp
varun@DESKTOP-GUDP1GO:~/day3$ ls -G
first.txt  index.html  index.ts  index.txt  second.txt  temp
varun@DESKTOP-GUDP1GO:~/day3$ find . -name "*.txt"
./first.txt
./index.txt
./second.txt
varun@DESKTOP-GUDP1GO:~/day3$ find . -name "*.ts"
./index.ts
varun@DESKTOP-GUDP1GO:~/day3$ find . -name "index.*"
./index.html
./index.ts
./index.txt
varun@DESKTOP-GUDP1GO:~/day3$



# find file by type
-type parameter is used to specify the file type


f: regular file
d: directory
l: symbolic link
c: character devices
b: block devices


> find . -type d -name "*.txt"    // *


# find file by name
> find . -name "index.html"
> find . -name "*.html"


# find newer file
> find . -newer msg.txt		// display all the files which are newer then msg.txt



varun@DESKTOP-GUDP1GO:~$ find ./day1 -name "*.txt"

# find and delete a file
> find ./day1 first.txt -delete

Note: once file deleted we cannot undo


# find a directory
> find . type -depth -name newDir


# find file by modification time
-mtime option followed by the number of days
it can take day as positive or negative value
-1 is used for last dat
+1 is used to more then one day agoi

> find ./day1 -mtime -1



# find by file by permission
-prem option is used to find by permission


# compress and extract file using tar

.tar		// archive files are usually not compressed
.tar.gz		// archive file compressed with gzip tool
.tar.bz2	// atrchive file compress with bzip2 tool


syntax
> tar options [archive_name.tar] file_to_archive


-a	// concatenate
-c	// create
-d	// difference
-r	// append
-t	// list
-u	// update
-x	// extract


# file compression is a fundamental task in managing and transfering data efficiently on a linux system
the tar command short for tape archive is a powerfull tool that allow user to create compress amd archive files


> tar [options] [archive-file] [file or directory to be archive]

tar		// command itself
[options]	// optional flag or setting that modify the behaviour of the tar command
[archive-file]   // name of the archive file you are creating
[file or dir]	// file or dir you want ti include in the archive


-c		// create
-v		// verbose
-f		// file

> tar cvf file.tar   *.txt

-x		// extract
-v		// verbose
-f		// file

> tar xvf file.tar


# Linux I/O redirection
redirection can be defined as changing the way from where command read input to where command send output

standard input (stdin)
standard output (stdout)
standart error (stderr)


# redirection into a file

'>'  overwrite existing file

>  - standard output
<  - standard input
2> - stabdard error

cat > <file_name>



# Append
'>>' do not overwrite the existing file content

>>	-	 standard output
<<	- 	 standart input
2>>	- 	 standard error


car >> <file_name>




# redirection into a program
pipe redirects a stream from one program to anmother

ls *.txt | cat > txtfile



varun@DESKTOP-GUDP1GO:~/demo11$ ls *.txt
first.txt  sample.txt
varun@DESKTOP-GUDP1GO:~/demo11$ touch index.html
varun@DESKTOP-GUDP1GO:~/demo11$ ls
first.txt  index.html  sample.txt
varun@DESKTOP-GUDP1GO:~/demo11$ ls *.txt
first.txt  sample.txt
varun@DESKTOP-GUDP1GO:~/demo11$ cat > textfile
^C
varun@DESKTOP-GUDP1GO:~/demo11$ ls
first.txt  index.html  sample.txt  textfile
varun@DESKTOP-GUDP1GO:~/demo11$ ls *.txt | cat > textfile2
varun@DESKTOP-GUDP1GO:~/demo11$ cat textfile2
first.txt
sample.txt
varun@DESKTOP-GUDP1GO:~/demo11$




# Vi editor
the vi editor is like a visual editor
in is installed in every unix system

vim is an improved version of the vi



vi editor has two modes
1. command mode - actions are take on file
2. insert mode - entered text will be inserted into the file

i - insert
esc - to exit from the insert mode




:wq - save and quit  -  recommanded
:w - save
:q - quit
:q! - quit discarding changes made
:w! - save (and write to non writable file)
ZZ - save and quit
:w fname - save as fname



# Linux file ownership
- user - it is one who create the file by default become the owner
- group - can contain multiple users. all the users belonging to a group have same permission for a file
- other - any one who has access to the file other user and group come in this category



/etc/psswd
/etc/group


> cut -d: -f1 /etc/passwd | column


# create new group 
# sudo groupadd <groupName>
> sudo groupadd php

# change the group
> chgrp <newGroup> <fileName>
> chgrp develop file


# change owner
> chown <newOwner> <file_name>
> chown paul second.txt


# Linux networking command
mainting a system network is a task fo system admin
this task include various netwok configuration

ifconfig - display and manipulate route and network interface
ip - it is relacement of ifconig
ping - to check communication between two nodes
traceroute - 
tarcepath - 
netstat - display connection info	// ss



> traceroute <destination>
 - it determines the location of the network latency
 - it follow the path
 - gives the name all devices on the path


> tracepath <destination> - // root previllage


> ping <destination>


> host -t <resource_name>  // DNC lookup


> curl  and   wget

these command are used to download fils from CLI from the internet

> curl -O <file_link>
> wget <file_name>




# Install Java with wget
> wget https://download.oracle.com/java/17/latest/jdk-17_linux-x64_bin.deb
> dpkg -i jdk-17_linux-x64_bin.deb
> export JAVA_HOME=/usr/lib/jvm/jdk-17/
> export PATH=$PATH:$JAVA_HOME/bin
> sudo nano /etc/environment

JAVA_HOME="/usr/lib/jvm/jdk-17"


[ctrl] + x
[Y]
[enter]

> echo $JAVA_HOME

> java --version



# iptable

it is a command line interface used to setup and maintain table for the firewall for IPv4
the firewall matches packets with rules define in these tables and then takes the specified action 



table - is the name of the set of chains
chain - is a collection of rules
rule - is condition used to match packet
target - action taken
policy - default action


filter - default used table for packet filtering 
nat - related to network address translation
mangle - for specialised patcket alteration
raw - confiugures exemption from connection tracking
security - used by mandatory access control




chains
- input
- forward
- output
- prerouting
- postrouting



append
delete
check


syntax
-------
iptables --table TABLE -A/-C/-D CHAIN rule --jump Target

iptables [-t table] --append [chain] [parameter]

iptables -t filter --append INPUT -j DROP

# Append (-A)
> sudo iptables -t filter --list
> sudo iptables -t filter --append INPUT -j DROP

# Delete (-D)
> sudp iptables -t filter --delete INPUT 2		// rule 2



# Check (-C)
iptables -t filter --check INPUT -s 192.168.1.1 -j drop



> sudo iptables --flush		// remove all filters rules and user created chains

> sudo iptables-save		// save the iptable configuration

> sudo tptables-restore		// restoring iptables config 




# cronjobs


> crontab - it is list of commands that you want to run on regular schedule


MIN
HOUR
DOM
MON
DOW
CMD



# scheduling a job for specific time
this basic usage of cron is to execute a job in a specified time 


30 08 10 06 * /home/varun/full-backup

30 - 30 mints
08 - 8 AM
10 - 10 Day
06 - 6th Month (June)
* - every day of the week


> crontab -l  to get list of all crontab entries






# to schedule a bachrond cron job for every 10 mints
*/10 * * * * /home/varun/full-backup



# Systemd

systemd uses to manages and acton upon units, units can be of many type

services




> sudo systemctl start nginx.service

> sudo systemctl stop nginx.service

> sudo systemctl restart nginx.service

> sudo systemctl reload nginx.service


bt default most systemd unit files are not started automatically at boot
to configure this functionality you need to enable to unit


> sudo systemctl enable nginx.service

> sudo systemctl disable nginx.service



> systemctl list-units


