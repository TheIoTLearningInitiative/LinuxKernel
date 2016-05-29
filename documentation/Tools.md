# Tools

- [Compiling, Linking and Building C/C++ Applications](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/gcc_make.html)

> nm
> > list symbols from object files

> objdump
> > 

> readelf
> > 

> hexdump
> > 

> objdump
> > 


## Compiler

```sh
user@workstation:~$ gcc --version
gcc (Debian 4.9.2-10) 4.9.2
Copyright (C) 2014 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
user@workstation:~$ 
```

### Linker


```sh
user@workstation:~$ ld -v
GNU ld (GNU Binutils for Debian) 2.25
user@workstation:~$ 
```

## Hello World Compilation Process, Manual

```c
#include <stdio.h>

int main() {
    printf("Hello World\n");
    return 0;
}
```

### Pre-Processing GNU C Preprocessor

```sh
user@workstation:~$ cpp main.c > main.i
user@workstation:~$ 
```

```sh
user@workstation:~$ cat main.i 
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
...
...
extern void funlockfile (FILE *__stream) __attribute__ ((__nothrow__ , __leaf__));
# 943 "/usr/include/stdio.h" 3 4

# 2 "main.c" 2

int main() {
    printf("Hello World\n");
    return 0;
}
```

### Compilation

```
user@workstation:~$ gcc -S main.i
user@workstation:~$ ls main*
main.c  main.i  main.s
user@workstation:~$ 
```


```
xe1gyq@jessie:~$ cat main.s
	.file	"main.c"
	.section	.rodata
.LC0:
	.string	"Hello World"
	.text
	.globl	main
	.type	main, @function
main:
.LFB0:
	.cfi_startproc
	leal	4(%esp), %ecx
	.cfi_def_cfa 1, 0
	andl	$-16, %esp
	pushl	-4(%ecx)
	pushl	%ebp
	.cfi_escape 0x10,0x5,0x2,0x75,0
	movl	%esp, %ebp
	pushl	%ecx
	.cfi_escape 0xf,0x3,0x75,0x7c,0x6
	subl	$4, %esp
	subl	$12, %esp
	pushl	$.LC0
	call	puts
	addl	$16, %esp
	movl	$0, %eax
	movl	-4(%ebp), %ecx
	.cfi_def_cfa 1, 0
	leave
	.cfi_restore 5
	leal	-4(%ecx), %esp
	.cfi_def_cfa 4, 4
	ret
	.cfi_endproc
.LFE0:
	.size	main, .-main
	.ident	"GCC: (Debian 4.9.2-10) 4.9.2"
	.section	.note.GNU-stack,"",@progbits
user@workstation:~$ 
```

### Assembly

```
user@workstation:~$ as -o main.o main.s
user@workstation:~$ ls main*
main.c  main.i  main.o  main.s
user@workstation:~$  
```

```
user@workstation:~$ objdump -t main.o

main.o:     file format elf32-i386

SYMBOL TABLE:
00000000 l    df *ABS*	00000000 main.c
00000000 l    d  .text	00000000 .text
00000000 l    d  .data	00000000 .data
00000000 l    d  .bss	00000000 .bss
00000000 l    d  .rodata	00000000 .rodata
00000000 l    d  .note.GNU-stack	00000000 .note.GNU-stack
00000000 l    d  .eh_frame	00000000 .eh_frame
00000000 l    d  .comment	00000000 .comment
00000000 g     F .text	0000002e main
00000000         *UND*	00000000 puts

user@workstation:~$  
```

```sh
user@workstation:~$ nm main.o
00000000 T main
         U puts
user@workstation:~$          
```

### Linker

```sh
user@workstation:~$ ld -o main main.o 
ld: warning: cannot find entry symbol _start; defaulting to 0000000008048074
main.o: In function `main':
main.c:(.text+0x1a): undefined reference to `puts'
user@workstation:~$ 
```

## Hello World Compilation Process, Automated

