Linux commands on Bash:

`uname` tells you where you are 

`history` see commands previously used 

`history -c` resets previous commands used 

`clear` clears command line without deleting recent content

`ls` Your able to see all your files in your directory

`ls -a` allows you to see hidden files your directory

`curl` is used to transfer data

`--output filename` is used to store 

`cp` used to copy files

`file filename` check data of file

`rm` is used to remove files

`rm -rf` used to delete a directory

`touch` create a file 

`mkdir` used to create a directory 

`cat` look at contents of a file 

`head` used to bring back first lines 

`tail` used to bring back last lines

^ u can used a `1` to bring a specific like from the top or bottom

`nano` open a nano text editor with a file name you want. It doesnt have to be pre-existing 

`nl` output the line and their position in the test file c

`| grep` used to print lines that have a specific word you want 

`sudo apt install` used to install packages

`tree` after installed gives a visual representation of file structure

root user has the permission to do everything 

`sudo su` makes you the root user 

`exit` will disconnect 
cd
Creating a script to install nginx

1) nano provision.sh- creates a shell script and a text editor will open 

2) `#!/bin/bash` always place at the top on the file 

3) print in nano text following commands:
#update
`sudo apt update`

# upgrade
`sudo apt upgrade -y`

# install nginx
`sudo apt install nginx`

#  restart nginx
`sudo systemctl restart nginx`

# enable nginx
`sudo sytemctl enable nginx`

4) enter: `sudo chmod +x provision.sh`. The +x makes the file exectuable 

5) `./provision.sh`

6) `sudo systemctl status nginx``




Managing processes 
`ps` user processes 

PID is the process id 

TTY- terminal session that its running within 

CMD is the command used 

`ps -- simple` 

`ps -A` shows all processes

`ps aux` shows all the information along with processes

`top - Live readout of processes that are running. SHIFT + M sorts by memory. SHIFT + N shows newest. SHIFT + P sorts by cpu usage. Press Q to exit.
`kill -1` is used to kill a process

`kill -15` stronger force to kill a process

`kill -9` strongest force used to kill a process. It is used at last resort if the previous commands ^ doesnt work

Permissions:
`ls -1` used to view permissions 

chmod [permissions] [file] - chmod g+w filename adds writing permission for group. Might have to add sudo to the start. g for group and o for users. If no group is stated, all groups are given permission

chmod calculator: 
https://chmod-calculator.com/


Enviroment variable
printenv - Prints environment variables

printenv USER - prints the user environment variable

export MYNAME=Nadia - Declares an environment variable