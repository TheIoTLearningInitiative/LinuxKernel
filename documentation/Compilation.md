# Compilation

- [Linux Kernel Source Tree](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/)

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
Receiving objects: 100% (4697469/4697469), 825.96 MiB | 372.00 KiB/s, done.
remote: Total 4697469 (delta 2172), reused 0 (delta 0)
Resolving deltas: 100% (3944070/3944070), done.
Checking connectivity... done.
Checking out files: 100% (53660/53660), done.
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

## System Information, Latest Version

Reboot your workstation and confirm the new version has been installed

```sh
user@workstation:~$ uname -a
```