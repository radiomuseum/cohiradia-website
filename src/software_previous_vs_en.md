---
title: Cohiradia Software
---
# Selection guide:

Essentially there are two different types of software available, a simple player for the most basic needs (playback of recordings and basic resampling) and a more advanced universal tool for playback, recording and additional features like inspecting the spectra, annotation of own recording and advanced resampling. If you just need a simple, playback tool which is easy to use, then opt for the <strong>RFCorder</strong>. If you want to have full functionality with many useful features for the post-processing of recordings, then opt for the <strong>COHIWizard</strong>. The COHIWizard includes all features of the RFCorder and is more frequently updated. 
An executable version (exe) is available for both versions under Windows. The COHIWizard is also available from v1.2 as open Python source code on [Github](https://github.com/hermy-sf/COHIWizard) for both [Windows](#windows) and [Linux](#linux). If you want to run the COHIWizard under Python, you can find the installation instructions on the GITHUB repository in the [README file](https://github.com/hermy-sf/COHIWizard/blob/main/README.md). If you are interested in trying out the newest version (Beta) please jump to   [Newest experimental Version](#experimentelleV).

<a id="windows"></a>
# Windows 10/11
## RFCorder Version 2.0 (November 2023)

<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder2_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip)

<p style='text-align: justify;'>RFCorder v2.0 is used to play back broadband recordings on analog radio receivers using the STEMLAB125-14. The description is included in the downloadable zip file. Typical features are:

* Recordings can be read and played back in IQ raw data format (*.dat) and in the wav format used by most well-known SDRs.
* You can use a scroll bar to jump back and forth on the timeline, making it very easy to find different points in the recording.
* The current time is displayed correctly, according to the actual time (UTC) at the time of recording. Of course, this only works with wav files, not with *.dat files.
* There is a logarithmic signal strength indicator. If the signal is too weak (bar turns yellow), you can use the 'Gain' control to amplify it within limits (logarithmically).
* There is an endless playback button.
* There is a simple resampler that allows you to resample recordings not originating from COHIRADIA to one of the sampling rates required for STEMLAB. This means that all recordings from external archives can also be used.

I would be grateful for [reports on successful use but also bugs](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html), as this helps to eliminate problems quickly.</p>

## COHIWizard 1.2.9 (June 2024)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard1.2.9_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.2.9c.zip)

<p style='text-align: justify;'>  The COHIWizard is a comprehensive program that provides many additional functions in addition to the full functionality of RFCorder2.0. These include

* the ability to create your own recordings, including the automatic start of a recording using a timer.
* a simple spectral analysis window for the band spectra, which enables a quick coarse assessment of recordings.
* a resampler that has been greatly expanded compared to RFCorder 2.0 for resampling recordings whose sampling rate is not STEMLAB-compatible. In contrast to RFCorder 2.0, any section of the spectrum can be cut out. Even entire series of related wav files can now be resampled at once.
* An annotation tool that can support the semi-automatic generation of metadata files. This also includes a generator for the yaml files that have to be created on the COHIRADIA server for annotation purposes.

However, the latter feature currently only works for Europe, the USA and New Zealand, as the reference tables for other zones have not yet been integrated.
</p>

## COHIWizard 1.3.3 (January 2025, first stable version)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_1_3_3_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.3.3.zip)

