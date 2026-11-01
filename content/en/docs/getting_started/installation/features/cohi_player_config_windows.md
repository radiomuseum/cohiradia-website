---
title: "cohi_player_config_windows"
nav_exclude: true
_build:
  list: never
  render: always
---

## Configuring the COHI-Player

The basic settings – **output hardware** (STEMLAB or fl2k) and **display size** – are most easily set with the graphical configuration tool. Start it in the program directory of the COHI-Player:

```bash
python3 cohi_config_gui.py
```

Alternatively, there is a terminal version with numbered menus, which additionally lets you choose the language (English/German):

```bash
python3 cohi_config_setup.py
```

**Operating mode:** Under Windows, select the **COHI-Player** mode. The COHI-Stream and COHI-Player+Stream modes currently do not work under Windows.

All other settings (e.g. the directories containing the wav recordings, the language, or shutting down the computer on exit) are stored in the file `config_sdr.yaml` in the program directory, where they are explained by comments. Changes take effect after restarting the program.

A STEMLAB is found automatically on the local network; alternatively, its IP address can be entered in `config_sdr.yaml`.

Details on all settings, operation and troubleshooting can be found in the [user manual (README)](https://github.com/CPG-Archive/COHI-Player-Universal/blob/master/README.md).
