---
title: Computer
linkTitle: Computer
date: 2026-01-01
weight: 5
description: >
---

The control computer has the task of reading the data from the recording files and transmitting it to the respectively connected signal converter. Depending on the control device, the data must either only be forwarded or, if necessary, recalculated and prepared beforehand. To make this convenient, suitable software runs on this computer.

Depending on the selected configuration (see the Selection Guide for this), the computer can be a standard PC or a sufficiently powerful single-board computer such as a Raspberry Pi, Model 4 or 5.

Since the data files are typically very large, they are often stored on external data carriers (hard drives, large USB sticks). For example, about 18GB per hour of runtime is needed for an MW band at standard IQ recording format (1.25MS/s, 4Byte/sample). Here, the PC has the advantage that, if a large hard drive is available, it can also be used simultaneously as storage for recordings. Furthermore, it is often already available for other purposes in the household anyway. However, if you want a compact stand-alone system, a single-board computer is a good choice.

### PC as Control Computer

When a signal converter equipped with an FPGA, such as the RedPitaya STEMLAB 125-14, is used, only fast reading of the data (possibly from an external disk via USB3.0) and a LAN connection are required; no very high demands are placed on the computer.

However, if, for example, the OSMO fl2k dongle is used, a certain amount of computing power is required. So far, it has been tested on the following computers under Windows 10 and Windows 11:

* Lenovo T430, Intel-Core i5-3320M, 8GB RAM
* Acer Swift, AMD Ryzen 5 4500U, 8GB RAM
* Acer Aspire 5, Intel-Core i7-1165G7, 16GB RAM
* HP250G6, Intel (R) Core (TM) i3-6006U CPU @ 2.00 GHz, 8GB RAM
* TODO: Computer from Claus-Peter




The software has so far been developed on a Lenovo T590 with Intel Core i7 with 32GB RAM. The software has been tested on PCs so far under Windows 10, Windows 11, and LINUX Debian 12 and Debian 13.


## Raspberry Pi as Control Computer

A Raspberry Pi 4 is suitable as the smallest single-board computer tested so far, in conjunction with software reduced to the essentials, the COHI-Player Mini, very well for pure playback on a STEMLAB. **TODO: CHECK, not yet sufficiently tested!!!!** Together with the OSMO-fl2k, the most cost-effective system to date can be realized, although it has certain limitations. **END TODO**. With a Raspberry Pi 5, you can also run the full version of the Python variant of the software written for the PC and alternative playback programs (see links under 'Projects') without any problems. For the Raspberry Pi 4 with COHI-Player Mini, 4GB of RAM is sufficient; with the Raspberry Pi 5, a 4GB version has not yet been tested, but 8GB is definitely sufficient.

Fig. 1 shows a Raspberry Pi 5 in a desktop housing with a 7" touch display while it couples a broadband signal into a Hornyphon W248U via an OSMO-fl2k. The COHIWizard was used as software here. (Click to go to the video):

{{< video_ext url="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/Raspi5_COHIRADIA_Demo_1_20260208_144840.mp4" width="60%" align="left" showframe_time="0" caption="Fig. 1: Raspberry Pi 5 in conjunction with a Hornyphon W248U." >}}



<!-- comment -->