---
title: "Postfix Raspberry Pi"
nav_exclude: true
_build:
  list: never
  render: always
---

3. Write the image to the SD card using suitable software. For Windows, [Win32Diskimager](https://win32diskimager.org/) or [Balena Etcher](https://etcher.balena.io/#download-etcher) are suitable.<br/>
Under LINUX, [Balena Etcher](https://etcher.balena.io/#download-etcher) is suitable. If you opt for directly using the command line, just type the following commands: <br/>

Read the mounted SD card partitions:

```bash
lsblk -f
```
These are listed as, e.g., sda1, sda2 or similar. Then unmount the SD devices:

```bash
sudo umount /dev/YOURSDDEVICE*
```
YOURSDDEVICE is then what your lsblk lists, in my above example 'sda'. Then change to the directory, to which you have downloaded the image file and type:

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

<br/>


### Alternative installation directly from the source code

Alternatively, for Step 2, you can also perform a custom installation directly from the [source code on GitHub](https://github.com/CPG-Archive/COHI-Player/). This may be useful if you already have a suitable OS (Trixie) installed on your Raspberry Pi or if you simply want to update the COHIA Player software.

**For special questions concerning the software for Raspberry Pi please contact Claus Peter Gallenmiller [email](mailto:cpg-radio@gmx.de).**
