3.0.8  Kitkat Kernel for Huawei Honor3
===========================================
Kernel release package version instruction

USE zImage NOTE:

1、This package make out zImage only, you have to get ramdisk and add kernel cmdline to generate a total boot.img before replace your phone's bootimage.
2、If your phone already enable secboot feature, please decrypt or unlock the secboot feature first.
3、Please make sure your phone software version is same with this release package, if not, please download the match version first.

This kernel package is released for the phone software version HN3-U01V100R001C00B000
################################################################################

1. How to Build
	- get Toolchain
		From android git server , codesourcery and etc ..
		 - arm-linux-androideabi-4.6

	- edit Makefile
		edit "CROSS_COMPILE" to right toolchain path(You downloaded).
		  EX)   CROSS_COMPILE= $(android platform directory you download)/android/prebuilts/gcc/linux-x86/arm/arm-linux-androideabi-4.6/bin/arm-linux-androideabi-
          Ex)   CROSS_COMPILE=/usr/local/toolchain/arm-linux-androideabi-4.6/bin/arm-linux-androideabi-          // check the location of toolchain
		  or
		  Ex)	export CROSS_COMPILE=arm-linux-androideabi-
		  Ex)	export PATH=$PATH:<toolchain_parent_dir>/arm-linux-androideabi-4.6/bin

		$ make ARCH=arm hisi_k3v2oem1_defconfig
		$ make ARCH=arm zImage

2. Output files
	- Kernel : arch/arm/boot/zImage
	- module : drivers/*/*.ko

3. How to Clean
		$ make ARCH=arm distclean
################################################################################
