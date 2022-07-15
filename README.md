# Linux Basics

- `echo`: write something to a file 
- `clear`: allows a user to clear the screen
- `touch`: allows a user to create a file
- `rm`: delete a file
- `rm -r`:  to delete folders and sub-folders (it may contain files and directory). `-r` is for (recursively)
- `mkdir`: allows user to create a directory (folder)
- `ls`: list files in a directory
- `cd` : to change directory
- `code .`: Visual Sudio Code, open current working directory

- `cp` : Let's us copy/back a file
- `cp -r`: backup or copy files, folders, and subfolders. Where `-r` is for `recursively`
- `ls -al`: list files and their permissions
- `chmod` : is a command used to `change the access permissions` of a file system object.
- `grep` : used to search for a string of characters in a specific file
- `sudo` : Super User Do - Administrative User


## To Push Modified file(s) to GitHub
```git status```

```git add README.md```

```git commit -m "your message here"```

```git push```


## Session-2 July 08, 2022
What is a `Virtual Machine (VM)`: is the virtualization/emulation of a computer system.

`EC2 Instance`:  It a virtual machine from AWS (Amazon Web Service). Linux OS (Operating System) - Ubuntu 18.04 (Distribution of Linux OS)

EC2 - Elastic Compute Cloud
OS - Operating System
VM - Virtual Machine

### Services on AWS
- Compute: EC2 Instances

### Key Permissions
- User  -> rwx
- Group -> rwx
- Other (ALL) -rwx

    - r : `READ`
    - w : `WRITE`
    - x : `EXECUTE`

Note: Upon downloading my key (myEC2Key.pem) my permission on the key was `rw- r-- r--` <br />
When I change permission it should look like this `-r-- --- ---`

```
--- --- ---
0   0   0
```

```
--- --- --x
0   0   1   
```


```
r-- --- ---
4   0   0

User: 100 ---> 4
Group: 000 ---> 0
Others: 000 ---> 0
```

- Get permission on the key `ls -al | grep "nameOfTheKey.pem"`

### Connecting to a Linux Server
`ssh -i "myEC2Key.pem" ubuntu@ec2-44-201-25-51.compute-1.amazonaws.com`

We need 3 important things
- the key `"*.pem"` - purity.pem, devops.pem, myEC2Key.pem
- the user : `ubuntu`
- IP Address (Internet Protocol): `ec2-44-201-25-51.compute-1.amazonaws.com` or `44.201.25.51`

#### Renaming the Server
Run the following command
```
sudo hostnamectl set-hostname "yourDesiredName"

sudo su ubuntu
```

#### Perform an update
```
sudo apt update
```

### July 14, 2022
`key` : it is what connect you to a server.
Security Group: it is firewall rule that controls incoming & outgoing traffic. it is a virtual firewall the Ec2 instance.(it is a rules  that prevents incoming & outgoing traffic)