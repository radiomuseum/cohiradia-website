---
title: Cohiradia Software
---


## RFCorder Version 2.0 (November 2023)

<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder2_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip)

RFCorder v2.0 is used to play back broadband recordings on analog radio receivers using the STEMLAB125-14. The description is included in the downloadable zip file. In contrast to the previous version v1.2, this version does not currently allow you to make your own recordings, but there are a number of useful new features:

* In addition to recordings in the raw data format (*.dat) originally used for COHIRADIA, you can now also play back those in wav format. This is useful because all well-known SDRs use this format and therefore all external archives of broadband files contain wav files. Consequently, all new recordings in the archive are now generated exclusively with wav headers. This means that the files can also be played back on the PC with common SDR software such as SDRUno or SDR#. Metadata can be transferred to the RFCorder and displayed much more compactly.
* You can now jump back and forth on the timeline with a scroll bar, making it very easy to find different passages in the recording.
* The current time is displayed correctly, according to the actual time (UTC) at the time of recording. Of course, this only works with wav files, not with *.dat.
* There is a logarithmic signal strength indicator. If the signal is too weak (bar turns yellow), you can use the 'Gain' control to increase the gain within limits (logarithmically).
* The play button is now a 'Play/Pause' button.
* There is an endless play button.
* There is a simple resampler that allows recordings not originating from COHIRADIA to be resampled to one of the sampling rates required for STEMLAB. This significantly increases compatibility with commercial SDR formats.

We recommend that all users who only want to play back files on their radios (not their own recordings) only use this program version, as the old versions will no longer be maintained in the future. A version with recording function is in preparation.

As this is a major change compared to the previous version, it is quite possible that one or two small bugs may still be present. I would be grateful for reporting on such issues [Reports](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html), as this helps to eliminate problems quickly.

## COHIWizard 1.0 (January 2024)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_1.0_resampler_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.0b.zip)


The [COHIWizard](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.0.zip) is a comprehensive program that provides many additional functions in addition to the full functionality of RFCorder2.0. These include:

* a simple spectral analysis window for the band spectra, which enables a quick static evaluation of recordings.
* a resampler that has been greatly expanded compared to RFCorder 2.0 for resampling recordings whose sampling rate is not STEMLAB-compatible. In contrast to RFCorder 2.0, arbitrary sections of the spectrum can be cut out. Additionally entire lists of related wav files can now be resampled at once and split into 2GB sized files.
* an annotation tool that can support the semi-automatic generation of metadata files. This also includes a generator for the yaml files that have to be created on the COHIRADIA server for annotation purposes.

However, the latter feature currently only works for Europe, the USA and New Zealand, as the reference tables for other areas have not yet been integrated. 

## RFCorder Version 1.2 (April 2022)
<!-- comment -->
<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder1.2_Screenshot.png" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/cohiradia_V1.2.zip)

RFCorder v1.2 is the first fully functional software for making broadband recordings using the STEMLAB125-14 and for the analog playback of the signals on connected radio receivers. The only supported file format in this version are raw files in 32-byte complex format with the extension '.dat'. The file names must comply with the old COHIRDIA naming convention (see [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_engl.pdf)) and must therefore also be downloaded from the archive in this format.

The playback of wav files, as used by most SDRs, is only possible to a limited extent, namely if they are renamed accordingly (dat instead of wav and the name is rewritten in accordance with the naming convention) and if the sampling rate corresponds to one of the rates supported by the STEMLAB. Formats other than 2 channels/int16 are not supported.

A special feature is the possibility to shift the frequency band in the spectrum during playback, e.g. to play a long wave band in the medium wave range of a radio. To do this, an offset to the center frequency of the band must be specified.

When recording, the program allows you to start a recording automatically using a timer. 

