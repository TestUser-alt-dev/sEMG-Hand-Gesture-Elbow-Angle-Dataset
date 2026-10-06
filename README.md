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

This resulted in eight gesture-angle combinations.

Each condition was repeated 30 times.

## sEMG Acquisition

A five-channel sEMG system (IX-BIO8, iWorx) was used for data acquisition.

- Sampling rate: 1,000 Hz
- Number of sEMG channels: 5
- Electrode type: Disposable Ag/AgCl electrodes
- Electrode configuration: Bipolar

The recording channels correspond to the following muscles:

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

Each trial consisted of:

- 2 s rest
- 1 s motion execution
- 2 s rest

Each gesture-angle condition was repeated 30 times.

## File Naming Convention

Each CSV file follows the naming convention:

`[participant]_[elbow angle] [gesture].csv`

Example:

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

### Example Files

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

...
