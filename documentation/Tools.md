# Tools

## Compiler

```sh
user@workstation:~$ gcc --version
gcc (Debian 4.9.2-10) 4.9.2
Copyright (C) 2014 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
user@workstation:~$ 
```


## Linker


```sh
user@workstation:~$ ld -v
GNU ld (GNU Binutils for Debian) 2.25
user@workstation:~$ 
```


```c
#include <stdio.h>

int main() {
    printf("Hello World\n");
    return 0;
}
```

```sh
xe1gyq@jessie:~$ cpp main.c > main.i
xe1gyq@jessie:~$ 
```

```sh
xe1gyq@jessie:~$ cat main.i 
# 1 "main.c"
# 1 "<built-in>"
# 1 "<command-line>"
# 1 "/usr/include/stdc-predef.h" 1 3 4
# 1 "<command-line>" 2
# 1 "main.c"
# 1 "/usr/include/stdio.h" 1 3 4
# 27 "/usr/include/stdio.h" 3 4
# 1 "/usr/include/features.h" 1 3 4
# 374 "/usr/include/features.h" 3 4
# 1 "/usr/include/i386-linux-gnu/sys/cdefs.h" 1 3 4
# 385 "/usr/include/i386-linux-gnu/sys/cdefs.h" 3 4
# 1 "/usr/include/i386-linux-gnu/bits/wordsize.h" 1 3 4
# 386 "/usr/include/i386-linux-gnu/sys/cdefs.h" 2 3 4
# 375 "/usr/include/features.h" 2 3 4
# 398 "/usr/include/features.h" 3 4
# 1 "/usr/include/i386-linux-gnu/gnu/stubs.h" 1 3 4
```


```

```

## Make


```sh
user@workstation:~$ gcc --version
gcc (Debian 4.9.2-10) 4.9.2
Copyright (C) 2014 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
user@workstation:~$ 
```
