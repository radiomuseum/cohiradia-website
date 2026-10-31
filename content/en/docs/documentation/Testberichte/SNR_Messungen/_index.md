---
title: SNR Measurements
linkTitle: SNR Measurements
date: 2026-02-07
weight: 1
description: >
  SNR measurements on signal converters by W. Barteczek, C. P. Gallenmiller, and H. Scharfetter
---

## Theoretically Expected Values

For an N-bit converter, the theoretical SNR is calculated as:

```SNR_q = 6.02*N + 1.76 (dB)```

This calculation relates the useful signal power to the noise power in the entire sampled band.

For the OSMO-fl2k with N = 8, theoretically just under 50dB SNR at full modulation is expected. Since the sampling rate is typically chosen at 10MS/s, this refers according to the Nyquist theorem to a usable bandwidth of max. 5MHz. The MW recordings have a bandwidth of 1.25MHz, therefore 4x oversampling is present, which enables an SNR gain of 6dB. Therefore, with optimal modulation, effectively just under 56 dB can be expected with the fl2k system in the MW band.

For the STEMLAB, 86dB base SNR results. With significantly higher oversampling of 100 (the sampling rate is 125MS/s), this gives an SNR gain of 20dB. Therefore, the SNR should effectively be 106dB.

## Measurements with SDR (H. Scharfetter):

The signal converter was coupled to input A of an RSPdx from SDRplay via an adjustable attenuator. Then a test signal generated using the synthesizer function was played via the COHIWizard. The playback amplitude on the COHIWizard and the gain of the SDRdx were set so that no noticeable intermodulation products became visible in the spectrum.

Two spectra were displayed:
1. Spectrum over the total bandwidth BW = 1250 kHz, FFT with 65536 points, RBW 19 kHz
2. A 20 kHz wide section with BW = 24kHz, FFT with 512 points, RBW = 28.85 Hz

Since the noise floor of the spectrometer at about -125 dB is not significantly below that of the measured spectrum, an accurate SNR determination with the signal dynamics used is only possible from the 20 kHz wide section with reasonable accuracy. The wide spectrum only serves to investigate any spurs that may occur.

To account for the RBW of the display window, the effective SNR results as:

    SNR_eff = Peak (dB) - noise floor (dB) - 10log(span/RBW)


### Measurement 1: Modulated Single Carrier

The test signal was music (ABBA, "Sugar Candy Kisses") modulated onto a carrier of 999kHz with modulation degree 0.8 and audio bandwidth 4.5 kHz. The total bandwidth of the recording was 1250 kHz (500-1750 kHz). This band has a raw SNR of more than 130 dB (tested with SDRUno), defined as the dB difference between carrier amplitude and noise floor.

### Measurement 2: Synthetic Spectrum with 29 Single Carriers

For the test, 29 carriers with music from the 20s and 30s were modulated using the COHIWizard synthesizer (source: collection of C.P. Gallenmiller). The total bandwidth of the recording was again 1250 kHz (500-1750 kHz).

When K uncorrelated carriers exist in the same band, the energy of a single peak must be reduced by a factor of K so that the total signal does not overdrive the DAC. With 29 carriers, this means a required reduction of at least 14.6dB. In fact, a reduction of at least 25 was necessary, since the transmitters in this spectrum were not ideally decorrelated.


## Measurement Result

**Single tone:**

* STEMLAB: SNR_eff = 75.8 dB, peak level of carriers -30 dB
* fl2k: SNR_eff = 57.8 dB, peak level of carriers -35 dB


<img 
  src="/images/Spektrum_PC_single_tone_fl2k_rspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Fig. 1: Spectrometer output for fl2k

<img 
  src="/images/Spektrum_PC_single_tone_SL_RP_xrspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Fig. 2: Spectrometer output for STEMLAB

Certain intermodulation peaks are visible in the wide spectrum with the fl2k and could never be completely eliminated.

For the STEMLAB, it should be noted that the measurement, due to the noise floor of the spectrometer, hardly allows better readings to be made; the actual values are probably significantly better.


**29 Carriers:**

* STEMLAB: SNR_eff = 47.8 dB, peak level of carriers -58 dB
* fl2k: SNR_eff = 35.8 dB, peak level of carriers -60 dB

<img 
  src="/images/Spektrum_PC_A2_fl2k_rspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Fig. 3: Spectrometer output for fl2k

<img 
  src="/images/Spektrum_PC_A2_SL_RP_rspdx_21_18_small.png"
  style="max-width: 70%; height: auto;"
/>

Fig. 4: Spectrometer output for STEMLAB

For the STEMLAB, it should be noted that the measurement, due to the noise floor of the spectrometer, hardly allows better readings to be made; the actual values are probably significantly better.




## Conclusion:

The single-tone measurements confirm the theoretical SNR of the fl2k (57.8 dB vs 56 dB) within the expected measurement error. For the STEMLAB, the theoretical value of 106 dB could not be verified, as the dynamic range of the spectrometer used (SDR) is insufficient to raise the noise level of the signal above that of the spectrometer. The measured value of 75.8 dB is therefore probably significantly too low, but at least illustrates the significantly better performance of the STEMLAB.

With 29 carriers, the signal amplitude had to be significantly reduced to prevent clipping. There, 35.8 dB SNR was still measured with the fl2k, while the STEMLAB again showed a value of 47.8 dB distorted by the noise floor of the spectrometer. Here too, the STEMLAB is of course superior.

Nevertheless, it can be noted that the difference is not really noticeable when listening, and the fl2k is therefore a very useful solution for most playback applications, as long as high sampling rates are not required (e.g., shortwave spectra).

## Measurements with Stand-Alone Spectrum Analyzers (W. Barteczek, C.P. Gallenmiller):

