---
title: Selection Guide
linkTitle: Selection Guide
date: 2026-02-04
weight: 1
nav_exclude: true
description: >
  Selection guide with intelligent selection
---

## Basics

This page is intended to help you quickly assemble the components suitable for your needs. The configurator embedded below allows you to determine, depending on the desired control computer and for a specific price category, which signal converter is available for the desired requirements in terms of SNR and playable AM bands.

The listed signal converters are all equipped with a transmit output and fast digital-to-analog converters as well as corresponding firmware support. However, broadband recording of AM signals directly from an antenna is not supported by all devices. There are several commercial SDRs available for this purpose, although they often lack a transmit output. These are therefore not covered in this overview.

Note: When a PC is used as the control computer, it is not included in the price estimate, as it is usually already available. If this is not the case, its acquisition costs should be added. If you want a stand-alone version that does not require a PC, a single-board computer, currently the Raspberry Pi, is used.

The SNR specifications refer to the maximum theoretically achievable value when calculating with 29 dominant, equally strong but completely decorrelated carriers in the medium wave band. For the exact definition, see [SNR Definition](snr_definition.md). Measured data can be found in the Test Reports section under [SNR Measurements](/en/docs/documentation/testberichte/snr_messungen/). In general, 40dB can be assumed to be sufficient for most applications on MW and LW.

## Configurator

Select your hardware requirements to get the appropriate selection:

 {{< selection-guide basepath="/en/docs/getting_started/auswahlhilfe/" >}}


## Available Combinations

The following table shows an overview of the available combinations:

| Control Computer | Signal Converter |
|------------------|------------------|
| PC               | STEMLAB          |
| PC               | fl2k Dongle      | 
| PC               | ADALM2000        |
| Raspberry Pi     | STEMLAB          | 
| Raspberry Pi     | fl2k Dongle      |

**Note:** These combinations are currently available. Additional combinations will follow as new options become known.