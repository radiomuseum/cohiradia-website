---
title: Cohiradia
card1:
  name: Recordings
  desc: "Download of recordings."
  link: "#recording"
card2:
  name: "Report 2023"
  desc: "Cohiradia report 2023."
  link: "https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf"
card3:
  name: Documentations
  desc: "Download of documentations."
  link: "https://www.radiomuseum.org/cohiradia/documentation.html"
card4:
  name: Software
  desc: "Software download."
  link: "https://www.radiomuseum.org/cohiradia/software.html"
banner: https://cohiradia.radiomuseum.org/download/docs/ressources_webpage/intropage_zierband2.png
---
## Introduction

<div style="float: left; margin-right: 15px;">
  <iframe width="320" height="180" src="https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_TimeMachine_English_YT.mp4"
          frameborder="0" allowfullscreen></iframe>
</div>

Imagine that you could tune through and listen to all the stations of the medium wave band, which were active on a certain day in 2006, on your historical radio receiver at any time. You could then get the feeling as if all these stations were broadcasting right now. Of course the playback should not be based on an artificial montage, but on an authentic historical recording. This scenario probably represents a dream of many collectors, whose beautiful and valuable devices will remain increasingly 'mute' due to the rapidly progressing final shutdown of AM transmitters. Exactly this dream is fulfilled by the COHIRADIA project, as this [demo video](https://cohiradia.radiomuseum.org/download/COHIRADIA_Demovideo_v1.mp4) shows.

COHIRADIA is an acronym for **CO**nservation of **HI**storical **RA**diofrequency bands by **DI**gital **A**rchiving.

## Goals
COHIRADIA has two main goals:

1) to give interested radio enthusiasts and collectors the opportunity to play back original radio signals recorded in the past on historical radio receivers. These signals should not contain only a single station, but a whole frequency band (e.g. medium wave) with all radio stations contained therein on the correct carrier frequencies existing at the time of recording. This allows all stations to be tuned-trough on the radio receiver.
2) to record currently broadcast radiofrequency bands, especially in the AM range, at various locations around the world. The goal is to map the still existing landscape of active stations in the form of archive files in time before the technology finally will die out.

 ## Technical Solution  
COHIRADIA is made possible by recording and playing back digitized radio frequency signals using software-defined radios (SDRs). Wideband recording directly from an antenna is now relatively easy with several SDRs on the market, while playback requires more advanced SDRs with transmit output. The initiator of COHIRADIA uses the STEMLAB125-14 from RedPitaya, which offers excellent quality for recording and playback with 14 bit ADC resolution and 125MS/s sampling rate. Alternative TX-capable SDRS with similar or better performance specifications also exist. The much cheaper STEMLAB125-10, for example, has already been used for playback on a trial basis, but has not been extensively tested.

The recordings can be played back by anyone who also possesses a STEMLAB125-14 or a suitable TX-capable SDR. The use of a uniform data format guarantees interchangeability between different platforms.

In order to build up a rich archive in as short a time as possible, interested amateurs are invited to make their own recordings and to make the data available to the Radio Museum and/or to report on the successful playback of files on historical radio equipment. Creative ideas for other applications (activities, museums, ...) are also very welcome.

If you are interested, more details on the technology, software and quality criteria used can be found in the [report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_engl.pdf).

The oldest existing recordings on MW and SW were made by the initiator in the years 2006 - 2009 in analog form on a video recorder and digitized in 2021 with a STEMLAB125-14. All further datasets, especially from 2015 on, were produced directly digitally by various radio amateurs participating in COHIRADIA, mainly on long, medium and short wave up to 30 MHz. On these recordings there are still many European stations which have been switched off in the meantime.

For the playback of the data files as well as for the creation of own recordings on the STEMLAB125-14 a first software version was created in Python and is available for Windows10 as exe program. The author has already created a GITHub repository for the sources, a release as an open source project is planned for the near future.

* [Descriptions for the installation of the necessary hard- and software](https://www.radiomuseum.org/cohiradia/hardware.html)
* [Available software installation packages](https://www.radiomuseum.org/cohiradia/software.html)
* [Data files from archived recordings](https://www.radiomuseum.org/cohiradia/#recording)

## CONTACT

The project coordinator of COHIRADIA is Hermann Scharfetter. As a member of rmorg, you can contact him via his [profile](/dsp_profile.cfm?Member_Id=3642). As a guest please drop him an by [email](mailto:hermann.scharfetter@gmail.com) to ask questions, suggest own recordings for the archive or develop the project further together with him.

## COHI Jukebox
Unfortunately, there are practically no original recordings of RF broadband signals in the sense of COHIRADIA, especially from the early days of radio up to the 1980s. However, it may feel a bit strange to play back music and other contents from e.g. 2020 on radio sets from the 20-50s. Thus it would be desirable to have access to recordings the contents of which at least 'fit' these sets. The category

* [COHI Jukebox](https://www.radiomuseum.org/dsp_cohiradia.cfm?synthetic)

attempts to approach this topic by providing synthetic AM bands (especially MW and LW) with a variety of 'stations' on common frequencies that convey the contents of time.

## Other Archives
Besides COHIRADIA, the following archives are known to contain interesting wideband material as well:

* [My DX Travel Logs](https://www.donmooredxer.com)  
  Many Latin American recordings and a few LW recordings on which European stations also appear 
* [The Radio Spectrum Archive](https://spectrumarchive.org)  
  Datasets from USA, some of which are digitized recordings made on analogue video recorders back to 1986
* [Perseus WAV Files by Günter Lorenz](http://pira.fmlist.org/perseus/)  
  European archive with mostly short sequences since 2009

## Interesting links to other projects:

In the context of COHIRADIA, there are now several activities in which recordings from our archive are used. Unfortunately this is a German site, but the idea is probably also accessible to international readers:

* [Radiobastler.de, project with fl2k](https://www.radio-bastler.de/forum/index.php?thread/27410-cohiradia-player-unter-gnu-radio/&postID=297313&highlight=fl2k#post297313)

    In this project an fl2k USB-VGA converter is presented, which can also be used as an [inexpensive alternative hardware](https://osmocom.org/projects/osmo-fl2k/wiki) with a high data rate for the playback of HF broadband signals. Although the resolution of the built-in DACs is not very high at 8-bit, an interesting project presented in the forum of [www.radio-bastler.de](https://www.radio-bastler.de) could be realized using GNU-Radio for playing COHIRADIA recordings. A great link for LINUX-affine radio friends!

The following two videos show very nicely the application of the fl2k system on two old receivers by Gerald Gauert, who is in charge of the exhibition [100 years of radio broadcasting](https://www.youtube.com/watch?v=qlJWguweo4U) at the Museumshof Chörau (Germany):

* [Example video application fl2k A](https://youtu.be/RRBtvOd3pog)
* [Example video application fl2k B](https://youtu.be/4jC2XtWUFI8)
    
    
