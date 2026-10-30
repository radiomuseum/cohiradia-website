---
title: "fl2k_raspi"
nav_exclude: true
_build:
  list: never
  render: always
---

## Connecting the fl2k dongle

Once the SD card is inserted in the Raspberry Pi, connect the peripherals. **Plug the OSMO fl2k dongle into a USB 3.0 port (blue) of the Raspberry Pi.** No separate driver installation is needed; the required software (osmo-fl2k) is already included in the prepared image.

Note: the COHI-Player+Stream mode is only possible with the fl2k dongle on the Raspberry Pi 5 (for details see [Documentation → Software](/en/docs/documentation/software/#cohi-player)).

**ATTENTION**: Only adapters with the Fresco Logic FL2000 chip are suitable; please note the (also no longer quite current) information on the [Osmocom Wiki](https://osmocom.org/projects/osmo-fl2k/wiki), since this chip is no longer manufactured and therefore increasingly adapters with other chips are being sold. Please keep this in mind when purchasing the adapter, otherwise the result will be negative!
