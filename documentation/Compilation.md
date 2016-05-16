# Compilation

- [Linux Kernel Git Repository](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/)

## Dependencies Setup

```sh
root@workstation:~# apt-get update
root@workstation:~# apt-get upgrade
root@workstation:~# apt-get install linux-headers-$(uname -r) kernel-package libncurses5 libncurses5-dev git
```

## Source Code Cloning

```sh
user@workstation:~$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
Cloning into 'linux'...
remote: Counting objects: 4697469, done.
remote: Compressing objects: 100% (3641/3641), done.
...
user@workstation:~$ cd linux
```

## System Information, Actual Version

```sh
user@workstation:~$ uname -a
Linux jessie 3.16.0-4-686-pae #1 SMP Debian 3.16.7-ckt20-1+deb8u4 (2016-02-29) i686 GNU/Linux
```

## Linux Kernel Compilation, Latest Version

```sh
user@workstation:~$ make oldconfig
<You will be asked configuration questions not answered, hit Enter for all of them>
user@workstation:~$ make
root@workstation:~# make modules_install
root@workstation:~# make install
```

## Linux Kernel Compilation, Latest Version

Reboot your workstation and confirm the new version has been installed

    user@workstation:~$ uname -a
    Linux Minnowboard 3.19.0-rc7+ #1 SMP Debian ... x86_64 GNU/Linux