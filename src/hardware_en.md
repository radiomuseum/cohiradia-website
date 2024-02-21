---
title:  Hardware-Platform STEMLAB125-14
---
## Required Hardware

1. basic RedPitaya STEMLAB125-14 package consisting of:
   
      * STEMLAB125-14 main unit
      * STEMLAB plug-in power supply unit
      * LAN cable
      * SD card with typ. 16GB

2. optional: housing for the STEMLAB

3. AM radio with external input for 'antenna' and 'earth ground'

4. plug adapter and coax cable for coupling between SMA output of the Stemlab and RF isolating transformer

5. PC with sufficient disk space for the data files.

6. RF isolating transformer (e.g. a balun) with a suitable transformation ratio from the 50&Omega; output of the STEMLAB to the radio. Usually an impedance transformation 1:9 to 1:16 (turns ratio 1:3 or 1:4) works for typical tube devices. In principle, any balun suitable for the respective frequency range can be used if the primary and secondary sides are completely separated (no common ground!). The author now uses a toroidal core FT114, material 43 with 15:60 turns, CuL 0.25 (inductance 120uH : 2mH), STEMLAB : Radio. 

##	Installation of the server software on the STEMLAB125-14

Normally, an SD card with the operating system (Ubuntu) is supplied with the purchase of a STEMLAB125-14. This must now be inserted into the SD card slot of the STEMLAB. If you do not have this SD card, you have to create one yourself, the instructions for this and the required image file can be found on the 
[Red-Pitaya Page](https://redpitaya.readthedocs.io/en/latest/quickStart/SDcard/SDcard.html)
You can then connect STEMLAB to the Internet and call up an installation script kindly created by Ueli Kurmann. The connection can be made either by Ethernet cable or by a WLAN dongle via a standard router. The following steps must then be taken:

1. start a web browser (e.g. Mozilla Firefox) on the PC. On the web browser in the address field
   
   `http://rp-######.local`
   
   where ###### stands for the MAC address (e.g. rp-f03e25.local). The MAC address is printed on the Ethernet connector of each STEMLAB.
 
3. wait until the STEMLAB apps are loaded in the web browser (this can sometimes take a while) <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step1_sm.png" /> The view should be similar to the adjacent image. You can see a series of icons with which you can call up various functions on the STEMLAB. Only the 'System' icon is relevant for COHIRADIA.

4. Open the folder „System“ by clicking on it and afterwards call the App „Network Manager“. <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step2.png" /> In this manager the IP address can be read out which has been assigned by the router.                           

&nbsp;

<img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step3.png" /> 

&nbsp;

&nbsp;

&nbsp;

5. Open a command prompt window under Windows and log in via ssh on the STEMLAB125-15 with the IP address assigned by the router, username and password are 'root' and 'root'.  (Port = port22). Typical call: 

    `ssh root@###.###.###.###, 	Password: root`

   ###.###.###.### is the IP-address.

6. after Ubuntu has reported with the command line prompt, it is best to carry out a system update with 'apt update' and then install the packages with 'apt upgrade'.

7. after the upgrade, enter the following command in one line:

    `curl --silent --cookie "SCHLUESSEL=1" ht<span>tps://</span>cohiradia.radiomuseum.org/install.sh |bash`

STEMLAB then executes the installation script and creates a directory with the necessary shell scripts, the server program and the bit file for the FPGA. 

8. after successful installation, shut down STEMLAB properly with the command:
   
    `halt`

When the console reports that the connection has been closed and the red heartbeat LED on the STEMLAB has stopped flashing, the device's power supply can be unplugged again. The system is then configured for use in accordance with COHIRADIA.

## Assembling the hardware

1. disconnect the STEMLAB from the router and connect it directly to the LAN socket of the PC using the LAN cable. **) 

2. connect the SMA output socket 'OUT1' to the low-impedance side of the RF isolating transformer/balun via a 50&Omega; coaxial cable. 

3. connect the antenna input of the AM radio to the high-impedance side of the isolating RF transformer/balun.

4. connect the plug-in power supply of the STEMLAB to the micro USB port for 'Power'. Alternatively, the STEMLAB can also be powered directly from a USB port on the PC using a suitable micro-USB cable.

See also the [video tutorial](https://cohiradia.radiomuseum.org/download/COHIRADIA_Installations_Tutorial.mp4). Although this tutorial refers to the use of the very first RFCorder version 1.0 (no longer supported), all higher versions can of course be used essentially in the same way.

**)  <font size="2"> According to the manufacturer, a WLAN connection can also be set up as an alternative to the LAN cable if a WLAN dongle has been purchased. However, the author has not yet tried this option himself. As a second alternative, the STEMLAB may probably also remain connected to the router, but the IP address assigned by the router would then have to be used. This mode is probably not relevant, as in practice the radio to be played is rarely located right next to the router. Also this operating mode not tested by the author. </font>

## Prepare playback app

There are several software versions available for playing archived recordings. All software can be downloaded from the [Software page](https://www.radiomuseum.org/cohiradia/software.html). It should be noted that RFCorder can only play wav files from version 2.0 onwards, the first version can only recognize the 'dat' format originally used in the first version. So far, only RFCorder v1.2 has a recording function. In addition to the full functionality of RFCorder 2.0, COHIWizard 1.0 offers many useful auxiliary functions for advanced COHIRADIA users. General procedure:

1. download the ZIP file of the desired software version to the PC.

2. unzip the file to a local directory (let's call it ~\LOCAL). The exe file as well as some auxiliary files and icons and the operating instructions (as pdf) are now created there.

3. afterwards the desired AM broadband data files (e.g. RM2006clip_fcorr_i16_C_lo1100_r1250_c0.dat ...) need to be downloaded from [Archive](https://www.radiomuseum.org/cohiradia/#recording). It is recommended to save these files in separate directories.

All zip files contain the respective operating instructions.  Although the [video-Tutorial](https://cohiradia.radiomuseum.org/download/COHIRADIA_Installations_Tutorial.mp4) is no longer completely up to date with regard to some content (e.g. use of RFCorder version 1.0), it can generally be helpful as a supplement to the operating instructions.

A detailed summary of all components tested to date and an overview of alternative hardware can be found in [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf).

<!-- comment -->
