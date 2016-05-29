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
remote: Counting objects: 97618, done.
remote: Compressing objects: 100% (19757/19757), done.
remote: Total 97618 (delta 83649), reused 91477 (delta 77600)
Receiving objects: 100% (97618/97618), 19.41 MiB | 106.00 KiB/s, done.
Resolving deltas: 100% (83649/83649), completed with 9530 local objects.
From https://git.kernel.org/pub/scm/linux/kernel/git/next/linux-next
 * [new branch]      akpm       -> linux-next/akpm
 * [new branch]      akpm-base  -> linux-next/akpm-base
 * [new branch]      master     -> linux-next/master
 * [new branch]      stable     -> linux-next/stable
 * [new tag]         next-20160527 -> next-20160527
user@workstation:~/linux$ 

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