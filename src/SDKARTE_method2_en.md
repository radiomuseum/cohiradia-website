---
title:  Hardware-Plattform STEMLAB125-14 oder STEMLAB125-10
---
## Option 2 for manual installation of the operating system and COHIRADIA software (more complicated, more suitable for experienced IT users)** 



This option is well known to existing users of COHIRADIA tools, but unfortunately has become more complicated since the introduction of OS2.00 by RedPitaya. We therefore no longer recommend this option as the first choice; it is only listed here for the sake of completeness.

**ATTENTION ! READ THE FOLLOWING BEFORE STARTING:**

**STEMLAB now comes with an SD card containing a newer version of the operating system, most recently OS2.00. All previous COHIRADIA software versions were developed under version 1.04; V2.00 is currently not compatible with our software. For COHIRADIA, you must always use version 1.04-28.**

If version 2.00 is preconfigured when you purchase a new STEMLAB, you must create your own SD card with version 1.04-28. You can find the link to the corresponding image and all relevant instrucions on the [Red-Pitaya Page](https://redpitaya.readthedocs.io/en/latest/quickStart/SDcard/SDcard.html), as well as the above link to the required image file. 

After inserting the correctly configured SD-card you have to connect STEMLAB to the Internet and call up an installation script kindly created by Ueli Kurmann. The connection can be made either by Ethernet cable or by a WLAN dongle via a standard router. The following steps must then be taken:

1. start a web browser (e.g. Mozilla Firefox) on the PC. On the web browser in the address field
   
   `http://rp-######.local`
   
   where ###### stands for the MAC address (e.g. rp-f03e25.local). The MAC address is printed on the Ethernet connector of each STEMLAB.
 
3. wait until the STEMLAB apps are loaded in the web browser (this can sometimes take a while) <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step1_sm.png" /> The view should be similar to the adjacent image. You can see a series of icons with which you can call up various functions on the STEMLAB. Only the 'System' icon is relevant for COHIRADIA.

4. Open the folder „System“ by clicking on it and afterwards call the App „Network Manager“. <img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step2.png" /> In this manager the IP address can be read out which has been assigned by the router.                           

&nbsp;

&nbsp;

<img align="right" width="200" height="100" src="https://cohiradia.radiomuseum.org/download/software/STEMLAB_Installation_Step3.png" /> 

&nbsp;

&nbsp;

&nbsp;

5. Open a command prompt window under Windows (or a terminal under LINUX) and log in via ssh on the STEMLAB125-15 with the IP address assigned by the router, username and password are 'root' and 'root'.  (Port = port22). Typical call: 

    `ssh root@###.###.###.###, 	Password: root`

   ###.###.###.### is the IP-address.

6. after Ubuntu has reported with the command line prompt, it is best to carry out a system update with 'apt update' and then install the packages with 'apt upgrade'.

7. after the upgrade, enter the following command in one line:

    `curl --silent --cookie "SCHLUESSEL=1" https://cohiradia.radiomuseum.org/install.sh |bash`

STEMLAB then executes the installation script and creates a directory with the necessary shell scripts, the server program and the bit file for the FPGA. 

8. after successful installation, shut down STEMLAB properly with the command:
   
    `halt`

When the console reports that the connection has been closed and the red heartbeat LED on the STEMLAB has stopped flashing, the device's power supply can be unplugged again. The system is then configured for use in accordance with COHIRADIA.

<!-- comment -->
