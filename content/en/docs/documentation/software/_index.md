---
title: Software
linkTitle: Software
date: 2026-01-01
weight: 1
description: >
  Description of all software tools provided by Cohiradia.
---

## General

Two equivalent, officially provided programs are available for COHIRADIA on the RM, complementing each other in their purpose:

* **[COHIWizard](#cohiwizard):** the comprehensive software for PC (Windows and Linux) and Raspberry Pi 5. Besides playback of the broadband recordings, it offers numerous tools, e.g. for viewing, annotating, resampling and synthesizing recordings. It supports the STEMLAB, OSMO fl2k and ADALM2000 signal converters.
* **[COHI-Player](#cohi-player):** the lean playback software that needs no manual interaction, particularly for stand-alone systems with the Raspberry Pi 4/5 (but also for PCs). It automatically plays IQ recordings after switch-on and can additionally output internet radio streams as AM carriers or mix them into IQ recordings. It supports the STEMLAB and OSMO fl2k signal converters.

The [installation guide](/en/docs/getting_started/installation/) shows which combination of computer, signal converter and software suits you.

<a id="cohiwizard"></a>

## COHIWizard

The COHIWizard enables playback of broadband recordings hosted in the archive on analog radios, but also provides several useful tools. Currently, these are:
* Viewer for inspecting spectra
* Annotator for commenting on your own recordings
* Resampling of recordings to sampling rates supported by the STEMLAB125-14
* Wav header editor for editing or creating wav headers afterward
* Synthesizer for creating your own AM bands (modulation of any number of carriers with audio content of your choice)

The COHIWizard is available for both [Windows](#windows) and [Linux](#linux). An executable version (exe) is available for Windows. In addition, the COHIWizard is freely available as open Python source code on [Github](https://github.com/hermy-sf/COHIWizard). For LINUX, currently only the Python version is available.

If you want to run the COHIWizard under Python, you can find the installation instructions on the GITHUB repository in the [README file](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

**The user manual of the current version** can be [downloaded here](https://github.com/hermy-sf/COHIWizard/blob/cohiwizard_v2.2/documentation/UserManual_COHIWizard_v2.2_en.pdf). It may happen that your browser doesn't display the pdf correctly, but you can still download the file from the GITHub repository.

If you want to access the latest version still under development, please refer to the [Experimental Version](#experimentelleV) section.

Bug reports for version 2.2.x are welcome.


<a id="windows"></a>

### Windows 10/11
The exe version can be downloaded as a zip file and also includes a user manual.

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_V2.1.1_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v2.2.5b.zip)

<a id="linux"></a>

### LINUX
The Python version was implemented under Debian 12 and 13 in Python. For installation, please clone the repository from [Github](https://github.com/hermy-sf/COHIWizard) and follow the instructions in the [README file](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).


<a id="experimentelleV"></a>

### Experimental Versions

If you use a local GIT and the source codes, you can also access the development branch [cohiwizard_v2.2](https://github.com/hermy-sf/COHIWizard/tree/cohiwizard_v2.2). However, it is experimental and constantly changing. Code loaded from there may show unexpected behavior and is therefore not officially recommended.

I am grateful for [reports](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html) and bug reports, as they help to quickly eliminate problems.

### Previous Versions

Those who already know previous versions of the current COHIWizard and may have installed them will find [in the software archive](alte-versionen.html) old versions right up to the RFCorder, which was the first simple playback software created for COHIRADIA. All of these previous versions should be considered outdated and are no longer maintained.


### Hardware Support

The player part of the COHIWizard is equipped with a device driver system. This makes it possible to use different hardware products suitable for COHIRADIA for generating the analog antenna signals.

So far, three device drivers have been implemented:

1. 'STEMLAB125-14': This is the generic driver for the STEMLAB125-14 from Red Pitaya, for which the COHIWizard was originally written. It enables playback and recording via a TCP connection (LAN interface). With 14-bit resolution and 125 MSamples/s, this solution offers very high data and signal quality for any AM bands up to a maximum of 60 MHz and is by far the best tested of all drivers.

1. 'fl2k-stream': This is a [USB to VGA adapter](https://osmocom.org/projects/osmo-fl2k/wiki) used by various user groups as a fast 8-bit DAC and has also been used in some high-frequency projects (see [fl2k-COHIRADIA project](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&pageNo=1)). With only 8-bit resolution, this very inexpensive device is of course not a full replacement for the STEMLAB, but it is quite sufficient for many standard playback applications, as [examples](https://youtu.be/4jC2XtWUFI8) show. **ATTENTION**: Only adapters with the Fresco Logic FL2000 chip are suitable; please note the (also no longer quite current) information on the [Osmocom Wiki](https://osmocom.org/projects/osmo-fl2k/wiki), since this chip is no longer manufactured and therefore increasingly adapters with other chips are being sold. Please keep this in mind when purchasing the adapter, otherwise the result will be negative!

1. ADALM2000: This driver allows playback of IQ files with upper band limit frequencies up to 2.5 MHz on the [ADALM2000](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm2000.html). This is a cheaper module compared to the STEMLAB125-14, USB-powered with 2 ADC and 2 DAC channels at 12-bit resolution each, as well as a GPIO port. It can be operated as an oscilloscope, function generator, or logic analyzer, but also allows playback of COHIRADIA IQ files. However, there are limitations: Due to the use of USB2.0, the upper limit frequency is limited to about 2500 kHz. This is sufficient for LW and MW, but only allows playback of SW recordings with a trick: By setting an appropriate value in the 'LO-Offset' field (e.g., -4000 kHz for the 49m band), the signal can be downmixed into the medium wave band of the radio and listened to. This driver has not yet been extensively tested and must therefore still be classified as a beta version. Initial tests showed usable playback for MW and LW with better dynamics than the fl2k. However, slight noise occurs with certain recordings, possibly caused by poorer filtering/interpolation than with the STEMLAB.

Both (2) and (3) score with significantly lower costs than a STEMLAB, but require significantly more computing power on the PC, since they do not have an FPGA for the necessary recoding of the complex baseband data like the STEMLAB. The ADALM2000 and the fl2k are therefore not equivalent alternatives to the STEMLAB, whose performance remains unrivaled.

<a id="cohi-player"></a>

## COHI-Player

The COHI-Player by Claus Peter Gallenmiller is a lean playback software that turns a Raspberry Pi or PC into a small "broadcast station" for vintage radios. It needs no manual interaction: after start-up it automatically plays all broadband IQ recordings stored on a USB stick or in an internal directory. This makes it particularly suitable for collections, exhibitions and museums. The STEMLAB (Red Pitaya) and the OSMO fl2k dongle are supported as signal converters.

### Operating modes

* **COHI-Player:** playback of broadband IQ recordings (wav files), e.g. historical recordings of the complete medium wave band from the COHIRADIA archive.
* **COHI-Stream:** current **internet radio streams** (MP3/AAC/M3U) are output simultaneously as AM carriers on freely selectable frequencies – each station with its own carrier frequency and audio bandwidth. Local audio files can also be used as a source via M3U playlists. An example list with 31 internet radio stations (many of them with music of the 1920s–1960s) is included, and the station list can be edited directly in the program.
* **COHI-Player+Stream:** a combination of both – internet radio streams (or local audio files via M3U playlists) are **mixed into** a static IQ recording as additional carriers.

Internet radio streams require an internet connection; a wired LAN connection is strongly recommended to avoid dropouts in the sound.

### Platforms and performance

All three operating modes are available under Linux and Raspberry Pi OS. Under Windows only the COHI-Player mode (playback of IQ recordings) is possible, because the C++ tools required for the streams are not provided for Windows.

According to the user manual, the following approximate limits apply on the Raspberry Pi (estimates, depending on data rate and stability of the streams):

| Operating mode | Raspberry Pi 4 | Raspberry Pi 5 |
|---|---|---|
| COHI-Player with STEMLAB or fl2k | ✔ | ✔ |
| COHI-Stream with STEMLAB | < 25 streams | > 50 streams |
| COHI-Stream with fl2k | < 14 streams | > 40 streams |
| COHI-Player+Stream with STEMLAB | IQ recording + < 25 streams | IQ recording + > 50 streams |
| COHI-Player+Stream with fl2k | not possible | IQ recording + > 40 streams |

On PCs, performance depends heavily on the installed CPU.

### Important notes

* The COHI-Player only finds recordings whose file name ends with **`_0.wav`** (e.g. `MW_Berlin_1936_0.wav`). Subdirectories are searched as well, and follow-up files (`_1.wav`, `_2.wav`, …) are played automatically.
* The output delivers a real RF signal in the medium wave band. Connect it to the radio only by cable via a [coupling device](/en/docs/getting_started/koppelgeraet/) with an insulating transformer, and observe the regulations in your country.

### Source code, user manual and installation

The source code is freely available on GitHub in the repository [COHI-Player-Universal](https://github.com/CPG-Archive/COHI-Player-Universal). The complete operating and configuration instructions can be found in the [README file](https://github.com/CPG-Archive/COHI-Player-Universal/blob/master/README.md). Pre-configured images are available for the Raspberry Pi 4 and 5; the step-by-step instructions can be found in the [installation guide](/en/docs/getting_started/installation/).

<!-- comment -->