- codes always added under the name 'note'
- codes are separated with '/'

e.g. 
```python
:l note frmod_rec/bw
```

- frmod_state
    - firing rate seems clearly modulated by state of animal (i.e. regular oscillations in firing rate that seem to generally track a generic mouse sleep/wake pattern)
- frmod_rec
    - firing rate seems clearly modulated by the recording (i.e. block). Important one to catch, but need to know the lengths of all blocks in the sorting (which is in the subject_info file)
- bw
    - i.e. 'bad waveform' this should be added to a cluster which has a bad waveform, but for some reason we don't want to classify as noise
- gw
    - i.e. 'good waveform' for clusters with particularly good, high-SNR waveforms
- few
    - A cluster that has very few units, but for some reason wanted to keep (e.g. has some interesting modulation or a very good waveform)
- noisy
    - based on amplitude view and firing rate view... basically really hitting up against the noise floor. Also used to implicate a very low-amplitude cluster generally (which would make it closer to the noise floor). 
- merged
    - a cluster that is the result of 1+ merges
- split
    - a cluster that is the result of 1+ splits
- art
    - a cluster that is not worth throwing away as noise, but which has a lot of (usually high-amplitude) artifact around the spikes in the WaveformView. 
- ampdrift
    - cluster that has some amplitude drift (often which coincides w/ recordings)
- pawake
    - 'possible artifact - wake' indicates that the unit seems mostly good and has a good waveform, but is potentially contaminated by artifact during wake - amplitude view is primary judge of this (often firing rate is heavily modulated to be higher in wake as well). 
- ch_x:
    - for a cluster where the channel field is for some reason incorrect. e.g. if a cluster were listed as being on channel-4, but it really were on channel-5, this code would be ch_5.

