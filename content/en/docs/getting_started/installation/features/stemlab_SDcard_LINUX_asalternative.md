---
title: "stemlab_SDcard_LINUX"
nav_exclude: true
_build:
  list: never
  render: always
---

#### Should you use LINUX:

Under LINUX, again the [Balena Etcher](https://etcher.balena.io/#download-etcher) is suitable. Alternatively you can write the SD card directly on the CLI using the following commands:<br/>

First read the mounted SD card partitions:

```bash
lsblk -f
```
These are listed as, e.g., sda1, sda2 or similar. Then unmount the SD devices and start writing:

```bash
sudo umount /dev/YOURSDDEVICE*
```
YOURSDDEVICE is then what your lsblk lists, in my example sda. Then:

```bash
sudo dd if=redpitaya_full.img of=/dev/YOURSDDEVICE bs=4M status=progress conv=fsync
```
Now the card will be written. When it's finished, eject the card:

```bash
sudo eject /dev/YOURSDDEVICE
```

**ATTENTION: dd must be used with great caution. If you specify the wrong target, important system drives may be erased. So please check three times what you are doing!**