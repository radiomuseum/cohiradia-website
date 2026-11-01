---
title: "display_35_config"
nav_exclude: true
_build:
  list: never
  render: always
---

## OPTIONAL: Configuring the 3.5" display driver {#optional-display-driver}

**This section is only needed if you use the Raspberry 3.5" touchscreen display, type RPI-35LCD. In all other cases you can skip it.**

In the RasPi4 3.5" image, the display from CUQI is preconfigured. The driver can very easily be reconfigured for the Raspberry 3.5" touchscreen display, type RPI-35LCD:

1. Establish an SSH connection to the Raspberry Pi with PuTTY.
2. Log in with user `pi` and password `pi`.
3. When using the Raspberry 3.5" touchscreen, type RPI-35LCD, enter:

```bash
bash config_display_2.sh
```

The configuration for the CUQI display can be restored with

```bash
bash config_display_1.sh
```

If required, the touchscreen can be recalibrated in Raspberry Pi OS via the system menu under "Preferences" – "Calibrate Touchscreen".
