---
title: "cohiwizard_python_raspi"
nav_exclude: true
_build:
  list: never
  render: always
---

## Installing the COHIWizard on the Raspberry Pi

The prepared Raspberry Pi image contains the operating system and the COHI-Player, **but the COHIWizard is not pre-installed**. It has to be installed afterwards directly on the Raspberry Pi from the GitHub repository:

1. Connect the Raspberry Pi to the internet (LAN or WLAN) and open a terminal.

2. Clone the [COHIWizard repository from GitHub](https://github.com/hermy-sf/COHIWizard/tree/main) into a directory of your choice:

```bash
git clone https://github.com/hermy-sf/COHIWizard.git
cd COHIWizard
```

3. Follow the instructions in the [README file](https://github.com/hermy-sf/COHIWizard/blob/main/README.md) under "Method B" (setting up a virtual Python environment and installing the required packages).

Attention: this installation is only recommended if you have some experience with GitHub, Python and the Linux command line. The COHI-Player remains installed on the image and can be used alternatively.
