---
title: Basics Report
linkTitle: Basics Report
date: 2026-01-01
weight: 3
nav_exclude: false
description: >
  This document contains all technical basics of COHIRADIA in much detail. Also some detailed descriptions of hardware are included. 
---

All important technical details for the implementation of COHIRADIA were summarized in the [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf). The important points are:

* Organization of COHIRADIA
* Structure and rules for building the archive
* Analyses of signal quality
* Technical basics of the signal converters
* Required additional hardware (incl. DIY instructions)
* Basics for software design
* References
* Data structures

It should be noted that this report represents the knowledge of the COHIRADIA team in 2023 and is therefore no longer entirely up to date in some points. Two relevant points should therefore be explicitly mentioned:

(1) At that time, it was assumed that 8-bit signal converters would not be suitable for COHIRADIA. While this still applies for recordings (except in the case of excessive oversampling), it has been shown for playback that, e.g., the OSMO-fl2k system does indeed allow satisfactory results, although the SNR naturally does not match that of a converter with 12 or 14 bits. However, this does not significantly disturb many recordings and playback with most broadcast receivers on LW and MW.

(2) Construction of the coupling transformer: Here, the 2023 report still mentions windings with enameled wire (CuL). **For the sake of sufficient safety when operating old tube radios, the use of enameled wires is now strongly discouraged, as they can lead to dangerous galvanic coupling via the often conductive toroidal cores in case of damage.** We therefore now only recommend the construction method described in the ['Coupling Devices']({{< relref "/docs/getting_started/koppelgeraet/_index.md" >}}) section of this webpage. 



