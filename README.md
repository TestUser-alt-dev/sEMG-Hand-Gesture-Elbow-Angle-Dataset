# sEMG Hand Gesture and Elbow Angle Dataset

This repository contains the surface electromyography (sEMG) dataset used in the study:

**"Simultaneous classification of hand gestures and elbow angles using sEMG signals: a comparison of machine learning performances"**

Published in *Biomedical Engineering Letters* (2026).

## Overview

This dataset was collected to investigate the feasibility of simultaneously classifying hand gestures and elbow angles using surface electromyography (sEMG) signals.

sEMG signals were collected from eight healthy participants while performing four hand gestures at two different elbow angles.

## Participants

- Number of participants: 8
- Male: 5
- Female: 3
- Mean age: 23 ± 2 years
- All participants were right-handed.

For data anonymization, participants are represented using alphabetical identifiers (e.g., `a`, `b`, `c`, ...).

## Experimental Conditions

Four hand gestures were performed:

1. Fist
2. Open hand
3. Wrist pronation
4. Wrist supination

Each gesture was performed at two elbow angles:

- 30°
- 60°

This resulted in a total of eight gesture-angle combinations.

Each condition was repeated 30 times.

## sEMG Acquisition

A five-channel sEMG system (IX-BIO8, iWorx) was used for data acquisition.

- Sampling rate: 1,000 Hz
- Number of sEMG channels: 5
- Electrode type: Disposable Ag/AgCl electrodes
- Electrode configuration: Bipolar

The five recording channels correspond to the following muscles:

| Channel | Muscle |
|---|---|
| Ch 1 | Extensor carpi radialis |
| Ch 2 | Extensor digitorum |
| Ch 3 | Flexor digitorum superficialis |
| Ch 4 | Biceps brachii |
| Ch 5 | Triceps brachii |

The ground electrode was placed near the radial styloid process.

## Experimental Protocol

Participants followed a metronome set at 60 beats/min.

Each trial lasted 5 seconds:

- 2 s: Rest
- 1 s: Motion execution
- 2 s: Rest

Each gesture-angle condition was repeated 30 times.

## File Naming Convention

Each CSV file follows the naming convention:

`[participant]_[elbow angle] [gesture].csv`

For example:

`a_30 fist.csv`

indicates:

- `a`: Participant identifier
- `30`: Elbow angle of 30°
- `fist`: Fist gesture

### Gesture Labels

| File label | Gesture |
|---|---|
| `fist` | Fist |
| `open` | Open hand |
| `pro` | Wrist pronation |
| `extor` | Wrist supination |

### Example File Structure

```text
a_30 extor.csv
a_30 fist.csv
a_30 open.csv
a_30 pro.csv
a_60 extor.csv
a_60 fist.csv
a_60 open.csv
a_60 pro.csv

b_30 extor.csv
b_30 fist.csv
b_30 open.csv
b_30 pro.csv
b_60 extor.csv
b_60 fist.csv
b_60 open.csv
b_60 pro.csv

c_30 extor.csv
...
```

Each participant has eight CSV files corresponding to four hand gestures performed at two elbow angles.

## CSV Data Format

Each CSV file contains eight columns:

| Column | Description |
|---|---|
| `bandpass 1` | Band-pass filtered sEMG signal from Channel 1 |
| `bandpass 2` | Band-pass filtered sEMG signal from Channel 2 |
| `bandpass 3` | Band-pass filtered sEMG signal from Channel 3 |
| `bandpass 4` | Band-pass filtered sEMG signal from Channel 4 |
| `bandpass 5` | Band-pass filtered sEMG signal from Channel 5 |
| `time` | Time information in seconds |
| `onset` | Onset information |
| `mark` | Trial/event marker |

The sampling interval of the `time` column is 0.001 s, corresponding to a sampling frequency of 1,000 Hz.

## Signal Processing

The sEMG signals were preprocessed using:

- 60 Hz notch filter
- 20–450 Hz fourth-order Butterworth band-pass filter

For the analysis reported in the associated paper, the filtered signals were segmented into 2-second (2,000-sample) segments.

Feature extraction was performed using:

- Window size: 200 ms (200 samples)
- Overlap: 50%
- Step size: 100 ms (100 samples)

## Extracted Features

Five time-domain features were extracted from each sEMG channel:

1. Root Mean Square (RMS)
2. Mean Absolute Value (MAV)
3. Waveform Length (WL)
4. Zero Crossings (ZC)
5. Slope Sign Changes (SSC)

Since five features were extracted from five sEMG channels, each analysis window produced a 25-dimensional feature vector.

## Machine Learning Models

The following machine learning models were evaluated in the associated study:

- Random Forest (RF)
- Support Vector Machine (SVM)
- Extreme Gradient Boosting (XGBoost)

Please refer to the associated publication for detailed information regarding signal processing, feature extraction, model configuration, validation procedures, and experimental results.

## Citation

If you use this dataset in your research, please cite:

Lee, S., Kim, J., & Choi, S. (2026).  
**Simultaneous classification of hand gestures and elbow angles using sEMG signals: a comparison of machine learning performances.**  
*Biomedical Engineering Letters*.

DOI: 10.1007/s13534-026-00607-7

## Data Availability

The dataset in this repository is provided for research purposes.

Please cite the associated publication when using this dataset in academic work.

## Contact

For questions regarding the dataset or the associated study, please contact the corresponding author.
