---
title: Cohiradia Internal procedures
---

# Process for preparing a recording before uploading to the archive

TODO: write description


# Process for upload of  a new recording

1) The recording must consist of one or several wav-files, while the wav header must comply with the format for SDR-IQ-Files as used by e.g. SDRUno. This wav header is automatically produced by SDR software like SDRUno and the COHIWizard.
  Each header must contain the name of the subsequent file in the field 'nextfilename'. This name can be edited with the COHIWizard in the tab 'Wavheader editor'. The last file of the series MUST NOT CONTAIN any name. Otherwise there will occur an error when committing the annotation yaml
2) Please connect to the server with any file transfer software like Filezilla, WinSCP or similar. Navigate to the directory 'data'.
3) Within this direcory create a new folder for the recording. There is a standard nomenclature fur the naming of such directories which is
   
           XX_YYYYS
   
   XX are initals of the author, YYYY is the year of the recording, S is a uppercase letter from A - Z in ascending order and <1stfilenamstem> is the stem (without extension)
   of the name of the first file in the recording. Example
   
          HS_2025A
  
        * Author = H.S. (here Hermann Scharfetter), 
        * Recording year 2025, 
        * A: first folder in the 2025 series
        
4) copy all files of the recording to that folder
5) go to https://github.com/radiomuseum/cohiradia-metadata/commits/main/yaml. You need to be authorized to access this GITHub repository. Please ask the RMOrg-sysadmin for admission if you don't have any.
6) create a new file (or push one from your local git) which complies with the general formatting rules specified in Appendix 7.1 of the [Report 2023](https://cohiradia.radiomuseum.org/download/docs/Documentation/COHIRADIA_Report2023_dt.pdf). Name the file appropriately. There is a standard nomenclature for the naming of such files which is

  XX_YYYYS-<1stfilenamstem>.yaml

  Example
   
        HS_2025A-SDRuno_20250330_185100Z_1125kHz.yaml 
  
        * Author = H.S. (here Hermann Scharfetter), 
        * Recording year 2025, 
        * A: first folder in the 2025 series
        * SDRuno_20250330_185100Z_1125kHz is the stem of SDRuno_20250330_185100Z_1125kHz.wav, the first file of the recording
        * .yaml: extension of a yaml-File

7) fill in all required informations. You can either do that manually, using as a template any other yaml-file already provided in the repository, or generate it automatically with the COHIWizard. The COHIWizard has a tab 'annotator' which provides all tools for generating a valid annotation yaml and which guides you through the annotation process interactively. For details see the users guide of the COHIWizard. It is recommended to use the COHIWizard, because this helps avoiding errors during the validation of the annotation by the respective server routines.
8) commit the yaml to the repository and wait until the validation procedure has been accomplished. This will be visible by a green hook, something like that:

 <img src="https://cohiradia.radiomuseum.org/download/docs/Documentation/Ann_yaml_valid.PNG" /> 

9) If there appears a red cross, the validation has failed. Clicking on 'Details' opens a logfile which then shows the error messages. Mostly they show useful details on what went wrong. Then you should correct your yaml accordingly. If you cannot find any solution, contact the RMOrg system admin for help.
10) If validation went o.k., open GITBash and enter the command:

  `curl --verbose -s -XPOST https://cohiradia.radiomuseum.org/api/metadata/import`

11) After that a new entry for the recording should appear in the list of recordings on the landing page. Now click on 'Download' and check, if there appears a list of files corresponding to what you have uploaded to the repository. If this list does not appear or some strange message is visible, please chack for errors. One common error is that the last file of the recording contains a non-empty filename in the field 'nextfilename'. Please remove that in any case and re-upload the file. Also wrong names of the files following one another in 'nextfilename' can cause this error.

