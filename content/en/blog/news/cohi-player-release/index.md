---
date: 2026-11-01
title: The new COHI-Player turns the Raspberry Pi into a broadband medium wave broadcast station
linkTitle: New COHI-Player
description: >
  The new COHI-Player by Claus Peter Gallenmiller is here: ready-made images for Raspberry Pi 4 and 5, historical recordings and current internet radio streams on freely selectable medium wave frequencies.
author: Hermann Scharfetter
---

You turn the tuning knob of your vintage radio, and one station after another comes up on the dial, just like in its day. That is exactly what the new **COHI-Player** by Claus Peter Gallenmiller, the successor to the COHI-Player mini, makes possible: it turns a Raspberry Pi into a small "broadcast station" for vintage radios.

<figure>
  <img src="/images/COHIPlyer_Teaser1_CPG_image021.png" alt="Raspberry Pi with touch display running the COHI-Player in front of a vintage Telefunken 8001W radio" style="width: 380px; max-width: 100%; height: auto;"/>
  <figcaption><em>The COHI-Player on the Raspberry Pi in front of a Telefunken 8001W. Photo: Claus Peter Gallenmiller</em></figcaption>
</figure>

### Three operating modes

* **COHI-Player:** replays recordings of complete medium wave bands, for example from the [COHIRADIA archive](/en/archiv/).
* **COHI-Stream:** broadcasts current internet radio streams simultaneously on several freely selectable carrier frequencies. A sample list of 31 stations is included, many of them playing music from the 1920s to the 1960s. Your own audio files can also be added via M3U playlists.
* **COHI-Player+Stream:** mixes internet radio streams as additional carriers into a historical band recording.

### Switch on and listen

The COHI-Player needs no operation to start playing: after startup it automatically plays all recordings stored on a USB stick or in an internal directory. This also makes it ideal for supplying antenna signals to historic receivers in large collections and museums.

### Ready-made images for the Raspberry Pi

Preconfigured images are available for the Raspberry Pi 4 and 5. Simply write one to an SD card, and the system is ready for operation. New recordings and program updates can be conveniently transferred over the network.

The RF signal is generated either by a STEMLAB (Red Pitaya) or by an inexpensive fl2k USB-to-VGA dongle. A Raspberry Pi 4 is sufficient for the COHI-Player. For many simultaneous streams the Raspberry Pi 5 is recommended, which according to the user manual handles more than 40 live streams (fl2k) or more than 50 (STEMLAB).

### Getting started

* [Installation guide](/en/docs/getting_started/installation/): choose your combination of computer and signal converter.
* [Documentation → Software](/en/docs/documentation/software/#cohi-player): an overview of all operating modes and performance data.
* [Source code and user manual on GitHub](https://github.com/CPG-Archive/COHI-Player-Universal): the COHI-Player is licensed under GPL-3.0.

**Important:** The COHI-Player generates a real RF signal in the medium wave band. Transmitting without a licence is illegal in most countries and can disturb other radio services. Therefore connect the output to the radio's antenna input by cable and insulating transformer, or use a coupling loop with negligible radiation. Further information can be found under [Coupling device](/en/docs/getting_started/koppelgeraet/).
