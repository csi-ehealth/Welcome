# Welcome

Welcome. This CSI project is part of the Midiacom laboratory’s research group, which is located at Universidade Federal Fluminense (UFF), focused on digital health using WiFi data. We provide controlled access to the datasets, which can be requested by sending an email to one of the group members:
* **Célio Albuquerque** - celio@midiacom.uff.br
* **Débora Muchaluat-Saade** - debora@midiacom.uff.br
* **Fábio Queirós** - fabiogabriel@midiacom.uff.br
* **Iandra Galdino** - igar@midiacom.uff.br
* **Julio Soto** - jsoto@midiacom.uff.br
* **Raphael Guerra** - rguerra@midiacom.uff.br
* **Taiane Ramos** - taiane@midiacom.uff.br

Below you will find information about the structure and the available data, and for more details, please contact us by email.


# Collection of participant position data

The positions of the volunteers are collected and stored using the following numerical codes:
* 00 - Absence of a person
* 01 - Sitting facing forward, breathing normally
* 02 - Sitting facing forward, breathing intermittently
* 03 - Sit and stand (every 10 seconds), breathing normally
* 04 - Sitting with back facing, breathing normally
* 05 - Sitting with back facing, breathing intermittently
* 06 - Standing facing forward, breathing normally
* 07 - Standing facing forward, breathing intermittently
* 08 - Standing with back facing, breathing normally
* 09 - Standing with back facing, breathing intermittently
* 10 - Lying face up, breathing normally
* 11 - Lying face up, breathing intermittently
* 12 - Lying face down, breathing normally
* 13 - Lying face down, breathing intermittently
* 14 - Lie and stand (every 20 seconds), breathing normally
* 15 - Walk, breathing normally
* 16 - Run, breathing normally
* 17 - Sweep, breathing normally
* 18 - Stand and fall (20 seconds and 40 seconds respectively), breathing normally

The corresponding terms for the positions:
* **Breathing normally** - Breathing normally during the one-minute recording
* **Breathing intermittently** - Initially breathing for 20 seconds, holding the breath for 10 seconds, and repeating the cycle until completing the one-minute recording


# File name structure

## Raspberry and router asus data

The files follow the naming pattern:
pre_time_bw_80_ch_36.extension
Where:
* **pre** - prefix indicating the capture position  
* **time** - timestamp marking the start of the capture  
* **bw_80_ch_36** - network configuration used during the capture
* **extension** - Type of extension in file **.pcap**.

### Example

00_2023_11_08_-_17_26_26_bw_80_ch_36.pcap

### Breakdown

| Component               | Meaning                                        |
|-------------------------|------------------------------------------------|
| `00`                    | Absence of a person                     	   |
| `2023_11_08_-_17_26_26` | Capture start time                             |
| `bw_80_ch_36`           | Network configuration (Wi-Fi bandwidth/channel)|
| `.pcap`		  | File data in PCAP format		   	   |


## Smartwatch data

The files follow the naming pattern:
pre_time_HeartRateData.extension
Where:
* **pre** - Prefix indicating the capture position.
* **time** - Timestamp marking the start of the capture.
* **HeartRateData** - Type of vital sign data collected.
* **extension** - Type of extension in processed collected file **.json**, or in graphic format **.png**.

### Example

01_2023_10_30_-_12_20_05_HeartRateData.json

### Breakdown

| Component               | Meaning                                        |
|-------------------------|------------------------------------------------|
| `01`                    | Sitting facing forward, breathing normally 	   |
| `2023_10_30_-_12_20_05` | Capture start time                             |
| `HeartRateData`         | Type of vital sign data collected		   |
| `.json`		  | Vital sign data in JSON format		   |


## Polar data

The files follow the naming pattern:
pre_time_HeartRateData.extension
Where:
* **pre** - Prefix indicating the capture position.
* **time** - Timestamp marking the start of the capture.
* **HeartRateData** - Type of vital sign data collected.
* **extension** - Type of extension in processed collected file **.csv**, or in graphic format **.png**.

### Example

01_2023_10_30_-_12_20_05_HeartRateData.csv

### Breakdown

| Component               | Meaning                                        |
|-------------------------|------------------------------------------------|
| `01`                    | Sitting facing forward, breathing normally 	   |
| `2023_10_30_-_12_20_05` | Capture start time                             |
| `HeartRateData`         | Type of vital sign data collected		   |
| `.csv`		  | Vital sign data in CSV format		   |


# DataSet Version

The dataset is divided into two different data collection protocols, containing variations of the devices used in each repository, as follows:
* Data_DS1_(raspberry/smartwatch/Fabio_raspberry)
* Data_DS2_(raspberry/asus/smartwatch/polar/Fabio_raspberry/Fabio_asus)

## Data_DS1

Contains the following data:
* Sample rate of pcap: 500 packets per minute.
* Collected positions and order: 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17
* Smartwatch data collections with sample rate of: 7 or 60 samples per minute.

## Data_DS2

