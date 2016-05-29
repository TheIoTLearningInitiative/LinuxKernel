# Kernel Trees

## Linux-Next

- [Working with Linux-Next](https://www.kernel.org/doc/man-pages/linux-next.html)


```sh
user@workstation:~$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
Cloning into 'linux'...
...
Checking out files: 100% (53660/53660), done.
user@workstation:~$ cd linux
user@workstation:~/linux$ git remote add linux-next https://git.kernel.org/pub/scm/linux/kernel/git/next/linux-next.git
user@workstation:~/linux$ git fetch linux-next
user@workstation:~/linux$ make oldconfig
<You will be asked configuration questions not answered, hit Enter for all of them>
user@workstation:~/linux$ make -j3
  IHEX2FW firmware/whiteheat_loader.fw
  IHEX2FW firmware/whiteheat.fw
  IHEX2FW firmware/keyspan_pda/keyspan_pda.fw
  IHEX2FW firmware/keyspan_pda/xircom_pgs.fw
user@workstation:~/linux# make modules_install

root@workstation:~# make install
```