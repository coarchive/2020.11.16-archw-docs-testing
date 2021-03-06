---
title: "How to Use"
---
# How to Use (Installed Instance)
## exe Usage

```
Usage :
    <no args>
      - Open a new shell with your default settings.

    run <command line>
      - Run the given command line in that distro. Inherit current directory.

    runp <command line (includes windows path)>
      - Run the path translated command line in that distro.

    config [setting [value]]
      - `--default-user <user>`: Set the default user for this distro to <user>
      - `--default-uid <uid>`: Set the default user uid for this distro to <uid>
      - `--append-path <on|off>`: Switch of Append Windows PATH to $PATH
      - `--mount-drive <on|off>`: Switch of Mount drives

    get [setting]
      - `--default-uid`: Get the default user uid in this distro
      - `--append-path`: Get on/off status of Append Windows PATH to $PATH
      - `--mount-drive`: Get on/off status of Mount drives
      - `--lxguid`: Get WSL GUID key for this distro

    backup [contents]
      - `--tgz`: Output backup.tar.gz to the current directory using tar command
      - `--reg`: Output settings registry file to the current directory

    clean
      - Uninstall the distro.

    help
      - Print this usage message.
```


## Just Run exe
```
>Arch.exe
[root@PC-NAME user]#
```

## Run with command line
```
>Arch.exe run uname -r
4.4.0-43-Microsoft
```

## Run with command line with path translation
```
>Arch.exe runp echo C:\Windows\System32\cmd.exe
/mnt/c/Windows/System32/cmd.exe
```

## Change Default User(id command required)
```
>Arch.exe config --default-user user

>Arch.exe
[user@PC-NAME dir]$
```
If the default user has not been changed, please reboot the computer.(issue [#7](https://github.com/yuk7/ArchWSL/issues/7))
> You can try to do before it (From [This Comment](https://github.com/yuk7/ArchWSL/issues/7#issuecomment-397725710))
>```
>sc stop LxssManager
>sc start LxssManager
>```

## How to backup instance image
backup
```
>Arch.exe backup
```
restore/install backup tarball
```
>Arch.exe install full/path/to/backup.tar.gz
```


## How to uninstall instance

```
>Arch.exe clean

```
