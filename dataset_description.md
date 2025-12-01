# EEG Dataset for ADHD Classification

## Overview
This dataset contains EEG (Electroencephalogram) recordings collected by Shahed University and released in IEEE. It's designed for binary classification between children with ADHD (Attention-Deficit/Hyperactivity Disorder) and healthy control subjects during a visual attention task.

## Dataset Context
The data was collected from 121 children (61 with ADHD and 60 healthy controls) aged 7-12 years, including both boys and girls. The EEG signals were recorded while children performed a visual counting task involving cartoon characters, specifically targeting visual attention deficits common in ADHD.

## Participants

### ADHD Group (n=61)
- Diagnosed by experienced psychiatrist according to DSM-IV criteria
- Had been taking Ritalin for up to 6 months

### Control Group (n=60)
- No history of psychiatric disorders
- No history of epilepsy
- No reports of high-risk behaviors

## Recording Specifications

- **Sampling Frequency**: 128 Hz
- **Number of Channels**: 19
- **Electrode Placement**: 10-20 International System
- **Reference Electrodes**: A1 and A2 (placed on earlobes)
- **Task**: Visual attention task (counting cartoon characters in images)
- **Stimulus**: Images containing 5-16 randomly positioned cartoon characters
- **Recording Duration**: Variable, dependent on child's response speed

## Features/Columns

### EEG Channel Features (19 columns)

These 19 columns represent electrical brain activity measurements (in microvolts) captured from different locations on the scalp using the 10-20 International System. Each channel continuously records brain signals during the visual attention task.

**Channels**: Fz, Cz, Pz, C3, T3, C4, T4, Fp1, Fp2, F3, F4, F7, F8, P3, P4, T5, T6, O1, O2

These channels cover different brain regions including frontal (attention, executive function), central (motor control), temporal (memory, auditory), parietal (spatial processing), and occipital (visual processing) areas.

### Target Variable
- **Class**: Binary classification label indicating diagnosis
  - `ADHD`: Child diagnosed with ADHD
  - `Control`: Healthy control subject

### Identifier
- **ID**: Unique patient identifier linking records to specific participants

## Important Data Structure Note

**Why ~250,000 records from only 121 participants?**

EEG data is recorded as a **time series** at 128 Hz sampling frequency, meaning 128 measurements are captured **per second** for each channel. Here's the breakdown:

- **121 participants** performed the visual counting task
- Each task session lasted several seconds/minutes (depending on child's response speed)
- **Each row = one time point** (1/128th of a second)
- All 19 channels recorded simultaneously at each time point

**Example**: If a child's session lasted 30 seconds:
- 30 seconds × 128 Hz = 3,840 records for that one child
- Multiply across 121 children with varying session lengths = ~250,000 total records

This means the dataset contains **sequential brain activity readings** over time, not independent samples. Each participant contributes hundreds to thousands of time-series data points.

## Brain Region Coverage

- **Frontal regions** (Fp1, Fp2, F3, F4, F7, F8, Fz): Executive function, attention, decision-making
- **Central regions** (C3, C4, Cz): Motor control and sensory processing
- **Temporal regions** (T3, T4, T5, T6, F7, F8): Auditory processing, memory, language
- **Parietal regions** (P3, P4, Pz): Spatial processing, attention, sensory integration
- **Occipital regions** (O1, O2): Visual processing

## Citation

**Authors**: Ali Motie Nasrabadi, Armin Allahverdy, Mehdi Samavati, Mohammad Reza Mohammadi  
**DOI**: 10.21227/rzfh-zn36  
**License**: Creative Commons Attribution

## Data Shape

- **Total Records**: ~250,000 time-series data points
- **Total Participants**: 121 (61 ADHD + 60 Control)
- **Features**: 19 EEG channels + 1 class label + 1 ID
- **Total Columns**: 21
- **Data Type**: Time-series (sequential brain activity measurements at 128 Hz)