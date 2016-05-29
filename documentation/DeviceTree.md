# Device Tree

> A devicetree is a data structure for describing hardware [Homepage](http://www.devicetree.org/)


```sh
xe1gyq@jessie:~/linux$ find -name *.dts
./arch/microblaze/boot/dts/system.dts
...
./arch/x86/platform/ce4100/falconfalls.dts
...
./arch/arm/boot/dts/armada-xp-matrix.dts
...
./arch/arm/boot/dts/omap4-sdp.dts
...
./drivers/of/unittest-data/testcases.dts
```

```sh
xe1gyq@jessie:~/linux$ make  ARCH=x86 falconfalls.dtsscripts/kconfig/conf  --silentoldconfig Kconfig
```