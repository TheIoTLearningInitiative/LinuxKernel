# Kernel Trees

## Linux-Next

- [Working with Linux-Next](https://www.kernel.org/doc/man-pages/linux-next.html)


```sh
user@workstation:~$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
Cloning into 'linux'...
...
Checking out files: 100% (53660/53660), done.
user@workstation:~$ cd linux
```

```sh
user@workstation:~/linux$ git remote add linux-next https://git.kernel.org/pub/scm/linux/kernel/git/next/linux-next.git
```

```sh
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
```

```sh
user@workstation:~/linux$ git fetch --tags linux-next
remote: Counting objects: 126380, done.
remote: Compressing objects: 100% (26312/26312), done.
remote: Total 126380 (delta 111790), reused 113686 (delta 99914)
Receiving objects: 100% (126380/126380), 18.05 MiB | 149.00 KiB/s, done.
Resolving deltas: 100% (111790/111790), completed with 3716 local objects.
From https://git.kernel.org/pub/scm/linux/kernel/git/next/linux-next
 * [new tag]         next-20160229 -> next-20160229
 * [new tag]         next-20160301 -> next-20160301
 * [new tag]         next-20160302 -> next-20160302
 * [new tag]         next-20160303 -> next-20160303
 * [new tag]         next-20160304 -> next-20160304
 * [new tag]         next-20160307 -> next-20160307
 * [new tag]         next-20160308 -> next-20160308
 * [new tag]         next-20160309 -> next-20160309
 * [new tag]         next-20160310 -> next-20160310
 * [new tag]         next-20160311 -> next-20160311
 * [new tag]         next-20160314 -> next-20160314
 * [new tag]         next-20160315 -> next-20160315
 * [new tag]         next-20160316 -> next-20160316
 * [new tag]         next-20160317 -> next-20160317
 * [new tag]         next-20160318 -> next-20160318
 * [new tag]         next-20160321 -> next-20160321
 * [new tag]         next-20160322 -> next-20160322
 * [new tag]         next-20160323 -> next-20160323
 * [new tag]         next-20160324 -> next-20160324
 * [new tag]         next-20160327 -> next-20160327
 * [new tag]         next-20160329 -> next-20160329
 * [new tag]         next-20160330 -> next-20160330
 * [new tag]         next-20160331 -> next-20160331
 * [new tag]         next-20160401 -> next-20160401
 * [new tag]         next-20160404 -> next-20160404
 * [new tag]         next-20160405 -> next-20160405
 * [new tag]         next-20160406 -> next-20160406
 * [new tag]         next-20160407 -> next-20160407
 * [new tag]         next-20160408 -> next-20160408
 * [new tag]         next-20160411 -> next-20160411
 * [new tag]         next-20160412 -> next-20160412
 * [new tag]         next-20160413 -> next-20160413
 * [new tag]         next-20160414 -> next-20160414
 * [new tag]         next-20160415 -> next-20160415
 * [new tag]         next-20160418 -> next-20160418
 * [new tag]         next-20160419 -> next-20160419
 * [new tag]         next-20160420 -> next-20160420
 * [new tag]         next-20160421 -> next-20160421
 * [new tag]         next-20160422 -> next-20160422
 * [new tag]         next-20160426 -> next-20160426
 * [new tag]         next-20160427 -> next-20160427
 * [new tag]         next-20160428 -> next-20160428
 * [new tag]         next-20160429 -> next-20160429
 * [new tag]         next-20160502 -> next-20160502
 * [new tag]         next-20160503 -> next-20160503
 * [new tag]         next-20160504 -> next-20160504
 * [new tag]         next-20160505 -> next-20160505
 * [new tag]         next-20160506 -> next-20160506
 * [new tag]         next-20160509 -> next-20160509
 * [new tag]         next-20160510 -> next-20160510
 * [new tag]         next-20160511 -> next-20160511
 * [new tag]         next-20160512 -> next-20160512
 * [new tag]         next-20160513 -> next-20160513
 * [new tag]         next-20160516 -> next-20160516
 * [new tag]         next-20160517 -> next-20160517
 * [new tag]         next-20160518 -> next-20160518
 * [new tag]         next-20160519 -> next-20160519
 * [new tag]         next-20160520 -> next-20160520
 * [new tag]         next-20160523 -> next-20160523
 * [new tag]         next-20160524 -> next-20160524
 * [new tag]         next-20160525 -> next-20160525
 * [new tag]         next-20160526 -> next-20160526
user@workstation:~/linux$ 
```

```sh
user@workstation:~/linux$ make oldconfig
<You will be asked configuration questions not answered, hit Enter for all of them>
user@workstation:~/linux$ make -j3
  IHEX2FW firmware/whiteheat_loader.fw
  IHEX2FW firmware/whiteheat.fw
  IHEX2FW firmware/keyspan_pda/keyspan_pda.fw
  IHEX2FW firmware/keyspan_pda/xircom_pgs.fw
root@workstation:~/linux# make modules_install

root@workstation:~/linux# make install
```

## Stable

```sh
user@workstation:~/linux$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git
```