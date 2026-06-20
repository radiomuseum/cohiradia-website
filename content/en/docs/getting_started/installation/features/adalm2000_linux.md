---
title: "adalm2000_linux"
nav_exclude: true
_build:
  list: never
  render: always
---


## Installation of the Driver for ADALM2000:

To operate the ADALM2000 on a PC, libm2k must be installed. [On this page](https://wiki.analog.com/university/tools/m2k/libm2k/libm2k#windows) you will find the corresponding instructions for various operating systems.

Since the ADALM2000 option has so far been verified by only one user other than the COHIRADIA team, there is limited experience regarding installation issues. However, the drivers were generally installed successfully on both Windows 10 and Debian 12/13. Here is an [initial test report](../../../documentation/Testberichte/ADALM2000.html) on performance. 
**Please also make sure** to insert a passive antialiasing filter between the ADALM2000 and the connected receiver in order to suppress excessive noise, as described in this report.