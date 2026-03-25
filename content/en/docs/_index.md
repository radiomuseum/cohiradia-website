---
title: Technology
linkTitle: Technology
---

COHIRADIA is made possible by the recording and playback of digitized high-frequency signals using software-defined radios (SDRs). The use of a uniform data format guarantees interchangeability between different platforms.

For playback, the following elements are basically required:

* a control computer (can also be a small single board computer like a Raspberry Pi)
* a signal converter ([Example](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=1352,1420)) 
* a coupling device ([Example](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=1420,1480)) 
* suitable software ([Example](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_deutsch_v2AbspannJazz.mp4#t=1490,1562)) 
* an archive with digitized broadband AM signals

For each of these elements, there are several possible implementation options, depending on requirements and budget. While the software is written by the COHIRADIA team itself and is fundamentally open-source, commercial products are used for part of the hardware (especially computer and signal converter). Another part of the hardware (e.g., the coupling devices) can be manufactured by users with technical/electronic skills. Figure 1 gives a schematic overview including some currently tested components.

{{% imgproc blockbild-buildingblocks_en_v1 Fit "1200x1000 webp" %}}
*Figure 1:* Schematic overview of the required elements with exemplary illustration of currently used components. The data archive is not shown; it is usually located on a local storage medium on the control computer.
{{% /imgproc %}}

If desired, broadband recording of AM signals directly from an antenna is relatively easy with several commercial SDRs. However, playback requires SDRs with a transmit output or suitable fast digital-to-analog converters with corresponding firmware support. 


Then possibly an image of the signal flow plan or also only on 'Detailed information'