```
user@workstation:~$ gcc -v main.c -o main
Using built-in specs.
COLLECT_GCC=gcc
COLLECT_LTO_WRAPPER=/usr/lib/gcc/i586-linux-gnu/4.9/lto-wrapper
Target: i586-linux-gnu
Configured with: ../src/configure -v --with-pkgversion='Debian 4.9.2-10' --with-bugurl=file:///usr/share/doc/gcc-4.9/README.Bugs --enable-languages=c,c++,java,go,d,fortran,objc,obj-c++ --prefix=/usr --program-suffix=-4.9 --enable-shared --enable-linker-build-id --libexecdir=/usr/lib --without-included-gettext --enable-threads=posix --with-gxx-include-dir=/usr/include/c++/4.9 --libdir=/usr/lib --enable-nls --with-sysroot=/ --enable-clocale=gnu --enable-libstdcxx-debug --enable-libstdcxx-time=yes --enable-gnu-unique-object --disable-vtable-verify --enable-plugin --with-system-zlib --disable-browser-plugin --enable-java-awt=gtk --enable-gtk-cairo --with-java-home=/usr/lib/jvm/java-1.5.0-gcj-4.9-i386/jre --enable-java-home --with-jvm-root-dir=/usr/lib/jvm/java-1.5.0-gcj-4.9-i386 --with-jvm-jar-dir=/usr/lib/jvm-exports/java-1.5.0-gcj-4.9-i386 --with-arch-directory=i386 --with-ecj-jar=/usr/share/java/eclipse-ecj.jar --enable-objc-gc --enable-targets=all --enable-multiarch --with-arch-32=i586 --with-multilib-list=m32,m64,mx32 --enable-multilib --with-tune=generic --enable-checking=release --build=i586-linux-gnu --host=i586-linux-gnu --target=i586-linux-gnu
Thread model: posix
gcc version 4.9.2 (Debian 4.9.2-10) 
COLLECT_GCC_OPTIONS='-v' '-o' 'main' '-mtune=generic' '-march=i586'
 /usr/lib/gcc/i586-linux-gnu/4.9/cc1 -quiet -v -imultiarch i386-linux-gnu main.c -quiet -dumpbase main.c -mtune=generic -march=i586 -auxbase main -version -o /tmp/ccf2KJ9x.s
GNU C (Debian 4.9.2-10) version 4.9.2 (i586-linux-gnu)
	compiled by GNU C version 4.9.2, GMP version 6.0.0, MPFR version 3.1.2-p3, MPC version 1.0.2
GGC heuristics: --param ggc-min-expand=100 --param ggc-min-heapsize=131072
ignoring nonexistent directory "/usr/local/include/i386-linux-gnu"
ignoring nonexistent directory "/usr/lib/gcc/i586-linux-gnu/4.9/../../../../i586-linux-gnu/include"
#include "..." search starts here:
#include <...> search starts here:
 /usr/lib/gcc/i586-linux-gnu/4.9/include
 /usr/local/include
 /usr/lib/gcc/i586-linux-gnu/4.9/include-fixed
 /usr/include/i386-linux-gnu
 /usr/include
End of search list.
GNU C (Debian 4.9.2-10) version 4.9.2 (i586-linux-gnu)
	compiled by GNU C version 4.9.2, GMP version 6.0.0, MPFR version 3.1.2-p3, MPC version 1.0.2
GGC heuristics: --param ggc-min-expand=100 --param ggc-min-heapsize=131072
Compiler executable checksum: 01d8da4b8303b5d93fb017bb5b178083
COLLECT_GCC_OPTIONS='-v' '-o' 'main' '-mtune=generic' '-march=i586'
 as -v --32 -o /tmp/ccSNuLny.o /tmp/ccf2KJ9x.s
GNU assembler version 2.25 (i586-linux-gnu) using BFD version (GNU Binutils for Debian) 2.25
COMPILER_PATH=/usr/lib/gcc/i586-linux-gnu/4.9/:/usr/lib/gcc/i586-linux-gnu/4.9/:/usr/lib/gcc/i586-linux-gnu/:/usr/lib/gcc/i586-linux-gnu/4.9/:/usr/lib/gcc/i586-linux-gnu/
LIBRARY_PATH=/usr/lib/gcc/i586-linux-gnu/4.9/:/usr/lib/gcc/i586-linux-gnu/4.9/../../../i386-linux-gnu/:/usr/lib/gcc/i586-linux-gnu/4.9/../../../../lib/:/lib/i386-linux-gnu/:/lib/../lib/:/usr/lib/i386-linux-gnu/:/usr/lib/../lib/:/usr/lib/gcc/i586-linux-gnu/4.9/../../../:/lib/:/usr/lib/
COLLECT_GCC_OPTIONS='-v' '-o' 'main' '-mtune=generic' '-march=i586'
 /usr/lib/gcc/i586-linux-gnu/4.9/collect2 -plugin /usr/lib/gcc/i586-linux-gnu/4.9/liblto_plugin.so -plugin-opt=/usr/lib/gcc/i586-linux-gnu/4.9/lto-wrapper -plugin-opt=-fresolution=/tmp/ccdqYGCy.res -plugin-opt=-pass-through=-lgcc -plugin-opt=-pass-through=-lgcc_s -plugin-opt=-pass-through=-lc -plugin-opt=-pass-through=-lgcc -plugin-opt=-pass-through=-lgcc_s --sysroot=/ --build-id --eh-frame-hdr -m elf_i386 --hash-style=gnu -dynamic-linker /lib/ld-linux.so.2 -o main /usr/lib/gcc/i586-linux-gnu/4.9/../../../i386-linux-gnu/crt1.o /usr/lib/gcc/i586-linux-gnu/4.9/../../../i386-linux-gnu/crti.o /usr/lib/gcc/i586-linux-gnu/4.9/crtbegin.o -L/usr/lib/gcc/i586-linux-gnu/4.9 -L/usr/lib/gcc/i586-linux-gnu/4.9/../../../i386-linux-gnu -L/usr/lib/gcc/i586-linux-gnu/4.9/../../../../lib -L/lib/i386-linux-gnu -L/lib/../lib -L/usr/lib/i386-linux-gnu -L/usr/lib/../lib -L/usr/lib/gcc/i586-linux-gnu/4.9/../../.. /tmp/ccSNuLny.o -lgcc --as-needed -lgcc_s --no-as-needed -lc -lgcc --as-needed -lgcc_s --no-as-needed /usr/lib/gcc/i586-linux-gnu/4.9/crtend.o /usr/lib/gcc/i586-linux-gnu/4.9/../../../i386-linux-gnu/crtn.o
user@workstation:~$ 
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