Contains the following data:
* Sample rate of pcap: 2000 packets per minute.
* Collected positions and order: 1, 3, 4, 6, 8, 10, 12, 14, 2, 5, 7, 9, 11, 13, 15, 16, 17, 18
* Smartwatch data collections with sample rate of: 60 samples per minute.
* Polar data collections with sample rate of: 60 samples per minute.

## Types of repositories

The repositories with suffixes ending in: asus, raspberry, polar, and smartwatch are data collections from the same participants, at the same moment, using different devices. Each data repository follows its respective specification:

### asus
Contains data collected by the Asus RT-AC86U device, in **.pcap** format, for the participants of dataset version 2.

### raspberry
Contains data collected by the Raspberry Pi 4 B device, in **.pcap** format, for the participants of dataset version 1 or 2.

### polar
Contains data collected by the Polar Band H10 device, in **.csv** and **.png** formats for the participants of dataset version 2.

### smartwatch
Contains data collected by the Samsung Galaxy Watch 4 device, in **.json** and **.png** format, for the participants of dataset version 1 or 2.

### Fabio_asus
Contains data collected by the RaspBerry Pi 4 B device, in **.pcap** format, for the proprietary dataset of member Fábio, following the modified protocol of dataset version 2.

### Fabio_raspberry
Contains data collected by the Asus RT-AC86U device, in **.pcap** format, for the proprietary dataset of member Fábio, following the modified protocol of dataset version 2.


# Integrity

To verify the integrity of the data collection for each dataset, each one includes a file named <b>"valid.txt"</b>, which contains the marking of successful collections and missing ones.


# Others files

The following existing repositories:
* Data_Polar - Data collected from the participants using the Polar device, from the beginning of the data collection in the first position to the last, including heart rate, accelerometer, and heart rate variability data, among other metrics.
* Data_Smartwatch - Data collected from the participants using the Smartwatch, from the beginning of the data collection in the first position to the last, including heart rate, distance traveled, among other metrics.

They contain extra files resulting from data collections with the devices of all participants, which are not currently structured or explored. To obtain access or information about each extra raw data file, contact us using the email at the top of the page.


# Collection of members’ code repository

The codes of the members and each branch of the research on CSI technology (person identification, heart rate estimation, respiratory rate estimation, position identification, among many others) are stored in secondary repositories, made available under research permission or limited by prior authorization from the responsible party. Contact us to obtain information and possible access.


# Command line for CSI data collection

The execution of the collection script (collectCSIdata.sh) must be performed on the Raspberry Pi and/or router Asus.
The parameters of collectCSIdata.sh are:

1. Anonymized participant code: Numeric three-digit code assigned at the time of completing the form.

2. The activity code defined in ‘Collection of participant position data'.

3. The bandwidth used in the Wi-Fi network.

4. The bandwidth used in the Wi-Fi network.

5. The MAC address of the device performing the ping.

6. Number of samples to be collected.

For participant 000, in the activity sitting facing forward, breathing intermittently, using the testbed in Room 534, which has an 80 MHz Wi-Fi bandwidth, on channel 36, with the laptop of MAC address DC:53:60:11:66:92 executing the ping, if we want to obtain 500 CSI samples, we use the script as follows:

sudo bash collectCSIdata.sh 000 02 80 36 DC:53:60:11:66:92 500

The result of this collection will be the creation of a directory with the participant code under the scans directory and a **.pcap** file whose name contains the activity code, the timestamp of the start of the collection, and the bandwidth and channel information used in the capture. In the case of the example above, if the capture was performed at 12:25:38 on 02/25/2022, the generated file would be:

directory_path/scans/000/02_2022_02_25_-_12_25_38_bw_80_ch_36.pcap

In addition to creating the file, the collection script also sends the collected file to the room’s desktop or notebook via SCP.


# Used devices 

The following devices were used for Wi-Fi data collection, data storage and processing, as well as vital-sign acquisition:
* Router Asus RT AC86U - Router operating in monitor mode collecting PCAP packets.
* Router TP-Link AC1750 - Router that communicates with the laptop, generating network traffic with sent/received packets.
* Raspberry Pi 4 B- Microcomputer operating in monitor mode collecting PCAP packets.
* Laptop DELL Inspiron 15 i7-5500U - Laptop that communicates with the TP-Link router, generating network traffic.
* Laptop Dell Inspiron 15-7572 - Laptop that communicates via SSH with the Asus router to store files and send commands.
* Desktop Gigabyte i7 i7-4790 - Desktop that communicates via SSH with the Raspberry Pi to store files and send commands.
* Smartphone Samsung Galaxy A12 - Smartphone that communicates with the Polar H10 heart strap, storing the files and sending commands.
* Smartwatch Samsung Galaxy Watch 4 - Smartwatch that collects heart rate data and distance traveled.
* Chest strap Polar Band H10 - Heart strap that collects heart rate, accelerometer data, and heart rate variability.

For more details, refer to **specs_devices.txt**.
