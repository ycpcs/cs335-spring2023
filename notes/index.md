---
layout: default
course_number: CS335
title: Notes and Snippets
---

This page contains notes and code snippets regularly used in class.

- [TCP](#tcp)
- [ARP](#arp)
- [Networking](#networking)
- [Buffer Overflow](#buffer-overflow)
- [Shellshock](#shellshock)
- [Reverse Shell](#reverse-shell)
- [Networking](#networking-1)
- [User Management](#user-management)
- [File Commands and Directory Navigation](#file-commands-and-directory-navigation)
- [Process commands](#process-commands)
- [Permissions](#permissions)
- [Install Editors](#install-editors)
- [Clone a website](#clone-a-website)
- [Upgrade VM](#upgrade-vm)

#### TCP
- Client: <a href=".\tcp\client.txt" target="_blank">client.py</a>
- Server: <a href=".\tcp\server.txt" target="_blank">server.py</a>
- Multi Server: <a href=".\tcp\server2.txt" target="_blank">server2.py</a>
- Synflood: <a href=".\tcp\synflood.txt" target="_blank">synflood.py</a>
- Synfloof: <a href=".\tcp\synflood.c" target="_blank">synflood.c</a>
- Reset: <a href=".\tcp\reset.txt" target="_blank">reset.py</a>
- Auto Reset: <a href=".\tcp\auto_reset.txt" target="_blank">auto_reset.py</a>
  
<a href="#">To top</a>

#### ARP
- Docker Setup: <a href=".\arp\docker-compose.yml" target="_blank">docker-compose.yml</a>
- arp poisoning: <a href=".\arp\arp.txt" target="_blank">arp.py</a>
- arp mitm: <a href=".\arp\mitm.txt" target="_blank">mitm.py</a>
  
<a href="#">To top</a>

#### Networking 
- udp_client: <a href=".\network\udp_client.txt" target="_blank">udp_client.py</a>
- udp_server: <a href=".\network\udp_server.txt" target="_blank">udp_server.py</a>
- Docker Setup: <a href=".\network\docker-compose.yml" target="_blank">docker-compose.yml</a>
- Scapy: 
  - sniff: <a href=".\network\sniff.txt" target="_blank">sniff.py</a>
  - icmp_spoof: <a href=".\network\icmp_spoof.txt" target="_blank">icmp_spoof.py</a>
  - udp_spoof: <a href=".\network\udp_spoof.txt" target="_blank">udp_spoof.py</a>
  - sniff_spoof: <a href=".\network\sniff_spoof.txt" target="_blank">sniff_spoof.py</a>
  
<a href="#">To top</a>

#### Buffer Overflow 
- Buffer Overflow Example : <a href=".\buffer\buffer.c" target="_blank">buffer.c</a>
- Memory Layout: : <a href=".\buffer\layout.c" target="_blank">layout.c</a>
- Launching shell: <a href=".\buffer\launch_shell.c" target="_blank">launch_shell.c</a>
- ASCII vs binary: <a href=".\buffer\print_zero.c" target="_blank">print_zero.c</a>
- Print *esp*: <a href=".\buffer\sp.c" target="_blank">sp.c</a>
- ASLR: <a href=".\buffer\aslr.c" target="_blank">aslr.c</a>

<a href="#">To top</a>

#### Shellshock 
- Set-UID Example : <a href=".\shellshock\vul.c" target="_blank">vul.c</a>

<a href="#">To top</a>

#### Reverse Shell
- File Descriptors Intro: <a href=".\reverse-shell\fd.c" target="_blank">fd.c</a> 
- Redirection: <a href=".\reverse-shell\redirect.c" target="_blank">redirect.c</a>
- Duplicate a file descriptor: <a href=".\reverse-shell\dup.c" target="_blank">dup.c</a> and <a href=".\reverse-shell\dup2.c" target="_blank">dup2.c</a>
- Redirecting IO to TCP Connections: <a href=".\reverse-shell\tcp_in.c" target="_blank">tcp_in.c</a> and <a href=".\reverse-shell\tcp_out.c" target="_blank">tcp_out.c</a>
  
<a href="#">To top</a>

#### Networking

- ```ifconfig -a``` displays all network interfaces and IP address.
- ```hostname -I``` displays the IP addresses of the host (all local IP addresses).
- ```host domain``` displays IP address for _domain_.
- ```ping host``` sends ICMP echo request to _host_.
- ```whois domain``` displays whois records for _domain_.
- ```dig domain``` displays DNS information for _domain_.
- ```dig -x IP``` does reverse lookup of _IP_ address.  

<a href="#">To top</a>

#### User Management 

- Local user information is stored in the _/etc/passwd_ file. Get the list of all users using ```cat /etc/passwd```. The fields are delimited by colons and contain the following:
  - User name
  - Encrypted password (x means that the password is stored in the ```/etc/shadow``` file)
  - User ID number (UID)
  - User's group ID number (GID)
  - Full name of the user (GECOS)
  - User home directory
  - Login shell (defaults to /bin/bash)
    - If you need a user account with a password for authentication with a system, but do not require an interactive shell
    - _/sbin/nologin_ and _/bin/false_ if the user tries to log in to the system, the nologin shell closes the connection of the user
- ```whoami``` prints out your current user name)
- ```id``` display the user and group ids of your current user
- ```groupadd attackers``` created a group named _attackers_
- ```useradd -c "John Doe" -m john``` creates an account names _john_ with a comment of _John Doe_
- ```passwd john``` will set the password for the user _john_
- ```usermod -a -G attackers geek``` adds _john_ to the _attackers_ group
- ```usermod --shell /bin/bash john``` update the default shell to bash of user _john_
- ```sudo gpasswd -d john attackers``` removes _john_ from the _attackers_ group
- ```userdel john``` deletes the _john_ account
  - ```rm -r /home/john``` will delete the home directory of the _john_ account
  - ```su``` temporarily become the superuser
  - ```last``` show last system logins
  - ```who``` displays who is currently logged into the system
  - ```w``` shows which users are logged in and their activity
  - _chmod_ command is used to change the permissions of a file or directory.
    - ```man chmod``` finds the manual for the _chmod_ command

<a href="#">To top</a>

#### File Commands and Directory Navigation

- ```cd``` go to _$HOME_ directory.
- ```cd ...``` go one level up the directory tree.
- ```cd /etc``` to change to the _/etc_ directory.  
- ```ls``` list all files.
  - Use ```-R``` to list all-subdirectories as well
  - ```-a``` will list hidden files as well
  - Use the ```-al``` argument to view details
- ```pwd``` lists the present working directory.
- ```mkdir directory``` created a _directory_.
- ```rm -r directory``` removes the _directory_ and its contents recursively. Use the ```f``` argument to forcefully remove, re: ```rm -rf directory```.
- ```touch file``` will create an empty _file_.
- ```rm file``` removes a _flle_.
- ```cp file file2``` will copy _file_ to _file2_.
- ```mv file file2``` renames or moves _file_ to _file2_.
- ```cat filename``` will display the contests of _filename_.
- ```cat > filename```  creates a new file with _filename_.

<a href="#">To top</a>

#### Process commands

- ```bg``` sends a process to the background.
- ```fg```	runs a stopped process in the foreground.
- ```top``` shows	details on all active processes.
- ```ps```	gives the status of processes running for a user.
- ```pidof```	gives the process id (PID) of a process.
- ```ps PID```	gets the status of a particular process.
- ```kill PID```	kills a process with _PID_ .
- ```nice```	starts a process with a given priority.

<a href="#">To top</a>

#### Permissions

![](images/file_permissions.png "File Permissions")

- Legend
  - User or Owner ```U```
  - Group ```G```
  - World (Other Users) ```W```
- Permission Classes
  - Read ```r```
  - Write ```w```
  - Execute ```x```
- File Type
  - ```-``` regular file
  - ```d``` directory
- Examples
  - file _desktop.ini_: ```-rwxrwxrwx 1 seed seed 282 Dec 27 10:10 desktop.ini```
  - directory _host_: ```drwxrwxrwx 1 seed seed 4096 Jan 20 13:22 host```

  Number | Permission Type | Symbol |
  -------|-----------------|--------|
  0	     | No Permission   | ---     |
  1	     | Execute         | --x
  2      | Write	         | -w-
  3	     | Execute + Write | -wx
  4 	   | Read	           | r--
  5	     | Read + Execute	 | r-x
  6	     | Read +Write  	 | rw-
  7	     | Read + Write +Execute	| rwx
- Permission Examples  
  - ```chmod 777 filename```: _rwx rwx rwx_
  - ```chmod 775 filename```: _rwx rwx r-x_
  - ```chmod 755 filename```: _rwx r-x r-x_
  - ```chmod 664 filename```: _rw- rw- r--_
  - ```chmod 644 filename```: _rw- r-- r--_

<a href="#">To top</a>

#### Install Editors
- Sublime: ```sudo snap install sublime-text --classic```  
- Visual Studio Code: ```sudo snap install --classic code```

<a href="#">To top</a>

#### Clone a website 
```wget --mirror --convert-links --adjust-extension --page-requisites --no-parent https://site-to-copy.com```
  - ```--mirror``` make the download recursive.
  - ```--no-parent``` do not crawl the parent/top directory.
  - ```--convert-links``` makes all the links work properly with the offline copy.
  - ```--page-requisites``` download JS/CSS files.
  - ```--adjust-extension``` add the appropriate extensions (e.g. html, css, js) to files.

<a href="#">To top</a>

#### Upgrade VM 
- ```sudo apt update``` - downloads package information from all configured sources.
- ```sudo apt upgrade``` - will upgrade all installed packages to their latest versions.
- ```sudo apt-get autoremove``` - deletes orphaned packages, or dependencies that remain installed after you have installed an application and then deleted it.
- ```sudo apt-get clean``` - removes all packages from the cache.

<a href="#">To top</a>