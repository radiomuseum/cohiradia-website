---
title:  Hardware-Platform STEMLAB125-14 or STEMLAB125-10
---
## Required Hardware

As the software was initially developed specifically for the STEMLAB 125-14, all of the following descriptions are tailored to this device. Alternatively, COHIRADIA recordings have already been played back on the much cheaper STEMLAB 125-10 without any subjectively perceived loss of quality. This variant has not yet been extensively tested, but is most likely also sufficient for AM playback purposes with good level control. For this reason, the type designation is written STEMLAB 125-XX below, XX = 14 (fully recommended) or XX = 10 (not fully tested). In any case, we recommend the STEMLAB 125-14 for recording purposes.

1. basic RedPitaya STEMLAB125-XX package consisting of:
   
      * STEMLAB125-XX main unit
      * STEMLAB plug-in power supply unit
      * LAN cable
      * SD card with typ. 16GB

2. optional: housing for the STEMLAB

3. AM radio with external input for 'antenna' and 'earth ground'

4. plug adapter and coax cable for coupling between SMA output of the Stemlab and RF isolating transformer

5. PC with sufficient disk space for the data files.

6. RF isolating transformer (e.g. a balun) with a suitable transformation ratio from the 50&Omega; output of the STEMLAB to the radio. Usually an impedance transformation 1:9 to 1:16 (turns ratio 1:3 or 1:4) works for typical tube devices. In principle, any balun suitable for the respective frequency range can be used if the primary and secondary sides are completely separated (no common ground!). The author now uses a toroidal core FT114, material 43 with 15:60 turns, CuL 0.25 (inductance 120uH : 2mH), STEMLAB : Radio. 

## Installation of the server software on the STEMLAB125-XX

Before the STEMLAB125-XX can be put into operation with COHIRADIA, the SD card with the operating system and server software must be prepared. The STEMLAB is typically delivered with an SD card containing the operating system (a version of UBUNTU). However, this alone does not enable communication with the COHIRADIA software on the PC.

Therefore, please be sure to create a new SD card as follows:

1. Insert a new SD card (8 GB is sufficient, larger cards will of course also work) into the SD card slot of your PC (if available) or into an SD card reader connected to your PC. You can also overwrite the supplied card if necessary, but it is usually safer to keep it as an original.

