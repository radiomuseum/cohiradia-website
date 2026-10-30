---
title: "Cohi-Player_LINUX"
nav_exclude: true
_build:
  list: never
  render: always
---

## Install the COHI-Player as Python Version for LINUX

You can install the COHI-Player from the [source code on GitHub](https://github.com/CPG-Archive/COHI-Player-Universal). Download the release or clone the repository into a directory of your choice and follow the installation instructions in the "Installation" section of the [README file](https://github.com/CPG-Archive/COHI-Player-Universal/blob/master/README.md). They essentially comprise

* installing some system packages (among others PyQt5, ffmpeg and – for the fl2k dongle – osmo-fl2k),
* installing the Python packages from `requirements.txt`, and
* compiling the C++ tools with `make` (required for the internet radio stream modes and the fl2k dongle).

The program is started in the program directory with

```bash
python3 cohi_player_main.py
```

Performance on a PC depends heavily on the installed CPU.

**For special questions concerning the COHI-Player please contact Claus Peter Gallenmiller [email](mailto:cpg-radio@gmx.de).**
