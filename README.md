# Motivation
This dataset was created for the AICUP 2025 Competition, focusing on Sensitive Health Information (SHI) Recognition in medical dialogue.

The dataset draws upon multiple sources, both domestic and international:

* For the international data portion: The collaborating Lowy Cancer Research Centre at the University of New South Wales (UNSW) in Australia provided real case data that has undergone ethical review. Our project personnel generated proxies for the Sensitive Health Information (SHI) within this data, which was then transcribed into a verbatim script. This script was then proofread by narrators who specialized in mimicking the medical professional's tone and style. Finally, the voice recordings were made based on the proofread script and released. Additionally, we utilized some online medical-related educational video materials (from the Dataset for Automated Medical Transcription). These were programmatically processed into audio files and transcripts, which were subsequently annotated by labeling personnel.
* The domestic data sources mainly consist of subtitles from healthcare-related TV series authorized by Public Television Service (PTS). 
These primarily include: 
1. [A young doctor in the big hospital](https://youtube.com/playlist?list=PLLhKX7btG59fhO0rJIFrLbpmjKs5aRKyx&si=8gTDjLe4sw1R2FGB)
2. [The Coordinators](https://www.ptsplus.tv/zh/programs/4545e678-65ee-4eac-aa5f-6405823a2eb2)
3. [Wake Up](https://www.ptsplus.tv/zh/programs/dd8e14a9-2af2-49ee-8bce-b82cb883b1e6)
4. [Mad Doctor](https://www.ptsplus.tv/zh/programs/a3f838da-d613-4d6b-a0b0-2c5a048dba5f)


We have compiled this dataset for the purpose of hosting the AICUP 2025 competition, themed around the identification of sensitive personal information in doctor-patient voice conversations.
The dataset sources encompass multiple domestic and international origins:

* For the international data component, ethically reviewed real-world case data is provided by the Lowy Cancer Research Centre at the University of New South Wales (UNSW) in Australia. Project personnel will generate synthetic speech for the SHI (Speech-to-Speech) data within these cases, convert it into transcripts, and then have speech actors proofread the transcripts using medical personnel narration styles before recording and releasing the audio files. Additionally, some online medical teaching video materials (from the Dataset for Automated Medical Transcription) are utilized. These are processed by programs to generate audio files and transcripts, which are then annotated by annotation personnel.
* Domestic data sources primarily consist of subtitles from medical-themed television series licensed from Public Television Service (PTS).

Translated with DeepL.com (free version)
Primarily from:
1. [A young doctor in a big hospital](https://youtube.com/playlist?list=PLLhKX7btG59fhO0rJIFrLbpmjKs5aRKyx&si=8gTDjLe4sw1R2FGB)
2. [The Coordinators](https://www.ptsplus.tv/zh/programs/4545e678-65ee-4eac-aa5f-6405823a2eb2)
3. [Wake Up](https://www.ptsplus.tv/zh/programs/dd8e14a9-2af2-49ee-8bce-b82cb883b1e6)
4. [Mad Doctor](https://www.ptsplus.tv/zh/programs/a3f838da-d613-4d6b-a0b0-2c5a048dba5f)

# Description of the dataset

## Directories:

| Directory | Description |
| --- | --- |
| <code>dataset/test</code> | Competition Test Set (Competition Test Set): task1_answer.txt, task2_answer.txt |
| <code>dataset/train/first phase</code> | Competition Training Set (Competition Training Set Part One), Part 1: audio folder, task1_answer.txt, task2_answer.txt |
| <code>dataset/train/second phase</code> | Competition Training Set (Competition Training Set Part Two), Part 2: audio folder, task1_answer.txt, task2_answer.txt |
| <code>dataset/valid</code> | Competition Valid Set (Competition validation set): audio folder, task1_answer.txt, task2_answer.txt |
| <code>Kappa Value</code> | SHI Annotation Consistency (SHI Labeling Consistency) |
| <code>Public Television Service Authorization Source.csv</code> | PTS Drama Source Clip (公視戲劇來源片段) |

## Task1_answer file structure:

```
File ID	Transcript
SAMPLE_1	Mr. Li, 45 years old, has had hypertension for three years. Recently, his blood pressure has been unstable, and his doctor recommended adjusting his medication and monitoring his daily readings.。
SAMPLE_2	Mr. Johnson, 58 years old, has been experiencing irregular heartbeat. The doctor advised him to undergo further cardiac examination next week.
```
### Definitions

| Term | Definition |
| --- | --- |
| <code>File ID</code> | Audio File Name (Audio File Name) |
| <code>Transcript</code> | The transcript of the audio (Subtitles for this audio) |


## Task2_answer file structure:

```
File ID	SHI Type	Start Offset	End Offset	Text(Optional)
file01	AGE	1.523	1.826	57
file01	ATIENT	1.923	2.120	Ken Moll
file01	IDNUM	4.85	5.401	62S021442H
file01	STREET	5.52	5.865	Yale
file01	CITY	6.451	6.732	Andergrove
file01	STATE	6.735	6.957	Tasmania
file01	ZIP	11.167	11.984	2042
file01	MEDICALRECORD	12.491	13.644	6270214.MFH
file01	IDNUM	14.464	15.782	62S02144

```
### Definitions

| Term | Definition |
| --- | --- |
| <code>File ID</code> | Audio File Name (Audio File Name) |
| <code>SHI Type</code> | Label Types (Label Types) |
| <code>Start Offset</code> | Label Start Position (Tag Start Position) |
| <code>End Offset</code> | Label End Position (End of tag position) |
| <code>Text(Optional)</code> | Label Reference Text (Label Reference Text) |

### Task 2 Annotation Categories

| SHI Category | Category Definition | Category Names in the Provided Data |
| :----| :----| :----|
| Name | Patient name / Doctor name / Username / Family name / Personl name | PATIENT / DOCTOR / USERNAME / FAMILYNAME / PERSONALNAME |
| Occupation | None | PROFESSION |
| Location | Room number / Department / Hospital / Organization / Street / City / State / Country / Zip Code / Other | ROOM / DEPARTMENT / HOSPITAL / ORGANIZATION / STREET / CITY / DISTRICT / COUNTY / STATE / COUNTRY / ZIP / LOCATION-OTHER |
| Age | None  | AGE |
| Date | Date / Time / Duration / Frequency | DATE / TIME / DURATION / SET |
| Contact Information | Phone number / Fax / Email address / URL / IP address | PHONE / FAX / EMAIL / URL / IPADDRESS |
| Identifiers	 | 	Social Security Number (SSN) / Medical Record Number / Health Plan Number / Account / License Number / Vehicle / Device Number / Biometric ID / ID Number | SOCIAL_SECURITY_NUMBER / MEDICAL_RECORD_NUMBER / HEALTH_PLAN_NUMBER / ACCOUNT_NUMBER / LICENSE_NUMBER / VEHICLE_ID / DEVICE_ID / BIOMETRIC_ID / ID_NUMBER |
| Other | None  | OTHER |



| SHI Category | Category Definition | Category Name in Competition Data |
| :----| :----| :----|
| Name | Patient Name / Doctor Name / User Name / Family Member Name / Personal Name | PATIENT / DOCTOR / USERNAME / FAMILYNAME / PERSONALNAME |
| Profession | None | PROFESSION |
| Location | Room Number / Department / Hospital / Organization / Street / City / District / County / State / Country / ZIP / OTHER | ROOM / DEPARTMENT / HOSPITAL / ORGANIZATION / STREET / CITY / DISTRICT / COUNTY / STATE / COUNTRY / ZIP / LOCATION-OTHER |
| Age | None | AGE |
| Date | Date / Time / Duration / Frequency | DATE / TIME / DURATION / SET |
| Contact Method | Mobile Number / Fax / Email Address / URL / IP Address | PHONE / FAX / EMAIL / URL / IPADDRESS |
| Identifier | Social Security Number / Medical Record Number / Health Plan Number / Account / License Number / License Plate / Device ID / Biometric ID / Identification Number | SOCIAL_SECURITY_NUMBER / MEDICAL_RECORD_NUMBER / HEALTH_PLAN_NUMBER / ACCOUNT_NUMBER / LICENSE_NUMBER / VEHICLE_ID / DEVICE_ID / BIOMETRIC_ID / ID_NUMBER |
| Other | None | OTHER |

# How to get dataset
We do not actively provide the original voice recordings of real patient cases in this dataset. If you are interested in using the complete OpenDeID v3 corpus, please refer to and apply through the following link: https://github.com/SREDH-Consortium/OpenDeID-Corpus.<br>
The Public Television (PTS) segments only provide the source reference. Users are responsible for downloading the corresponding audio files themselves.<br>
This resource does not actively provide authentic patient speech recordings. Interested parties wishing to use the complete The OpenDeid v3 corpus should refer to https://github.com/SREDH-Consortium/OpenDeID-Corpus for application procedures.<br>
Public television clips serve solely as data sources; users must download the speech recordings themselves.

## External Resources

Some parts of this project are based on external works licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0), which have been modified or reused in accordance with the terms of that license.
You can view the full license details at the following link: https://creativecommons.org/licenses/by/4.0/

### 1. [Dataset for Automated Medical Transcription/Data set]

```
Title: Dataset for Automated Medical Transcription (v1.0)
Author: Kazi, N., Kuntz, M., Kanewala, U., & Kahanda, I. Zenodo. (2020)
Source: https://doi.org/10.5281/zenodo.4279041
License: Creative Commons Attribution 4.0 International
Changes: A total of 40 audio files (D0420-S1-T01.wav to D0422-S4-T05.wav) were used from this dataset.
The audio files were annotated with SHI labels, segmented into multiple audio clips, and released together with corresponding audio files, transcription texts, and SHI label answers.
The original content and copyright remain the property of the original authors.
```

# Disclaimer

This dataset is provided “As Is”, without any express or implied warranty.
In no event shall the authors or copyright holders be liable for any claims, damages, or other liabilities.

The original transcripts and labels may not fully correspond to the actual speech content.
