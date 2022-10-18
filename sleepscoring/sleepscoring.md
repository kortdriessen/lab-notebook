# Sleepscoring Instructions

To sleepscore a recording, we need to have a few basic things: 

1. A machine with the visbrain 'sleepscore' program installed, per instructions [here](https://github.com/CSC-UW/sleepscore).
2. A recording that needs scoring, which typically includes EEG + EMG data, and often LFP data. 
3. A config file which points to the recording to be scored, and specifies all relevant information. 


## Basic Steps for Scoring
1. Open a terminal, and activate the sleepscoring environment:
```python
conda activate sleepscore
```
2. Navigate to the config file you want to score, and copy its path.
3. Then, from the terminal with your sleepscore environment activated, enter:

```python
python -m sleepscore <path-to-config-file>
```

## Using the Sleepscore Program
A few basic parameters to get started: 

- A good starting point for window settings:
    - window size = 24 sec.
    - step size = 24 sec.
    - scoring window = 4 sec.
- Set the amplitudes on all channels
- Set the spectrogram to an EEG channel (parietal is best)
- Set Rule to seconds
- Save the gui config so you don't have to do this every time (should only need to save 1 gui-config per subject)
    - file -> save -> GUI config


## Naming Conventions
There are a few important naming conventions for saving the config files and hypnograms

### Config Files:
```python
SUBJECT_sleepscore-config_recording-chunk
```
### Hypnograms:
```python
hypno_recording_chunk
```