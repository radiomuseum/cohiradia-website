---
title: Getting Started
weight: 1
sidebar_root_for: self
menu:
  main:
    weight: 15
---
COHIRADIA is made possible by the recording and playback of digitized high-frequency signals using software-defined radios (SDRs). The use of a uniform data format guarantees interchangeability between different platforms.

For playback, the following elements are basically required:

* a control computer (can also be a small single board computer like a Raspberry Pi)
* a signal converter ([Example](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_TimeMachine_English_YT.mp4#t=1505,1570)) 
* a coupling device ([Example](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_TimeMachine_English_YT.mp4#t=1535,1617)) 
* suitable software ([Example](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_TimeMachine_English_YT.mp4#t=1618,1725)) 
* an [archive](../../archiv/index.html) with digitized broadband AM signals 

For each of these elements, there are several possible implementation options, depending on requirements and budget. We would like to explicitly point out here that COHIRADIA does not sell any products; rather, the platform merely provides information, instructions, and open-source software. The latter is written by the COHIRADIA team itself, but there are also alternatives from other SDR-focused groups (see the links at the end of this chapter). For part of the hardware (especially computer and signal converter) commercial products are used. Another part of the hardware (e.g., the coupling devices) can be manufactured by users with technical/electronic skills. Figure 1 gives a schematic overview including some currently tested components.

**Decision Aid:** To quickly arrive at a decision for a system that suits you, please use the 'Selection Guide' in the navigation bar on the left. More detailed descriptions of the elements can be found under 'Coupling Device', 'Signal Converter', and 'Computer'.


{{% imgproc blockbild-buildingblocks_en_v1 Fit "1200x1000 webp" %}}
*Figure 1:* Schematic overview of the required elements with exemplary illustration of currently used components. The data archive is not shown; it is usually located on a local storage medium on the control computer.
{{% /imgproc %}}

If desired, broadband recording of AM signals directly from an antenna is relatively easy with several commercial SDRs. However, playback requires SDRs with a transmit output or suitable fast digital-to-analog converters with corresponding firmware support. 

### Interesting Alternative Software Projects:

Software other than COHIWizard can also be used to play back COHIRADIA recordings. For those working on Linux, the very interesting code in the GITHUB repository [radiolab81](https://github.com/radiolab81) is a good option. In particular, the [COHIRADIA Streamer](https://github.com/radiolab81/COHIRADIAStreamer) and [AMWavSynth](https://github.com/radiolab81/AMWaveSynth) are worth mentioning here. However, users should have some IT expertise to use these tools effectively. Meanwhile, new device drivers based on individual code snippets from this repository have also been integrated into experimental versions of COHIWizard.

### Interesting Alternative Hardware Solutions

[radiolab81](https://github.com/radiolab81) also offers some good ideas for alternative hardware, some of which is very inexpensive but requires a bit of DIY skill. Notable examples include [parlioSDR](https://github.com/radiolab81/parlioSDR) and [smisdr](https://github.com/radiolab81/smisdr).
