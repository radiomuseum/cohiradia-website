---
title: "Raspberry4_SDcard"
nav_exclude: true
_build:
  list: never
  render: always
---

Before the Raspberry Pi 4 can be put into operation with the COHI Player Mini, the SD card must be prepared with the operating system and the COHI Player Mini software.

**Create a new SD card as follows:**

1. Insert a new SD card (at least 16 GB) into the SD card slot of your PC (if available) or into an SD card reader connected to your PC.

2. Download the [Image file ](https://cohiradia.radiomuseum.org/download/software/COHI-RasPi4_V4.1_shrink.img) from the COHIRADIA software archive and save it to any directory.

3. Write the image to the SD card using suitable software. Under LINUX, [Balena Etcher](https://etcher.balena.io/#download-etcher) is suitable. Of course, it can also be done directly on the command line:
First read the mounted SD card partitions:

```bash
lsblk -f
```
These are listed as, e.g., sdb1, sdb2 or similar. Then unmount the SD devices and start writing:

```bash
sudo umount /dev/YOURSDDEVICE*
```
YOURSDDEVICE is then what your lsblk lists, in my example sbd. Then change to the directory, to which you have downloaded the image file and type:

```bash
sudo dd if=COHI-RasPi4_V4.1_shrink.img of=/dev/YOURSDDEVICE bs=4M status=progress conv=fsync

```
Now the card will be written. When it's finished, sync and eject the card:

```bash
sync
sudo eject /dev/YOURSDDEVICE
```
Afterwards it can be inserted into the SD card slot of the Raspberry Pi which then should be ready for operation.


**ATTENTION: dd must be used with great caution. If you specify the wrong target, important system drives may be erased. So please check three times what you are doing!**