Besides a few small changes (e.g. a monitor for the currently playing spectrum) this version contains a completely new module: The <strong>synthesizer</strong> which can be activated with a new tab at the right end of the menu bar. This tool enables you to create your own RF bands with individual playlists containing arbitrary audios in either wav- or mp3-format, according to your own taste. In that way one can e.g. generate a medium wave band with music from the 60ies and/or spoken (historic) texts which then can be played back in the same way as one of the original recordings from the archive. An example is given in the [Youtube video](https://www.youtube.com/watch?v=pYD5mz_M_bQ) (in fact the intro section stems from such a synthetic band). A detailed user's manual is contained in the installation zip file. There is a small, not fully updated [video-tutorial](https://cohiradia.radiomuseum.org/download/software/Tutorial_synthesizer_v0.mp4) for an early preliminary version, which does not contain all features but which may still be useful for getting started. This software version has not yet been tested excessively, thus bug-reports are welcome. A small preview of the GUI can be seen here:

<img src="https://cohiradia.radiomuseum.org/download/software/Synthesizer_Screenshot_v0.PNG" width="400" height="200" />


# LINUX
<a id="linux"></a>
The Python version was successfully tested under Debian 12 and 13.

For the installation, please clone the repository from the main branch of [Github](https://github.com/hermy-sf/COHIWizard). More detailed instructions can be found in the [README file](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

If you use a local git, then you can also access the [branch cohiwizard_v2.2](https://github.com/hermy-sf/COHIWizard/blob/cohiwizard_v2.2) which contains the synthesizer. However, this is the current development branch and must thus be considered as experimantal.


<a id="experimentelleV"></a>

# Newest experimental version: COHIWizard 2.2.x

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_V2.1.1_Screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v2.2.0.zip)

Following a revision of the player architecture, version 2 of the COHIWizard is now available. The player part of the COHIWizard is equipped with a device driver system. This makes it possible to select not only the STEMLAB as a recording/playback device, but also alternative hardware. This means that other SDRs that are compatible with the requirements for COHIRADIA can be operated in the future. The synthesiser has also been revised and equipped with a significantly faster modulator based on ffmpeg. This makes it possible to synthesise your own broadband files almost five times faster than before. However, this feature has a slightly worse SNR than the 'slow version' and has therefore been added as an optional beta module for the time being. If the SNR of the new option can be made equivalent to that of the slow mode, it will replace the latter in future releases. Version 2.2.x is currently available for download.

So far two alternative, experimental drivers have been implemented:

(1) “fl2k”: This is a [USB to VGA-Adapter](https://osmocom.org/projects/osmo-fl2k/wiki) that is used by various user groups as a fast 8-bit DAC and has also been used in some radiofrequency projects (see [fl2k-COHIRADIA-Projekt](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&pageNo=1)). With its only 8-bit resolution, this low-cost device is of course not a full replacement for the STEMLAB, but for playback it is sufficiently good for a range of standard applications, as [examples](https://youtu.be/4jC2XtWUFI8) show.

(2) "ADALM2000": This driver allows the playback of IQ files with upper cut-off frequencies up to 2.5 MHz on the [ADALM2000](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm2000.html). This USB-powered module is considerably cheaper than a STEMLAB125-14 and which comes with 2 ADC and 2 DAC channels (12-bit resolution each), and a GPIO port. It can be operated as an oscilloscope, function generator or logic analyser and, together with the new COHIWizard, allows the playback of COHIRADIA IQ files. However, there are limitations: Due to the use of USB2.0, the uppermost allowable signal frequency in the RF-bands is 2500 kHz. This is sufficient for LW and MW while SW recordings can only be played back with a trick: Setting the option 'LO offset' to a suitable value (say -4000 kHz for the 49m band) the signals can be downconverted and played back in the medium wave band of the radio. Initial tests showed usable playback for MW and LW with markedly better dynamic range than the fl2k. However, some recordings come with slight additional noise, possibly due to poorer filtering/interpolation than with the STEMLAB.

Both (1) and (2) require a reasonably powerful PC for recoding the complex baseband data into the data format required for the devices. We therefore recommend neither the ADALM2000 nor the fl2k as real alternatives to STEMLAB, whose performance remains unrivalled due to the outsourcing of computationally intensive operations to the FPGA. However, if you already have an ADALM2000, for example, you can now control it and tap the radio signal at DAC output 1 (W1).

It is planned to develop further drivers in the future, possible targets could be e.g. the [ADALM Pluto](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm-pluto.html).

If you use a local GIT and the source codes, you can already access the branch [cohiwizard_v2.0](https://github.com/hermy-sf/COHIWizard/tree/cohiwizard_v2.2/sources) which is the current development branch for version 2 and must be classified as experimental.

Bug reports for version 2.2.x are welcome due to the not yet very excessive testing. For reports see my CONTACT on the main page.
