# LinuxKernel

- [Linux Kernel Git Repository](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/)

## Packages Setup

```sh
root@workstation:~# apt-get update
root@workstation:~# apt-get upgrade
root@workstation:~# apt-get install linux-headers-$(uname -r) kernel-package libncurses5 libncurses5-dev git
```

## Source Code

```sh
user@workstation:~$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
Cloning into 'linux'...
remote: Counting objects: 4697469, done.
remote: Compressing objects: 100% (3641/3641), done.
```

```sh
user@workstation:~$ uname -a
Linux Minnowboard 3.2.0-4-amd64 #1 SMP Debian 3.2.63-2+deb7u2 x86_64 GNU/Linux
user@workstation:~$ cd linux
user@workstation:~$ make oldconfig
<You will be asked configuration questions not answered, hit Enter for all of them>
user@workstation:~$ make
root@workstation:~# make modules_install
root@workstation:~# make install
```