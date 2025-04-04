---
title: Cohiradia Internal procedures
---
# Process for upload of  a new recording

1) The recording must consist on 1 - N wav-files, while the wav header must comply with the format for SDR-IQ-Files as used by e.g. SDRUno. This wav header is automatically produced by SDR software like SDRUno and the COHIWizard.
  Each header must contain the name of the subsequent file in the field 'nextfilename'. This name can be edited with the COHIWizard in the tab 'Wavheader editor'. The last file of the series MUST NOT CONTAIN any name. Otherwise there will occur an error when committing the annotation yaml
2) upload the file to the file system of the archive. There is a standard nomenclature: The server provides the subdirectory 'data' which is the root directory for all recordings.
3) Please connect to the server with any file transfer software like Filezilla, WinSCP or similar. Navigate to the directory 'data'
4) Within this direcory create a new folder for the recording. There is a standard nomenclature fur the naming of such directories which is
           XX_YYYYS-<1stfilenamstem>.yaml
   XX are initals of the author, YYYY is the year of the recording, S is a uppercase letter from A - Z in ascending order and <1stfilenamstem> is the stem (without extension)
   of the name of the first file in the recording. Example
   
          HS_2025A-SDRuno_20250330_185100Z_1125kHz.yaml 
  
  * Author = H.S. (here Hermann Scharfetter), 
  * Recording year 2025, 
  * A: first folder in the 2025 series
  * SDRuno_20250330_185100Z_1125kHz is the stem of SDRuno_20250330_185100Z_1125kHz.wav, the first file of the recording
  * .yaml: extension of a yaml-File
  
5) copy all files of the recording to that folder
6) go to https://github.com/radiomuseum/cohiradia-metadata/commits/main/yaml. You need to be authorized to access this GITHub repository. Please ask the RMOrg-sysadmin for admission if you don't have any.
7) create a new file (or push one from your local git) which complies with the general formatting rules   
