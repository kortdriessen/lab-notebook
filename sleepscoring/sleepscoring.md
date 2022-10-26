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
    - step size = window size.
    - scoring window = 4 sec.
- Set the amplitudes on all channels
- Set the spectrogram to an EEG channel (parietal is best)
- Set Rule to seconds
- Save the gui config so you don't have to do this every time (should only need to save 1 gui-config per subject)
    - file -> save -> GUI config

# Major SleepScoring Rules

## 1. Naming Conventions
There are a few important naming conventions for saving the config files and hypnograms

### Config Files:
```python
SUBJECT_sleepscore-config_recording-chunk
```
### Hypnograms:
```python
hypno_recording_chunk
```

## 2. Contiguity
All hypnograms must be contiguous with each other. For any given recording, the end of chunk(n) MUST be the start of chunk(n+1)

## 3. Link Between Hypnograms and Config-Files
All hypnograms must actually reflect the times specified in the config files. If a config file specifies tStart=0, tEnd=7200, the corresponding hypnogram MUST actually reflect that. 

This means that for any hypnogram that is already scored, if the config file is in any way changed, the TIMES must remain the same. Put another way: for any hypnogram that is already scored, do not change the times specified in the corresponding config-file. 

# Decision-Making Principles for SleepScoring
- Data Types
    - The EMG is very helpful... if the EMG is active, the animal is very likely NOT asleep
    - EEG is the best signal to use for sleepscoring. In any ambiguous situation, the EEG wins.
- Arousals During NREM/REM
    - Depending on the animal, arousals can be somewhat frequent during NREM, and are always rare in REM. 
    - IF arousal length clearly <1 sec, do not score out, ignore and count as NREM.
    - IF arousal length clearly between 1 and 4 sec, score it out as Brief Awakening
    - IF arousal length clearly > 4 sec (i.e. larger than a single 4-sec epoch) scored as Wake.
- Possible Transitions
    - W —> NREM
        - Transition to NREM button = 2
    - NREM —> REM
        - Transition to REM button = 3
    - REM —> W
        - Transition-to-wake button = 7
    - NREM —> W
    - Very occasionally you can also get wake directly to REM, but this always is something like REM, then brief period of wake, then back into REM. Never a long period of wake straight into REM without first having NREM. 
