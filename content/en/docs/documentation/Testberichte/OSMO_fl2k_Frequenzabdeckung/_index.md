---
title: OSMO fl2k Frequency Coverage
linkTitle: OSMO fl2k Frequency Coverage
date: 2026-02-20
weight: 1
description: >

---

## General:

The OSMO-fl2k USB-VGA converter enjoys a certain popularity as a playback signal converter due to its low price, but naturally has limitations. These are discussed here.

The limited DAC resolution of 8 bits has already been discussed in the chapter ['SNR Measurements']({{< relref "/docs/documentation/Testberichte/SNR_Messungen/_index.md" >}}); fortunately, it hardly affects the audio quality.

A more noticeable limitation compared to the flagship STEMLAB is the limited sampling rate (SR) in combination with the fact that no complex data is transmitted to the converter. Therefore, the SR according to the Nyquist theorem must be at least 2x the baseband bandwidth of the recording to be played. Since the OSMO furthermore does not convert on-board from baseband frequency to the target RF bandwidth, two consequences result:

1. The computer must convert the baseband signals to the target frequency, which means a considerable computing load for the CPU.
2. After that, the signal must be transmitted via the USB port at a sufficient SR. For example, the minimum SR for the 41m band is 2 x 7.6 = 15.2 MS/s.

### Performance with PC as Control Computer

**Data transfer via USB:**

Depending on the PC and operating system, transmission via the USB port can definitely become a bottleneck. This is illustrated by a specific example:

The OSMO can provide an SR of 7.5 MS/s and then values between 10MS/s to 100MS/s in intervals of 10MS/s, e.g., 10, 20, 30, ... MS/s. In the case of the 41m band, 20MS/s must therefore be selected. This also just barely accommodates the 31m band, while for the 25m band one must already switch to 30MS/s.

**Computing power / CPU:**

The computing power can usually be provided by modern PCs without major problems. However, it is computationally most favorable when the ratio between the SR of the dongle and the SR of the IQ file is an integer power of 2, i.e., 2<sup>N</sup>. Under this condition, signals up to 5 MHz can usually be played back without problems, even under Windows. MW files with a typical SR of 1250 kS/s and 16 BpS are, e.g., usually very well suited.
At sampling rates that do not follow the above rule (e.g., 500 kS/s), the ffmpeg used by the COHIWizard for recoding can become slower and the pipeline can block or even crash. Recordings with higher resolutions than 16 bit (24 and 32 fps) have also proven problematic.
If the SR is low enough (e.g., 250 kS/s for LW), practically no problems ever occur, even if it does not follow the 2<sup>N</sup> rule.

The problems can sometimes be reduced when using the COHIWizard by turning off spectral monitoring, but then the volume display no longer works, so you can only set the gain "blind."

**Operating System:**

In general, the operation of the COHIWizard under LINUX has proven to be significantly more stable than under Windows. This is evident, for example, when playing SW recordings. The following observations were made on a Lenovo T590 with Intel Core i7 and 32GB RAM:

WINDOWS 10/11:

Recordings of the 49m band with center frequency around 6 kHz (i.e., target sampling rate 20 MS/s) occasionally came to a standstill, especially when reading from an external hard drive via a USB hub to which the fl2k dongle is also connected. When reading from the internal SSD, there were usually no problems at 20MS/s, provided the original SR is 250 or 500 kS/s.

However, if, for example, an RSP1a/SDRUno was used for the recording in the 49m band, the SR of 333.3 kS/s used by this device regularly leads to problems. Such recordings should therefore always be resampled to, e.g., 500 kS/s or 250 kS/s. The latter, however, leads to truncation of the band.
Recordings of the 41m and 31m bands could rarely be played back without stuttering and/or interruptions. Usually, the COHIWizard gets stuck after some time of playback and must be restarted.


LINUX (Debian 12 and 13):

Recordings up to the 31m band could be played back without problems over longer periods, even from an external hard drive and with the spectrum monitor switched on. Playback of the 25m band (30MS/s), however, did not succeed without stuttering.

No problems were ever observed with LW and MW recordings.


### Performance with Raspberry as Control Computer

If you run the COHIWizard on a Raspberry Pi5 with 8GB RAM, MW and LW recordings can practically always be played back without problems. Already in the 49m band, however, stuttering and flutter typically occur, i.e., the data either cannot be converted fast enough or the transmission via USB is stuck.

As practical as the Raspberry Pi of course is as a standalone device, it is unfortunately limited with respect to the manageable AM bands when operating the OSMO-fl2k.