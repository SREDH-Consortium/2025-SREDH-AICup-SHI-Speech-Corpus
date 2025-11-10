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


我們製作了這個資料集，目的是舉辦 AICUP 2025 競賽，主題是醫病語音敏感個人資料辨識競賽。
資料集來源包含國內與國外多來源：

* 在國外資料部分，由合作之澳洲新南威爾斯大學（University of New South Wales，簡稱 UNSW）洛維癌症研究中心（Lowy Cancer Research Centre）提供通過倫理審查的真實病例資料，本計畫人員將針對其中的 SHI 進行代理產生後轉化為逐字稿，再透過口說人員以醫事人員口述的方式針對逐字稿進行校稿後，錄製語音檔並釋出。另外也使用部分線上醫療相關的教學影音資料(來自 Dataset for Automated Medical Transcription )，透過程式處理轉成音檔與逐字稿後再透過標註人員進行標註。
* 國內資料來源以取得公視授權的醫療場域相關影集字幕為主。
主要來自:
1. [大醫院小醫師](https://youtube.com/playlist?list=PLLhKX7btG59fhO0rJIFrLbpmjKs5aRKyx&si=8gTDjLe4sw1R2FGB)
2. [生死接線員](https://www.ptsplus.tv/zh/programs/4545e678-65ee-4eac-aa5f-6405823a2eb2)
3. [麻醉風暴](https://www.ptsplus.tv/zh/programs/dd8e14a9-2af2-49ee-8bce-b82cb883b1e6)
4. [村里來了個暴走女外科](https://www.ptsplus.tv/zh/programs/a3f838da-d613-4d6b-a0b0-2c5a048dba5f)

# Description of the dataset

## Directories:

| Directory | Description |
| --- | --- |
| <code>dataset/test</code> | Competition Test Set (競賽測試集): task1_answer.txt, task2_answer.txt |
| <code>dataset/train/first phase</code> | Competition Training Set (競賽訓練集 第一部份), Part 1: audio folder, task1_answer.txt, task2_answer.txt |
| <code>dataset/train/second phase</code> | Competition Training Set (競賽訓練集 第二部份), Part 2: audio folder, task1_answer.txt, task2_answer.txt |
| <code>dataset/valid</code> | Competition Valid Set (競賽驗證集): audio folder, task1_answer.txt, task2_answer.txt |
| <code>Kappa Value</code> | SHI Annotation Consistency (SHI標註一致性) |
| <code>Public Television Service Authorization Source.csv</code> | PTS Drama Source Clip (公視戲劇來源片段) |

## Task1_answer file structure:

```
File ID	Transcript
SAMPLE_1	李先生，45 歲，因高血壓三年，最近血壓控制不穩，醫生建議調整藥物並監測每日數據。
SAMPLE_2	Mr. Johnson, 58 years old, has been experiencing irregular heartbeat. The doctor advised him to undergo further cardiac examination next week.
```
### Definitions

| Term | Definition |
| --- | --- |
| <code>File ID</code> | Audio File Name (語音檔案名稱) |
| <code>Transcript</code> | The transcript of the audio (該語音的字幕) |


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
| <code>File ID</code> | Audio File Name (語音檔案名稱) |
| <code>SHI Type</code> | Label Types (標籤種類) |
| <code>Start Offset</code> | Label Start Position (標籤開始位置) |
| <code>End Offset</code> | Label End Position (標籤結束位置) |
| <code>Text(Optional)</code> | Label Reference Text (標籤參考文本) |

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



| SHI 類別 | 類別定義 | 競賽提供的資料中的類別名稱 |
| :----| :----| :----|
| 姓名 | 病患名 / 醫師名 / 使用者名稱 / 家屬姓名 / 個人姓名 | PATIENT / DOCTOR / USERNAME / FAMILYNAME / PERSONALNAME |
| 職業 | 無 | PROFESSION |
| 地點 | 診間號 / 部門 / 醫院 / 組織 / 街 / 城市 / 區 / 郡 / 州 / 國家 / 區號 / 其他 | ROOM / DEPARTMENT / HOSPITAL / ORGANIZATION / STREET / CITY / DISTRICT / COUNTY / STATE / COUNTRY / ZIP / LOCATION-OTHER |
| 年齡 | 無 | AGE |
| 日期 | 日期 / 時間 / 週期 / 頻率 | DATE / TIME / DURATION / SET |
| 聯絡方式 | 手機號碼 / 傳真 / 電子郵件信箱 / 網址 / 網際網路協定位址 | PHONE / FAX / EMAIL / URL / IPADDRESS |
| 識別符 | 社群安全碼 / 醫療紀錄號碼 / 健康計畫號碼 / 帳戶 / 證照號碼 / 車牌 / 裝置號碼 / 生物識別碼 / 識別碼 | SOCIAL_SECURITY_NUMBER / MEDICAL_RECORD_NUMBER / HEALTH_PLAN_NUMBER / ACCOUNT_NUMBER / LICENSE_NUMBER / VEHICLE_ID / DEVICE_ID / BIOMETRIC_ID / ID_NUMBER |
| 其他 | 無 | OTHER |

# How to get dataset
We do not actively provide the original voice recordings of real patient cases in this dataset. If you are interested in using the complete OpenDeID v3 corpus, please refer to and apply through the following link: https://github.com/SREDH-Consortium/OpenDeID-Corpus
The Public Television (PTS) segments only provide the source reference. Users are responsible for downloading the corresponding audio files themselves.
本資料不主動提供真實病例語音，有興趣使用完整的 The OpenDeid v3 corpus 請參考 https://github.com/SREDH-Consortium/OpenDeID-Corpus 進行申請。
公共電視片段僅提供資料來源，由使用者自行下載該語音。

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