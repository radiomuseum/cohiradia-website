---
title: Signal Converter
linkTitle: Signal Converter
date: 2026-01-01
weight: 10
description: >
  This is the 'SDR', i.e., currently STEMLAB, fl2k, and ADALM2000.
---

## General

The signal converter has the task of receiving a digital data stream from the control computer and converting it into the analog antenna signal for the receiver. Roughly simplified, this can be seen as a digital-to-analog converter, but most usable devices are more complex. Due to the device driver concept of the official COHIRADIA software, it is fundamentally possible to use different hardware products for signal conversion.

## Supported Hardware

So far, three devices have been tested and software drivers have been integrated for them:

1. [STEMLAB125-14 from Red Pitaya](https://redpitaya.com/stemlab-125-14-gen2/?srsltid=AfmBOoqpGfok05eVHWlfTpikYPgMxxi98fzhOZlGDNTpoSf0ceoIQGoq): This is the generic 'workhorse' for which the COHIWizard was originally written. It enables playback and recording via a TCP connection (LAN interface). With 14-bit resolution and 125 MSamples/s, this solution offers very high data and signal quality for any AM bands up to a maximum of 60 MHz and is by far the best tested of all products. However, at around €500, this device is comparatively expensive. It can also be used multifunctionally as a small signal generation and analysis platform (signal generator, oscilloscope, simple network analyzer) up to 60 MHz in the laboratory.

1. [OSMO fl2k](https://osmocom.org/projects/osmo-fl2k/wiki): This is a very inexpensive (about 25-30 €) USB to VGA adapter that is used by various user groups as a fast 8-bit DAC and has also been employed in some high-frequency projects (see [fl2k-COHIRADIA project](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&pageNo=1)). With only 8-bit resolution, this cheap device is of course not a full replacement for the STEMLAB, but it is quite sufficient for many standard playback applications, as [examples](https://youtu.be/4jC2XtWUFI8) show. **ATTENTION**: Only adapters with the Fresco Logic FL2000 chip are suitable; please note the (also no longer quite current) information on the [Osmocom Wiki](https://osmocom.org/projects/osmo-fl2k/wiki), since this chip is no longer manufactured and therefore increasingly adapters with other chips are being sold. Please keep this in mind when purchasing the adapter, otherwise the result will be negative!

1. [ADALM2000](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm2000.html): This hardware allows playback of COHIRADIA IQ files with upper band limit frequencies up to 2.5 MHz. The ADALM2000 is a cheaper module (about 200-250 €) compared to the STEMLAB125-14, USB-powered with 2 ADC and 2 DAC channels at 12-bit resolution each, as well as a GPIO port. Like the STEMLAB, it can alternatively be operated as a small PC-coupled oscilloscope, function generator, or logic analyzer. However, there are limitations: Due to the use of USB2.0, the upper limit frequency is limited to about 2500 kHz. This is sufficient for LW and MW, but only allows playback of SW recordings with a trick: By setting an appropriate value in the 'LO-Offset' field (e.g., -4000 kHz for the 49m band), the signal can be downmixed into the medium wave band of the radio and listened to. This driver has not yet been extensively tested and must therefore still be classified as a beta version. Initial tests showed usable playback for MW and LW with better dynamics than the fl2k. However, slight noise occurs with certain recordings, possibly caused by poorer filtering/interpolation than with the STEMLAB.

Both (2) and (3) require significantly more computing power on the PC, since they do not have an FPGA for the necessary recoding of the complex baseband data like the STEMLAB. The ADALM2000 and the fl2k are therefore not equivalent alternatives to the STEMLAB, whose performance remains unrivaled.