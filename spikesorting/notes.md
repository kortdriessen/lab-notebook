
12/8/2022
- Default thresholds are going to be [4, 10, 2] - then, if it looks like a lot of spikes are being missed or not counted properly, will adjust the middle parameter downward. 

12/23/2022:
- default end times for spikesorting will be the end_time field of master_rec_quality spreadsheet

OFF PERIOD ANALYSIS:
2/17/23 --> including the dark period does NOT affect the detected OFF periods during the light period AT ALL. Therefore, the general principle should be to run the detection on as much data per recording as is available (i.e. be rate-limited in how much OFF-detection one does by the availability of a hypnogram to cover the entire recording [and thus segment out all of the NREM in a recording])
