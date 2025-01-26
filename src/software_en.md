---
title: Cohiradia Software
---
# Selection guide:

Essentially there are two different types of software available, a simple player for the most basic needs (playback of recordings and basic resampling) and a more advanced universal tool for playback, recording and additional features like inspecting the spectra, annotation of own recording and advanced resampling. If you just need a simple, playback tool which is easy to use, then opt for the <strong>RFCorder</strong>. If you want to have full functionality with many useful features for the post-processing of recordings, then opt for the <strong>COHIWizard</strong>. The COHIWizard includes all features of the RFCorder and is more frequently updated. 
An executable version (exe) is available for both versions under Windows. The COHIWizard is also available from v1.2 as open Python source code on [Github](https://github.com/hermy-sf/COHIWizard) for both [Windows](#windows) and [Linux](#linux). If you want to run the COHIWizard under Python, you can find the installation instructions on the GITHUB repository in the [README file](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).

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

I would be grateful for reporting on such issues [Reports](https://www.radiomuseum.org/forum/software_fuer_cohiradia_details_und_problemloesungen.html), as this helps to eliminate problems quickly.</p>

## COHIWizard 1.2.9 (June 2024)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard1.2.9_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.2.9c.zip)

<p style='text-align: justify;'>  The COHIWizard is a comprehensive program that provides many additional functions in addition to the full functionality of RFCorder2.0. These include

* the ability to create your own recordings, including the automatic start of a recording using a timer.
* a simple spectral analysis window for the band spectra, which enables a quick static assessment of recordings.
* a resampler that has been greatly expanded compared to RFCorder 2.0 for recoding recordings whose sampling rate is not STEMLAB-compatible. In contrast to RFCorder 2.0, any area of the spectrum can be cut out. Even entire series of related wav files can now be resampled at once.
* An annotation tool that can support the semi-automatic generation of metadata files. This also includes a generator for the yaml files that have to be created on the COHIRADIA server for annotation purposes.

However, the latter feature currently only works for Europe, the USA and New Zealand, as the reference tables for other zones have not yet been integrated.
</p>

# Previous versions

## COHIWizard 1.0 (January 2024)

<img src="https://cohiradia.radiomuseum.org/download/software/COHIWizard_1.0_resampler_screenshot.PNG" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/COHIWizard_v1.0b.zip)


<p style='text-align: justify;'>The COHIWizard is a comprehensive program that provides many additional functions in addition to the full functionality of RFCorder2.0. These include:

* a simple spectral analysis window for the band spectra, which enables a quick static evaluation of recordings.
* a resampler that has been greatly expanded compared to RFCorder 2.0 for resampling recordings whose sampling rate is not STEMLAB-compatible. In contrast to RFCorder 2.0, arbitrary sections of the spectrum can be cut out. Additionally entire lists of related wav files can now be resampled at once and split into 2GB sized files.
* an annotation tool that can support the semi-automatic generation of metadata files. This also includes a generator for the yaml files that have to be created on the COHIRADIA server for annotation purposes.

However, the latter feature currently only works for Europe, the USA and New Zealand, as the reference tables for other areas have not yet been integrated.</p>

## RFCorder Version 1.2 (April 2022)
<!-- comment -->
<img src="https://cohiradia.radiomuseum.org/download/software/RFCorder1.2_Screenshot.png" width="400" height="200" /> [<img src="https://cohiradia.radiomuseum.org/download/software/Button_Download.PNG" width="200" height="70" />](https://cohiradia.radiomuseum.org/download/software/cohiradia_V1.2.zip)

<a style='text-align: justify;'>RFCorder v1.2 is the first fully functional software for making broadband recordings using the STEMLAB125-14 and for the analog playback of the signals on connected radio receivers. The only supported file format in this version are raw files in 32-byte complex format with the extension '.dat'. The file names must comply with the old COHIRDIA naming convention (see [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_engl.pdf)) and must therefore also be downloaded from the archive in this format.

The playback of wav files, as used by most SDRs, is only possible to a limited extent, namely if they are renamed accordingly (dat instead of wav and the name is rewritten in accordance with the naming convention) and if the sampling rate corresponds to one of the rates supported by the STEMLAB. Formats other than 2 channels/int16 are not supported.

A special feature is the possibility to shift the frequency band in the spectrum during playback, e.g. to play a long wave band in the medium wave range of a radio. To do this, an offset to the center frequency of the band must be specified.

When recording, the program allows you to start a recording automatically using a timer.</a>

# LINUX
<a id="linux"></a>
The Python version was successfully started under Debian 10, but has not yet been tested extensively - the player was able to successfully play back RF signals and the synthesizer was able to successfully create correct SDR wav files. An annotation with the annotator was also carried out on a recording as an example. More extensive tests will be carried out in the future.

For the installation, please clone the repository from [Github](https://github.com/hermy-sf/COHIWizard). More detailed instructions can be found in the [README file](https://github.com/hermy-sf/COHIWizard/blob/main/README.md).
