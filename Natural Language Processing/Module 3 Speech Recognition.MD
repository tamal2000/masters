# Speech Recognition 

## HMM POS Tagging
- HMM: Hidden Markov Model to apply it to part of speech tagging 
- HMM is a probabilistic sequence model. Given a sequence of units it computes the probability distribution over possible sequence of labels and chooses the best label sequence. 
- Markov chain: is a model that tell us something about the probabilities of sequences of random variables, states, each of which can take on values from some set. 


Acoustic model: Models baed on sequences of acoustic feature that form phonemes. modeling a sequence of feature vectors given a sequence of phones instead of words.

pronunciation lexicon: models sequence of phonemes that form words. A pronunciation model can use tables to convert words to phones.

The language model: models sequence of words that form sentences.  likelihood of the word sequence

The bias model 

ASR: The primary objective of speech recognition is to build a statistical model to infer the text sequences W from a sequence of feature vectors X 

HMM:   
input  
- Acoustic feature extraction/MEL frequency cepstral coefficient MFCC - MEL - preemphasis boost the amount of engegy iin the high frequencies.
- Windowing involves the slicing of the audio waveform into sliding frames. 
- By combining the acoustic model and the language model, we search for the text sequence with the maximum likelihood.
- 
