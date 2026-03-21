---
title: Actually < 100€, PC (not included in price) + OSMO fl2k Dongle
date: 2026-02-04
weight: 10
_build:
  list: never
  render: always
description: >
    Selection for < 100€ (excluding PC), max. SNR with 29 equally strong carriers 40dB, bandwidth limited to LW, MW and 49m SW
---

**This option is actually available for < 100€ (excl. PC):**

**Advantages:**

* low cost
* uncomplicated setup
* relatively compact (depending on PC)

**Disadvantages:**

* only 8 bit resolution, therefore SNR limited, but sufficient for most LW and MW bands as well as (mostly) SW 49m
* data rate limited by USB port; max. usable frequency is limited depending on operating system, for details see ['here']({{< relref "/docs/documentation/Testberichte/OSMO_fl2k_Frequenzabdeckung/_index.md" >}})
* higher computing power required on the PC than with FPGA-based systems
* only USB/VGA dongles with Fresco chipset supported, availability limited due to end of production, future uncertain.

**Software support:**

COHIWizard, COHI-Mini-Player (projected) and solutions from other communities such as radio-bastler.de via GNU Radio support

For technical evaluation see ['SNR Measurements']({{< relref "/docs/documentation/Testberichte/snr_messungen/_index.md" >}}) and ['OSMO fl2k Frequency Coverage']({{< relref "/docs/documentation/Testberichte/OSMO_fl2k_Frequenzabdeckung/_index.md" >}})
