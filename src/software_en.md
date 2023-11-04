---
title: Cohiradia Software
---
## RFCoder Version 2.0 (November 2023)
There is now a new version of the RFCorder called [RFCorder_v2](https://cohiradia.radiomuseum.org/download/software/RFCorder_v2_0.zip), which can be downloaded from the software directory. The description is included in the zip file. Like version v1, the program can currently only play recordings, but there are a number of useful new features:

* You can now also play IQ-files in wav-format. This is useful as all external archives of broadband files offer this format. Furthermore, all new recordings in the archive are now generated exclusively with wav headers. This allows the files to be played back on the PC with common SDR software such as SDRUno or SDR# and metadata can be transferred to the RFCorder and displayed much more compactly.
* You can now jump back and forth on the timeline with a scroll bar, making it very easy to find different points in the recording.
* The current time is displayed correctly, according to the actual time (UTC) at the time of recording. Of course, this only works with wav files, not with *.dat files.
* There is a logarithmic signal strength indicator. If the signal is too weak (bar turns yellow), you can use the 'Gain' control to increase the gain within limits (logarithmically).
* The play button is now a 'Play/Pause' button.
* There is an endless play button.
* There is a simple resampler that allows you to resample non-COHIRADIA recordings to one of the sampling rates required for STEMLAB. This significantly increases compatibility with commercial SDR formats.

I recommend all users who only want to play back files on their radios (no own recordings) to install this program version, as the old versions will no longer be maintained in the future. A version with recording function is in preparation.

As this is a major change compared to the previous version, it may well be that there exist still small bugs. I would be grateful for any [reports on bugs](https://www.radiomuseum.org/forum/software_for_cohiradia_details_and_problem_solving.html), as they help to eliminate problems quickly.

Have fun with the new tool

Hermann Scharfetter