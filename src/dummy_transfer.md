The official software provided by RM for COHIRADIA is COHIWizard. It allows you to play the broadband recordings hosted in the archive on analog radios, but also provides a number of useful tools. Currently, these are:

    Viewer for inspecting spectra
    Annotator for commenting on your own recordings
    Resampling of recordings to sampling rates supported by STEMLAB125-14
    Wav header editor for post-editing or creating wav headers
    Synthesizer for creating your own AM bands (modulation of any number of carriers with audio content of your choice)

COHIWizard is available for both Windows and Linux. An executable version (exe) is available for Windows. In addition, COHIWizard is freely available as open Python source code on Github. Currently, only the Python version is available for Linux.

If you want to run COHIWizard under Python, you will find the installation instructions in the README file on the GITHUB repository.

If you want to access the latest version, which is still under development, please refer to the Experimental Version section.

Bug reports for version 2.2.x are welcome.

# Hardware Support

The player part of COHIWizard is equipped with a device driver system. This makes it possible to use different hardware products suitable for COHIRADIA to generate analog antenna signals. 

Three device drivers have been implemented so far:

(1) ‘STEMLAB125-14’: This is the generic driver for the STEMLAB125-14 from Red Pitaya, for which COHIWizard was originally written. It enables playback and recording via a TCP connection (LAN interface). With 14-bit resolution and 125 MSamples/s, this solution offers very high data and signal quality for any AM bands up to a maximum of 60 MHz and has been the best tested of all drivers to date.

(2) ‘fl2k-stream’: This is a  [USB to VGA adapter](https://osmocom.org/projects/osmo-fl2k/wiki), which is used by various user groups as a fast 8-bit DAC and has also been used in some high-frequency projects (see [fl2k-COHIRADIA project](https://www.radio-bastler.de/ forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&pageNo=1)). With its resolution of only 8 bits, this very inexpensive device is of course not a full replacement for the STEMLAB, but it is sufficient for many standard playback applications, as [examples](https://youtu.be/4jC2XtWUFI8) show.

(3) ADALM2000: This driver allows playback of IQ files with upper bandwidth frequencies up to 2.5 MHz on the [ADALM2000](https://www.analog.com/en/resources/evaluation-hardware-and-software/evaluation-boards-kits/adalm2000.html). Compared to the STEMLAB125-14, this is a cost-effective, USB-powered module with 2 ADC and 2 DAC channels, each with 12-bit resolution, and a GPIO port. It can be used as an oscilloscope, function generator, or logic analyzer, but also allows the playback of COHIRADIA IQ files. However, there are limitations: Due to the use of USB 2.0, the upper frequency limit is limited to approximately 2500 kHz. This is sufficient for LW and MW, but allows playback of KW recordings only with a trick: By setting a suitable value in the ‘LO-Offset’ field (e.g., -4000kHz for the 49m band), the signal can be downmixed to the radio's medium wave band and listened to. This driver has not yet been extensively tested and must therefore still be classified as a beta version. Initial tests showed usable playback for MW and LW with better dynamics than the fl2k. However, slight noise occurs with certain recordings, which may be due to poorer filtering/interpolation than with the STEMLAB.

Although both (2) and (3) score points for being significantly less expensive than a STEMLAB, they require considerably more computing power on the PC, as unlike the STEMLAB, they do not have an FPGA for the necessary recoding of the complex baseband data. The ADALM2000 and fl2k are therefore not equivalent alternatives to the STEMLAB, whose performance remains unmatched. 
