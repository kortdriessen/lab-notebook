# General procedure

1. Decide if cluster is noise. If noise, classify as such and move to next. 

2. If cluster is not noise, decide if KS label is correct. 

3. Once cluster has been labelled as good or mua, check for splits and merges

4. Add notes

# Most efficient steps:
1. Start with clusters KS labelled as 'good,' do the general procedure

3. Then sort by number of spikes to get all of the most numerous clusters

3. Then sort by amplitude to get the easy high-amplitude clusters

4. Then run through the rest of the low-count, low-amplitude clusters, not spending too much time on them and with a bias towards calling them noise, or if they look good, merging them. 


Principles: 
1. With KS-labelled 'good' clusters, or clusters with a lot of spikes, err on the side of keeping and making notes
2. With low-count clusters, err on the side of discarding as noise. 
3. You can split on the amplitude view! This is helpful in removing wake-induced artifact!

Phy Gui Arrangement: 
- Waveform view and trace view to their own monitor
- Set TraceView color scheme to cluster group
