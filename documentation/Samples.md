# Samples

```sh
user@workstation:~/linux$ make menuconfig
  HOSTCC  scripts/kconfig/mconf.o
  HOSTCC  scripts/kconfig/lxdialog/checklist.o
  HOSTCC  scripts/kconfig/lxdialog/util.o
  HOSTCC  scripts/kconfig/lxdialog/inputbox.o
  HOSTCC  scripts/kconfig/lxdialog/textbox.o
  HOSTCC  scripts/kconfig/lxdialog/yesno.o
  HOSTCC  scripts/kconfig/lxdialog/menubox.o
  HOSTLD  scripts/kconfig/mconf
scripts/kconfig/mconf  Kconfig

< Kernel Menuconfig Screen >

```

```sh
   Symbol: SAMPLES [=n]
   Type  : boolean
   Prompt: Sample kernel code
     Location:
   (1) -> Kernel hacking
     Defined at samples/Kconfig:1
```

```sh
[ ] Sample kernel code  ----
```

```sh
      --- Sample kernel code
      < >   Build trace_events examples -- loadable modules only (NEW)
      < >   Build kobject examples -- loadable modules only (NEW)
      < >   Build kprobes examples -- loadable modules only (NEW)
      < >   Build kernel hardware breakpoint examples -- loadable modules (NEW)
      < >   Build kfifo examples -- loadable modules only (NEW)
      < >   Build configfs patching sample -- loadable modules only (NEW)
```

```sh
user@workstation:~/linux$ make  ARCH=x86
  CHK     include/config/kernel.release
  CHK     include/generated/uapi/linux/version.h
  CHK     include/generated/utsrelease.h
  CHK     include/generated/bounds.h
  CHK     include/generated/timeconst.h
  CHK     include/generated/asm-offsets.h
  CALL    scripts/checksyscalls.sh
  CHK     include/generated/compile.h
  LD      samples/configfs/built-in.o
  CC [M]  samples/configfs/configfs_sample.o
  LD      samples/hidraw/built-in.o
  HOSTCC  samples/hidraw/hid-example
  LD      samples/hw_breakpoint/built-in.o
  CC [M]  samples/hw_breakpoint/data_breakpoint.o
  LD      samples/kdb/built-in.o
  LD      samples/kfifo/built-in.o
  CC [M]  samples/kfifo/bytestream-example.o
  CC [M]  samples/kfifo/dma-example.o
  CC [M]  samples/kfifo/inttype-example.o
  CC [M]  samples/kfifo/record-example.o
  LD      samples/kobject/built-in.o
  CC [M]  samples/kobject/kobject-example.o
  CC [M]  samples/kobject/kset-example.o
  LD      samples/kprobes/built-in.o
  CC [M]  samples/kprobes/kprobe_example.o
  CC [M]  samples/kprobes/jprobe_example.o
  CC [M]  samples/kprobes/kretprobe_example.o
  LD      samples/livepatch/built-in.o
  LD      samples/rpmsg/built-in.o
  LD      samples/seccomp/built-in.o
  HOSTCC  samples/seccomp/bpf-fancy.o
  HOSTCC  samples/seccomp/bpf-helper.o
  HOSTLD  samples/seccomp/bpf-fancy
  HOSTCC  samples/seccomp/dropper.o
  HOSTLD  samples/seccomp/dropper
  HOSTCC  samples/seccomp/bpf-direct.o
  HOSTLD  samples/seccomp/bpf-direct
  LD      samples/trace_events/built-in.o
  CC [M]  samples/trace_events/trace-events-sample.o
  LD      samples/built-in.o
Kernel: arch/x86/boot/bzImage is ready  (#1)
  Building modules, stage 2.
  MODPOST 3226 modules
  CC      samples/configfs/configfs_sample.mod.o
  LD [M]  samples/configfs/configfs_sample.ko
  CC      samples/hw_breakpoint/data_breakpoint.mod.o
  LD [M]  samples/hw_breakpoint/data_breakpoint.ko
  CC      samples/kfifo/bytestream-example.mod.o
  LD [M]  samples/kfifo/bytestream-example.ko
  CC      samples/kfifo/dma-example.mod.o
  LD [M]  samples/kfifo/dma-example.ko
  CC      samples/kfifo/inttype-example.mod.o
  LD [M]  samples/kfifo/inttype-example.ko
  CC      samples/kfifo/record-example.mod.o
  LD [M]  samples/kfifo/record-example.ko
  CC      samples/kobject/kobject-example.mod.o
  LD [M]  samples/kobject/kobject-example.ko
  CC      samples/kobject/kset-example.mod.o
  LD [M]  samples/kobject/kset-example.ko
  CC      samples/kprobes/jprobe_example.mod.o
  LD [M]  samples/kprobes/jprobe_example.ko
  CC      samples/kprobes/kprobe_example.mod.o
  LD [M]  samples/kprobes/kprobe_example.ko
  CC      samples/kprobes/kretprobe_example.mod.o
  LD [M]  samples/kprobes/kretprobe_example.ko
  CC      samples/trace_events/trace-events-sample.mod.o
  LD [M]  samples/trace_events/trace-events-sample.ko
user@workstation:~/linux$
```