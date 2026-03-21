---
title: PC (not included in price) + OSMO fl2k Dongle
date: 2026-02-04
weight: 10
_build:
  list: never
  render: always
description: >
    Selection for < 100€ (excluding PC), max. SNR with 29 equally strong carriers 40dB, bandwidth limited to LW, MW
---

**Alternative options at this performance level:**

currently none

**Advantages:**

* low cost
* uncomplicated setup
* relatively compact (depending on PC)

**Disadvantages:**

* only 8 bit resolution, therefore SNR limited, but sufficient for most LW and MW bands
* data rate limited by USB port; max. usable frequency is limited depending on operating system, for details see ['here']({{< relref "/docs/documentation/Testberichte/OSMO_fl2k_Frequenzabdeckung/_index.md" >}})
* higher computing power required on the PC than with FPGA-based systems
* only USB/VGA dongles with Fresco chipset supported, availability limited due to end of production, future uncertain.

**Software support:**

COHIWizard, COHI-Mini-Player (projected) and solutions from other communities such as radio-bastler.de via GNU Radio support


**Audio sample for test listening:**

Band scan through a synthetic spectrum with 29 carriers, recorded by C.P. Gallenmiller with a Telefunken 8001W from 1939.

<audio controls>
  <source src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/Bandscans/Bandscan AM2 FL2K + COHIWizard_c.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>


**Technical evaluation**:
For reports see ['SNR Measurements']({{< relref "/docs/documentation/Testberichte/snr_messungen/_index.md" >}}) and ['OSMO fl2k Frequency Coverage']({{< relref "/docs/documentation/Testberichte/OSMO_fl2k_Frequenzabdeckung/_index.md" >}})

