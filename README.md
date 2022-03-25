# Audios Analysis

We would like to show examples of how two differents system affect the pre-processing of the audios. We use this systems at our work presented at [Interspeech 2022](https://www.interspeech2022.org/). All the examples listed here use audios from the [ADreSSo dataset](http://www.homepages.ed.ac.uk/sluzfil/ADReSSo-2021/).


## Voice Activity Detection
For voice activity detection (VAD) we used the pre-trained [Silero model](https://github.com/snakers4/silero-vad). This model outputs a score measuring the probability that speech is present on chunks of 5 seconds shifted by 0.16 seconds across the signal. Speech regions are then determined by comparing this score with a tunable threshold. 

At folder VAD you can find three audios with their correspond TextGrid file. We calculated the speech regions using differents threshold to check their behaviour. The tiers of the TextGrid files correspond to a different threshold. 

## Speech enhancement

At our paper, we experimented with two speech enhancement procedures: loudness normalization and noise reduction. We perform loudness normalization following the [EBU R128 standard](https://www.ebu.ch/files/live/sites/ebu/files/News/2011/r128%255B1%255D.pdf). The normalization is done over sliding windows, which results in experimenter, participant and background noises having similar loudness after processing. This second enhancement procedure is implemented using the [FullSubNet CNN model](https://arxiv.org/abs/2010.15508), which effectively subtracts stationary ambient noise and some of transient noises, but not reverberation. 

At folder "SP-Enhancement" it can be found three examples of audios with their different combination of procedures. The name of the file indicate the order that the systems were apply. 

