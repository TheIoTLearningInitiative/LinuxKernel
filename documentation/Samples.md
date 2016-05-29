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
      