---
title: "cohi_player_config"
nav_exclude: true
_build:
  list: never
  render: always
---

## Configuring the COHI-Player

The three basic settings – **output hardware** (STEMLAB or fl2k), **operating mode** (COHI-Player, COHI-Stream or COHI-Player+Stream) and **display size** – are most easily set with the graphical configuration tool. It is touch-friendly and can also be operated on the 3.5" display. Start it in the program directory of the COHI-Player:

```bash
python3 cohi_config_gui.py
```

Alternatively, there is a terminal version with numbered menus, which additionally lets you choose the language (English/German):

```bash
python3 cohi_config_setup.py
```

All other settings (e.g. the directories containing the wav recordings, the language, or shutting down the computer on exit) are stored in the file `config_sdr.yaml` in the program directory, where they are explained by comments. Changes take effect after restarting the program. The station list for the internet radio streams can be loaded, edited and saved directly in the program.

A STEMLAB is found automatically on the local network; alternatively, its IP address can be entered in `config_sdr.yaml`.

Details on all settings, operation and troubleshooting can be found in the [user manual (README)](https://github.com/CPG-Archive/COHI-Player-Universal/blob/master/README.md).