W. Barteczek performed measurements with an HP 8591E spectrum analyzer (9 kHz - 1.8 GHz) on a DeLock 62783 dongle. The spectrum recordings were made with a downstream 17dB 2N5109 amplifier and 2MHz low-pass filter behind the DeLock 62783. The test signal used was the recording 'Echoes of Bygone Radio Broadcasts: from 20's to 50's, Vol.1' from the COHI Jukebox played on a PC via COHIWizard, which contains 12 carriers. The COHIWizard settings were: No AGC/AVC, level control at -22dB. Fig. 5 shows the result with a span of 500 kHz and an RBW of 1 kHz.

<img 
  src="/images/WB_fl2k_Spektrum_bei_optimaler_Aussteuerung.jpg"
  style="max-width: 90%; height: auto;"
/>

Fig. 5: Spectrometer output for fl2k

Fig. 6 shows the result for the investigation of intermodulation products. An intermodulation distance IM3 of -40dB was achievable. The harmonic suppression was about -30dB.


<img 
  src="/images/WB_fl2k_DeLock62783_IM3_-40dB_OW_-30dB.jpg"
  style="max-width: 90%; height: auto;"
/>

Fig. 6: Spectrometer output with span 1000kHz and observation of intermodulation products.

C.P. Gallenmiller, in addition to the evaluations already presented above, also performed comparisons between COHIWizard and COHI-Player mini on a LINUX PC. The tests were conducted for 3 different signals:
1) RM2006B_part1 from the COHIRADIA archive
2) synthetic AM2 with 29 carriers as in Section 1.

The measurement device settings are identical in each case. First, Fig. 7 shows the comparison of RM2006_part1 and AM1 for STEMLAB and COHI-Player mini:

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image004_STL_mini_RM2006B_part1.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 7a: Spectrum RM2006B_part1 with STEMLAB and COHI Player mini on LINUX PC.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image001_STL_mini_AM2.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 7b: Spectrum AM2 with STEMLAB and COHI Player mini on LINUX PC.

Figures 8a and 8b show the situation for COHIWizard and fl2k for the same two source files.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image016_fl2k_Wiz_RM2006B_part1.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 8a: Spectrum RM2006B_part1 with STEMLAB and COHIWizard on LINUX PC.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image001_STL_mini_AM2.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 8b: Spectrum AM2 with STEMLAB and COHIWizard on LINUX PC.

Particularly interesting is a comparison between COHIWizard and the GNU Radio playback software for fl2k currently available on radio-bastler.de. Both were tested on a Linux PC as well as on the Raspberry Pi 5, with no relevant differences found between PC and Raspberry Pi. Therefore, the results are only shown for a Raspberry Pi. The tests were conducted for 3 different signals:
1) RM2006B_part1 from the COHIRADIA archive
2) synthetic AM2 with 29 carriers as in Section 1
3) synthetic spectrum with 14 carriers with radio broadcasts from the 70s, abbreviated 'Europa 1'

Fig. 9a-c shows the results for COHIWizard.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image016_fl2k_Wiz_RM2006B_part1.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 9a: Spectrum RM2006B_part1 with fl2k and COHIWizard on Raspberry Pi 5.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image014_fl2k_Wiz_AM2.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 9b: Spectrum AM2 with fl2k and COHIWizard on Raspberry Pi 5.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image018_fl2k_Wiz_Europa1.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 9c: Spectrum Europa 1 with fl2k and COHIWizard on Raspberry Pi 5.

Fig. 10a-c shows the results for the GNU Radio variant.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image007_fl2k_GNUraspi_RM2006B_part1.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 10a: Spectrum RM2006B_part1 with fl2k and GNU Radio on Raspberry Pi 5.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image009_fl2k_GNUraspi_AM2.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 10b: Spectrum AM2 with fl2k and GNU Radio on Raspberry Pi 5.

<img 
  src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/SNR_signal_converters/Spectra_cpg/cpg_image012_fl2k_GNUraspi_Europa1.png"
  style="max-width: 90%; height: auto;"
/>

Fig. 10c: Spectrum Europa 1 with fl2k and GNU Radio on Raspberry Pi 5.

As expected, the sound quality with the STEMLab is by far the best, regardless of the software used. Neither clipping nor cross-modulation occurs. With the FL2K, there are quality differences between GNU Radio and COHIWizard. The GNU Radio variant delivers a significantly stronger sound, which is actually quite usable in the case of a real MW spectrum. With synthetic spectra (AM2), the fl2k with GNU Radio performs significantly worse, as there is a lot of clipping and cross-modulation, but the result is reminiscent of the sound quality of a real MW transmission with interference and multipath reception. With the Europa1 spectrum with fewer and partially more widely spaced carriers, the situation is significantly better, although still not optimal. Playback with COHIWizard with FL2K stream is quieter, as the output level is about 30dB below that of GNU Radio. In return, there is practically no cross-modulation (no clipping), resulting in a significantly cleaner playback.

The following 3 audio examples provide band scans through a synthetic spectrum with 29 carriers, recorded by C.P. Gallenmiller with a Telefunken 8001W from 1939.

STEMLab with COHIWizard:

<audio controls>
  <source src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/Bandscans/Bandscan AM2 STEMLab_c.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

fl2k with COHIWizard:

<audio controls>
  <source src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/Bandscans/Bandscan AM2 FL2K + COHIWizard_c.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

fl2k with GNU Radio, version pts5 from [radiobastler.de](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&postID=297313&highlight=fl2k#post297313):


<audio controls>
  <source src="https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/documentation/test_data/Bandscans/Bandscan AM2 FL2K + GNURadio pts5.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
