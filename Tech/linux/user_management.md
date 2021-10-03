
# Linux commands - UBUNTU

## Creating a new user
```bash
adduser username
```

## Logout a user
```bash
logout
```

## Log as sudo on current user
```bash
sudo su
```
## Adding user to SUDO group

1. By editing the group file
    In file **/etc/group** add user to sudo group after comma eg.
```text
    sudo:x:27:noxiss,bolek
```
2. By command
```bash
    usermod -G <group> -a <username>
```

## Adding password for root user
```bash
    passwd root
```
## Show all installed packages
```bash
    apt list --installed
```

## Show the size of files and folders
du -sh *
