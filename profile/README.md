# Artifact Appendix

Paper title: **EXADPrinter: Semi-Exhaustive Permissionless Device Fingerprinting Within the Android Ecosystem**

Requested Badge(s):
  - [x] **Available**
  - [x] **Functional**
  - [ ] **Reproduced**


## Description

1. *Paper Title*: **EXADPrinter: Semi-Exhaustive Permissionless Device Fingerprinting Within the Android Ecosystem**
2. *Authors*: **Sihem Bouhenniche** (Univ. Lille, CNRS, Inria), **Pierre Laperdrix** (Univ. Lille, CNRS, Inria), **Walter Rudametkin** (Univ. Rennes, CNRS, Inria, IRISA, IUF).
3. *Year & Issue*: PETs Issue 3 - 2026
4. *Description*: This GitHub organization contains main artifacts supporting the paper. It includes two repositories:  
   - [AmIUniqueApp](https://github.com/AmIUniqueTools/AmIUniqueApp), provides the source code of the **EXADPrinter** Android fingerprinting library together with the Android application used to collect fingerprints from real devices. 
   - [EXADPrinterPipelineExample](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample), contains scripts and notebooks used for the data processing pipeline, including examples of data collection, parsing and cleaning fingerprints. 
To facilitate using [EXADPrinterPipelineExample](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample) while preserving privacy, we provide a small dummy dataset and an example collection workflow using real Android devices from the [BrowserStack](https://www.browserstack.com/) platform.

### Security/Privacy Issues and Ethical Concerns 
This artifact contains an Android application used to collect and device fingerprint attributes. 
The application extracts attributes **without requesting Android permissions** and **does not intentionally** access personal user data such as contacts, messages, or account information.

Device fingerprint data may contain attributes that could contribute to device identification. 
For privacy and ethical reasons, the **dataset collected during the study is not included in this artifact**. 
Instead, we provide synthetic example fingerprints.

The original data collection study involving real participants was conducted following institutional ethical guidelines and was **approved by the Institutional Review Board (IRB)** of [INRIA](https://www.inria.fr/), France. 
Participants provided consent prior to participation.

The artifact does not require disabling operating system security protections and does not execute exploit code, malware, or vulnerable binaries. 
The provided scripts only automate the execution of the example Android application and the processing of example datasets. Users may review the scripts and run them on test devices or emulators if desired.

## Basic Requirements

### Hardware Requirements

Minimal hardware requirements:
- Can run on a standard laptop or workstation.
- No special hardware is required.

Recommended configuration for faster execution:
- CPU: ≥4 cores
- RAM: ≥8 GB
- Storage: ≥10 GB free disk space

***Optional:** To test the data collection process, reviewers may use a **physical Android device with Developer Options and USB debugging enabled**. Alternatively, the artifact can be executed on an **Android emulator (e.g., the Android Studio emulator)**.*


### Software Requirements

#### Operating System
- Tested on Ubuntu 20.04.6 LTS.
- Should work on any operating systems (Linux, macOS, Windows) with the required tools installed.

#### Android Development Tools
The Android components of the artifact were built with the following environment:

- Android Studio: Koala – 2024.1.1 Patch 1
(Build #AI-241.18034.62.2411.12071903, built on July 10, 2024)
- Java: version 8 (source compatibility)
- JVM: 17.0.15
- Gradle: 8.7
- Android Gradle Plugin: 8.5.1
- Kotlin: 1.8.0
- Compile SDK: Android API 35
- ADB (Android Debug Bridge): 1.0.41

***These tools are required only if reviewers want to build the Android application from source. Otherwise, pre-built APKs are provided (see Android Artifacts below).***

#### Python dependencies
The Python scripts used for data cleaning and analysis require:
- Python 3.13.7
- pip 26.0.1
Required Python packages are listed in:
- [`requirements.txt`](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/requirements.txt)

#### Datasets
- [`DUMMY_DATA`](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/tree/master/DUMMY_DATA): **dummy fingerprint datasets** demonstrating the expected format collected from real Android testing devices.

***The collected dataset from participants used in the paper cannot be shared due to privacy considerations.***

#### Automation tools (optional)
Data collection on real Android devices can optionally be automated using external platforms such as [BrowserStack](https://www.browserstack.com/).
Example scripts are provided in [`DataCollectionSetup`](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/tree/master/DataCollectionSetup); however, running them requires a BrowserStack account.

#### Android artifacts
The EXADPrinter library is available through multiple distribution methods:
- As a Maven dependency published on Maven Central.
- As a downloadable `.aar` file from the [AmIUniqueApp GitHub release page](https://github.com/AmIUniqueTools/AmIUniqueApp/releases/).

Two APKs implementing the library are also provided:
- [AmIUnique Debug APK](https://github.com/AmIUniqueTools/AmIUniqueApp/blob/main/public/app-debug.apk) – the full application used in the experiments.
- [exadprinterDemoApp.apk](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/DataCollectionSetup/exadprinterDemoApp.apk) – a minimal demonstration application that integrates the library and runs the fingerprint collection process at application launch.

### Estimated Time and Storage Consumption (Required for Functional and Reproduced badges)

Replace the following with estimated values for:

- The overall human and compute times required to run the artifact.
- The overall disk space consumed by the artifact.

This helps reviewers schedule the evaluation in their time plan and others in
general to see if everything is running as intended. This should also be
specified at a finer granularity for each experiment (see below).

## Environment

### Accessibility 

The artifact is publicly available through the following persistent Github repositories:

- [EXADPrinter Android library](https://github.com/AmIUniqueTools/AmIUniqueApp/tree/main/EXADPrinterLib)
- [AmIUnique Android application using the library](https://github.com/AmIUniqueTools/AmIUniqueApp/tree/main/app)
- [EXADPrinterPipelineExample](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/): Artifact repository containing: 
   - data cleaning pipeline scripts and notebook.
   - [DUMMY_DATA](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/tree/master/DUMMY_DATA): Dummy dataset.
   - [DataCollectionSetup](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/DataCollectionSetup/): A minimal setup to run data collection.
   - [data_preparation_pipeline.ipynb](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/data_preparation_pipeline.ipynb): A notebook demonstrating cleaning pipeline

***Every repository contains a detailed documentation***

### Set up the environment

1. Clone the artifact repository:

```
git clone https://github.com/AmIUniqueTools/EXADPrinterPipelineExample.git
cd EXADPrinterPipelineExample
```

The repository is organized as follows:
- [DUMMY_DATA/](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/tree/master/DUMMY_DATA) # Example fingerprint dataset
- [DUMMY_DATA_PREPARED/](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/tree/master/DUMMY_DATA_PREPARED) # Cleaned Example fingerprint dataset
- [DUMMY_DATA_STRUCTURE/](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/tree/master/DUMMY_DATA_STRUCTURE) # Cleaned Example fingerprint structure dataset
- [fingerprint_parser/](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/tree/master/fingerprint_parser)                # Module for parsing fingerprint attributes.
- [data_cleanning_pipeline.ipynb](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/data_preparation_pipeline.ipynb) # A Jupyter notebook implementing the attribute cleaning logic
- [DataCollectionSetup](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/DataCollectionSetup/) # A minimal setup to run data collection.

2. Create a Python environment and install dependencies:

```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

3. (Optional) - Run Data Collection
Instead of using the provided dummy dataset (DUMMY_DATA/), reviewers may optionally run a small data collection experiment using the provided automation script.

   - Edit the configuration variables in [`pipeline.sh`](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/DataCollectionSetup/pipeline.sh)
   - Replace the following variables with your own values:
      - API_END_POINT= – URL of the server that will receive the collected fingerprints. The configured endpoint should have a similar schema as in [`FingerprintApi.kt`](https://github.com/AmIUniqueTools/AmIUniqueApp/blob/main/app/src/main/java/com/amiunique/amiuniqueapp/network/FingerprintApi.kt)
      - APP_URL= – Upload the [`exadprinterDemoApp.apk`](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/DataCollectionSetup/exadprinterDemoApp.apk) APK manually to browserstack and place the download link here.
      - BROWSERSTACK_USERNAME= – Your BrowserStack username.
      - BROWSERSTACK_ACCESS_KEY= – Your BrowserStack access key.
   - Run the collection pipeline:

   ```
   ./pipeline.sh
   ```

The script will:
- deploy the demo application to BrowserStack devices,
- launch the fingerprint collection process,
- and send the collected fingerprints to the configured API endpoint.

If the script completes successfully, the collected fingerprints should appear at the configured API server and can then be processed using the analysis scripts provided in the artifact.

### Testing the Environment

To verify that the environment is correctly configured, run the following tests.

1. *Python Environment Test*

2. *Android Environment Test*
Install the demo application on an Android device (with USB debugging activated), and run it by given your configured endpoint

```
adb install exadprinterDemoApp.apk
adb shell am start \
  -n "com.amiunique.exadprinterimplementationexample/.MainActivity"\
  --es API_END_POINT "YOUR_ENDPOINT_URL"
```
The application will automatically collect the device fingerprint at startup. At the end check your server to see the collected fingerprint.

## Artifact Evaluation 

### Main Results and Claims

#### Main Result: EXADPrinter, a semi-exhaustive framewok for Android device fingerprinting

In our paper, we introduce **EXADPrinter**, a novel methodology to extract and collect device fingerprints from Android devices using native APIs. 
The framework collects **semi-exhaustively** the **maximum** amount of information available on a device **without requiring special permissions.**
It achieves this by combining three extraction techniques: **execution of shell commands**, **invocation of Android APIs via Java reflection**, and **exploration of content provider values**.
The execution of the collection process on a single device produces a large fingerprint containing on average approximately **200,000 attributes**.

### Experiments

#### Experiment 1: Running data collection on a single device
- **Time**: ~5 minutes
- **Storage**: ~20 MB per collected fingerprint

This experiment demonstrates how to run the EXADPrinter fingerprint collection process on a single Android device (either a physical device or an emulator).
- **Steps**
   1. Download the application
   2. Install the application on the device:
   ```
   adb install -r com.amiunique.amiuniqueapp
   ```
   3. Launch the application while providing your API_BASE_URL:
   ```
   adb shell am start \
   -n "com.amiunique.amiuniqueapp/.presentation.MainActivity"\
   --es API_END_POINT "API_BASE_URL"
   ```

> The API request is defined in [`FingerprintApi.kt`](./app/src/main/java/com/amiunique/amiuniqueapp/network/FingerprintApi.kt). By default, the application sends fingerprints to: `<FALLBACK_URL>/saveFP/`. To receive fingerprints, your backend must implement the same API schema.

- **Expected Result**
When the application starts, it automatically collects device attributes using the EXADPrinter library.
After execution, a fingerprint containing a large set of device attributes will be sent to the configured API endpoint.

#### Experiment 2: Running data collection using automation (optional)

- **Time**: depends on the number of selected devices
Example: ~1 hour for 10 devices
- **Storage**: ~20 MB per fingerprint

This experiment demonstrates how to automate fingerprint collection across multiple real Android devices using the BrowserStack App Automate platform.

- **Steps**
   1. Create a [BrowserStack](https://www.browserstack.com/) account (a free trial typically provides limited testing minutes).
   2. Retrieve your BrowserStack credentials from your account dashboard:
   ```
   BROWSERSTACK_USERNAME
   BROWSERSTACK_ACCESS_KEY
   ```
   3. Upload [`exadprinterDemoApp.apk`](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/DataCollectionSetup/exadprinterDemoApp.apk) application to [BrowserStack](https://www.browserstack.com/docs/app-automate/appium/set-up-test-env/upload-and-manage-apps?fw-lang=python%2Fpytest) and get the APP_URL. 
   ```
   APP_URL=bs://<app-id>
   ```
   4. Configure the automation pipeline by editing [pipeline.sh](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/DataCollectionSetup/pipeline.sh) like that: 
   ```
   API_BASE_URL= # server receiving fingerprints, if no API_BASE_URL is provided fingerprints will be sent to our servers.
   APP_URL= # is the URL of the `exadprinterDemoApp.apk`
   BROWSERSTACK_USERNAME=
   BROWSERSTACK_ACCESS_KEY=
   ```
- The script will:
   1. create a BrowserStack session for each configured device,
   2. install the EXADPrinter demo application,
   3. execute fingerprint collection twice for each device,
   3. send collected fingerprints to the configured API endpoint.

The list of devices used during the experiment is defined in [`capabilities.json`](https://github.com/AmIUniqueTools/EXADPrinterPipelineExample/blob/master/DataCollectionSetup/capabilities.json)

- **Expected Result**
After execution, fingerprints from multiple Android devices will be sent to the configured API endpoint.
These fingerprints can then be processed using the parsing and cleaning pipeline provided in the repository.

#### Experiment 3: Processing the dummy dataset
- **Time**: ~10 min 
- **Storage**: <10 GB

This experiment demonstrates the fingerprint parsing and cleaning pipeline using the provided dummy dataset. 
The dummy dataset contains **22** fingerprints collected from **11** real Android devices provided by Browserstack.
These fingerprints reproduce the expected data format while preserving user privacy.

- **Steps**
   1. Launch the Jupyter notebook:
   ```
   jupyter notebook data_cleaning_pipeline.ipynb
   ```
   2. Execute the notebook cells sequentially.
   3. The notebook will:
      - load archive file fingerprints from DUMMY_DATA/,
      - parse fingerprint attributes using the `fingerprint_parser` module,
      - apply cleaning rules to normalize attributes,
      - generate processed fingerprints.
   4. The cleaned results will be stored in:
   ```
   DUMMY_DATA_PREPARED/
   DUMMY_DATA_STRUCTURE/
   ```
- **Expected Result**
After execution, the pipeline produces structured fingerprint datasets that illustrate how raw EXADPrinter fingerprints are parsed and cleaned before analysis.

## Limitations

The artifact does not include **the original datasets** collected from **real participants** during the study. 
These datasets contain device fingerprints collected from participants **who provided their consent** and may include potentially sensitive information. 
Therefore, for ethical and privacy reasons, these datasets cannot be publicly shared.

As a consequence, the **full experimental results reported** in the paper (e.g., some tables, figures, and statistical analyses) cannot be reproduced **exactly** using the artifact.

Instead, the artifact includes:
- **EXADPrinter Android library** that implements the complete data collection framework, which constitutes the main contribution of the paper.
- **AmIUnique** Android application used during the experiments and deployed in Google Play Store.
- An automation script used to run data collection.
- Dummy datasets that reproduce the structure and format of the real data.

These dummy datasets allow reviewers to execute the data cleaning and parsing pipeline and verify that the processing scripts function correctly.

Reviewers can also run their own data collection experiments using the provided framework (e.g., on their own Android devices or through platforms such as BrowserStack). This allows them to validate the functionality of the artifact and confirm that the framework successfully collects device fingerprints as described in the paper.

For these reasons, we believe the artifact enables a meaningful evaluation for the Functional badge.
