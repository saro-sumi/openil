***************************
NXP LS1021AIOT board
***************************

This file documents the Buildroot support for the NXP LS1021AIOT board.

Build
=====

First, configure Buildroot for LS1021AIOT board:

  make nxp_ls1021aiot_defconfig

Build all components:

  make

You will find in output/images/ the following files:
  - ls1021a-iot.dtb
  - rootfs.ext2
  - rootfs.tar
  - sdcard.img
  - u-boot.bin
  - uImage

Create a bootable SD card
=========================

Buildroot prepares a bootable "sdcard.img" image in the output/images/
directory, ready to be dumped on a SD card. Launch the following
command as root:

  dd if=./output/images/sdcard.img of=/dev/<your-sd-device>

*** WARNING! This will destroy all the card content. Use with care! ***

For details about the medium image layout, see the definition in
board/nxp/common/genimage.cfg.template.

Boot the LS1021AIOT board
=========================

To boot your newly created system:
- insert the SD card in the SD slot of the board;
- put a micro USB cable into the Debug USB Port and connect using a terminal
  emulator at 115200 bps, 8n1;
- power on the board.

Enjoy!
