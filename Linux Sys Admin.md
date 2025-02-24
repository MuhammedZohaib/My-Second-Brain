# Linux Sys Admin

```other
# who is logged and info about sessions
w
# check info about the processes
top
# gives cpu usage by processes
top -c
# open ports run with sudo gives more info
netstat -tupln
# list all files including hidden
ls -a
ls -al # list view
ls -alh # more readable
```

---

### Important Points

- Default Text Editor in gnome is gedit
- Exit vim :wq!, :q!
- /src/apt/sourcelist
- /etc/logconf.def
- /etc/passwd contains info about user accounts
- /etc/shadow contains information about account passwords and login access
- Exclamation mark in front of hashed password in /etc/shadow will lock the account
- /etc/resolve.conf contains the dns info
- /etc/group contains info about the groups
- /etc contains all the application configuration files
- /bin and /sbin contains binaries which are not executable even if they’re installed somewhere else they’ll have a link in /bin directory
- /dev contains the information about all the mounted devices on the system
- /tmp is the temporary files directory and it is emptied every time we shutdown our machine
- /lib and /lib64 contain all the libraries

```other
# output redirection to file 
> filename # (overwrite)
>> filenane # (append)
# ask kernal for running processes
ps aux
# run program2 if program 1 successful
program1 && program2
# cut command
cut -d: -f2
# sort
sort -bf # ignore leading ws and case insensitive
# unique
uniq
# wordcount
wc filename
# change file mode
chmod
# change file owner
chown
# add, del user
useradd -m -d /home/username -s bin/bash
userdel
passwd username
# lock a user
usermod -l username
# unlock a user
usermod -u username
# kill
sudo kill "signal" "pid"
sudo pkill -u "user"
# file system hierarchy
man hier
```

Every process in the linux has a priority which is measured by a number which is known as niceness it’s value ranges from -20 to 19 and -20 is the highest priority

```other
# start a process with priority
nice -5 "process name or path"
# if process is already started
renice -10 "process id"
# see mounted file systems
df -h
```

### Linux File System

1. #### `/proc`
It is the directory in the Linux file system where the kernel hosts the information about all the processes

2. #### `/bin`
This directory contains binaries which are part of the base operating system. These binaries are shipped with the operating system.

3. #### `/boot`
This directory contains the bootloader, the kernel and grub

4. #### `/dev`
This directory contains all the mounted devices on the system. Such as hard drives

sda is the first mounted hard drive

sdb will be the second mounted hard drive

sdba1 and sdba2 are the partitions on the sdba hard drive

5. #### `/etc`
This directory contains all the configuration files related to all the programs and services

6. #### `/home`
This directory is the home for all the non-root users

7. #### `/lib & /lib64`
These directories contian libraries which are as the same as dll in windows. These libraries can be used by different programs and processes by the system.

8. #### `/media || /mnt`
This directory contains all the auto-mounted devices because by default only root user can mount devices

9. #### `/opt`
This directory contains all the optional softwares

10. #### `/var/log`

This directory contains all the system logs

::Scheduling Tasks::

```other
# list crontab
crontab -l
# edit crontab
crontab -e

# min hour dayOfMonth monthOfYear weakDay
15 18 * * 1-7
```

**::TMUX::**

- `sudo apt install tmux`
- #### `ctrl b + c`
This will create a new tmux window terminal

- #### `ctrl b + n & ctrl b + p`
Go to next and previous window terminals of the tmux

- #### `ctrl b + w`
This will list all the window terminals of the  tmux

- #### `ctrl b + %`
This will split the window terminals of the tmux vertiacally

- #### `ctrl b + ,`
This command is used to rename the current active terminal

- #### `tmux list-sessions`
This command will list any active sessions in the tmux such as detached sessions

- #### `tmux new -s “session name”`
This Command Creates a new tmux session which can be created and restored

- #### `ctrl b + d`
This command in tmux will detach the running session means it’ll be running still jn the session

- #### `tmux attach -t “session name”`

This command will bring back the session which was detached or any session we created in the tmux

### Compression and Archibving

`tar -xcvf dirName`

`tar -zcvf dirName`

### Bash Scripting

```other
# variables
var="somedata"
# calling variable
$var
# executing commands in scripts
"‘anything in the back tick is executed‘"
# executing scripts
. script.sh # in same shell
source script.sh # in same shell
./script.sh # only run the script
bash script.sh

# arguments
$# number arguments passed in script
$0 give name of the script file
$1 first argument
```

### Systemd

```other
//Managing Services with Systemd
systemctl //for service management
journalctl // for logs management

systemctl status "serviceName"
systemctl start "serviceName"
systemctl enable "serviceName"
systemctl stop "serviceName"
systemctl disable "serviceName"
systemctl reload "serviceName"
systemctl restart "serviceName"

journalctl -xn
journalctl -u "serviceName"
journalctl -b
journalctl -f
journalctl --since "10 min ago"
```

?descriptionFromFileType=function+toLocaleUpperCase()+{+[native+code]+}+File&mimeType=application/octet-stream&fileName=Linux+Sys+Admin.md&fileType=undefined&fileExtension=md