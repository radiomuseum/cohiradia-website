---
title: "stemlab_SDcard_LINUX"
nav_exclude: true
_build:
  list: never
  render: always
---

## Prepare Firmware for STEMLAB

Before the STEMLAB125-XX can be put into operation with COHIRADIA, the SD card must be prepared with the operating system and server software.
The STEMLAB is usually delivered with an SD card containing the operating system. However, this alone does not yet enable communication with the COHIRADIA software on the PC.

**Therefore, please be sure to create a new SD card as follows:**

1. Insert a new SD card (at least 8 GB) into the SD card slot of your PC (if available) or into an SD card reader connected to your PC. You can also overwrite the included card if necessary, but you usually want to keep it as the original for safety.

2. Download the [Image file cohiradia_STEMLAB125_v1.0.img](https://cohiradia.radiomuseum.org/download/software/cohiradia_STEMLAB125_v1.0.img) from the COHIRADIA software archive and save it to any directory.

3. Write the image to the SD card using suitable software. Under LINUX, [Balena Etcher](https://etcher.balena.io/#download-etcher) is suitable. Of course, it can also be done directly on the command line:
First read the mounted SD card partitions:

```bash
lsblk -f
```
These are listed as, e.g., sdb1, sdb2 or similar. Then unmount the SD devices and start writing:

```bash
sudo umount /dev/YOURSDDEVICE*
```
YOURSDDEVICE is then what your lsblk lists, in my example sbd. Then:

```bash
sudo dd if=redpitaya_full.img of=/dev/YOURSDDEVICE bs=4M status=progress conv=fsync
```
Now the card will be written. When it's finished, eject the card:

```bash
sudo eject /dev/YOURSDDEVICE
```
Then it can be inserted into the SD card slot of the STEMLAB and the STEMLAB should be ready for operation.


**ATTENTION: dd must be used with great caution. If you specify the wrong target, important system drives may be erased. So please check three times what you are doing!**