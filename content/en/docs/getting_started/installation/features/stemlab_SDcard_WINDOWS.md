---
title: "stemlab_SDcard_WINDOWS"
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

3. Write the image to the SD card using suitable software. For Windows, [Win32Diskimager](https://win32diskimager.org/) or [Balena Etcher](https://etcher.balena.io/#download-etcher) are suitable.


After that, eject the card and insert it into the SD card slot of the STEMLAB. The STEMLAB should then be ready for operation.