2. Download the [image-File cohiradia_STEMLAB125_v1.0.img](https://cohiradia.radiomuseum.org/download/software/cohiradia_STEMLAB125_v1.0.img) from the COHIRADIA software archive and save it in any directory.

3. Write the image to the SD card using suitable software. Under Windows, [Win32Diskimager](https://win32diskimager.org/) oder der [Balena Etcher](https://etcher.balena.io/#download-etcher) are suitable, for example. Under LINUX, this can be done directly on the command line: First, read the mounted SD card partitions with `lsblk -f`. These are listed as sdb1, sdb2, or similar, for example. Then unmount the SD devices and start writing `sudo umount /dev/YOURSDDEVICE*`. YOURSDDEVICE is then what your lsblk lists, in my example sbd. Then: `sudo dd if=redpitaya_full.img of=/dev/YOURSDDEVICE bs=4M status=progress conv=fsync`. **WARNING: Use dd with extreme caution.** If you specify the wrong target, important system data may be deleted. So please check what you are doing three times!

Note: There is another [alternativ installation method](https://www.radiomuseum.org/cohiradia/SDKARTE_method2.html) that was used in the past, but it is no longer recommended as the first choice.

4. Eject the SD card and insert it into the SD card slot of the STEMLAB. Now you need to determine the IP address of the STEMLAB. There are several ways to do this. The easiest way is to connect the STEMLAB to the PC via an Ethernet cable **) and then switch on the power supply . The STEMLAB will boot up and you will see various LEDs flashing until the red ‘heartbeat’ LED starts flashing. **ATTENTION: In Windows, it can easily happen that the Ethernet connection does not work if the WIFI is switched on. So if the following steps do not work, please simply deactivate the WIFI on your PC.**

5. start a web browser (e.g. Mozilla Firefox) on the PC. On the web browser in the address field type
   
   `http://rp-######.local`
   
   where ###### stands for the MAC address (e.g. rp-f03e25.local). The MAC address is printed on the Ethernet connector of each STEMLAB.
 
6. wait until the STEMLAB apps are loaded in the web browser (this can sometimes take a while) <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step1_sm.png" /> The view should be similar to the adjacent image. You can see a series of icons with which you can call up various functions on the STEMLAB. Only the 'System' icon is relevant for COHIRADIA.

&nbsp;


8. Open the folder „System“ by clicking on it and afterwards call the App „Network Manager“. <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step2.png" /> In this manager the IP address can be read out which has been assigned by the router.                           

&nbsp;



<img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step3.png" /> 

&nbsp;

&nbsp;

&nbsp;


Once you have completed all these tasks, your STEMLAB is ready for use.  

&nbsp;;&nbsp;;&nbsp; Remark: On the Red Pitaya documentation page there is an [alternative method](https://redpitaya.readthedocs.io/en/latest/developerGuide/software/console/console/console.html) for accessing the OS of the STEMLAB via a USB console connection. This method may be used in the rare case thate the IP addres cannot be determined easily. It works via a terminal and an additional USB console connection. That way you can directly operate on the command line and read out e.g. the IP address. Recommended only for experienced IT users.

**)  <font size="2"> According to the manufacturer, a WIFI connection can also be set up as an alternative to the LAN cable if a WLAN dongle has been purchased. However, the author has not yet tried this option himself. As a second alternative, the STEMLAB may probably also remain connected to the router, but the IP address assigned by the router would then have to be used. This mode is probably not relevant, as in practice the radio to be played is rarely located right next to the router. Also this operating mode not tested by the author. </font>

## Assembling the hardware

Once you have set up he SD card and know your IP address you can connect to your Radio receiver in the following way:

1. connect the SMA output socket 'OUT1' to the low-impedance side of the RF isolating transformer/balun via a 50&Omega; coaxial cable. 

2. connect the antenna input of the AM radio to the high-impedance side of the isolating RF transformer/balun.

3. connect the plug-in power supply of the STEMLAB to the micro USB port for 'Power'. Alternatively, the STEMLAB can also be powered directly from a USB port on the PC using a suitable micro-USB cable.

See also the [video tutorial](https://cohiradia.radiomuseum.org/download/docs/COHIRADIA_Installation_Guide_part1_playback.mp4). Although this tutorial refers to the use of the very first RFCorder version 1.0 (no longer supported), all higher versions can of course be used essentially in the same way.


## Prepare playback app

There are several software versions available for playing archived recordings. All software can be downloaded from the [Software page](https://www.radiomuseum.org/cohiradia/software.html). It should be noted that RFCorder can only play wav files from version 2.0 onwards, the first version can only recognize the 'dat' format originally used in the first version. So far, only RFCorder v1.2 has a recording function. In addition to the full functionality of RFCorder 2.0, COHIWizard 1.0 offers many useful auxiliary functions for advanced COHIRADIA users. General procedure:

1. download the ZIP file of the desired software version to the PC.

2. unzip the file to a local directory (let's call it ~\LOCAL). The exe file as well as some auxiliary files and icons and the operating instructions (as pdf) are now created there.

3. afterwards the desired AM broadband data files (e.g. RM2006clip_fcorr_i16_C_lo1100_r1250_c0.dat ...) need to be downloaded from the [Archive](https://www.radiomuseum.org/cohiradia/#recording). It is recommended to save these files in separate directories.

All zip files contain the respective operating instructions.  Although the [video-Tutorial](https://cohiradia.radiomuseum.org/download/docs/COHIRADIA_Installation_Guide_part1_playback.mp4) is no longer completely up to date with regard to some content (e.g. use of RFCorder version 1.0), it can generally be helpful as a supplement to the operating instructions.

A detailed summary of all components tested to date and an overview of alternative hardware can be found in the [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_engl.pdf).

<!-- comment -->
