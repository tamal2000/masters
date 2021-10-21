### Time domain
derive feature in time domain
- numerical: 
    - numerical attribute in a certain window. lambda = 1 
    - temporal ordering 
    - proper value in window - mean value. max, sd etc.  
- categorical data
    - succession, b 
    - co-occurrence,c 
    - how to find the patterns 
        - notion of support 
        - what fraction of all time points does the pattern occur. 
- pattern generation 
    - frequent enough. 
    - expand to more complex pattern 
#### Mixed Data 
combination of numerical and categorical data. Categorical values form numerical data using pattern finding algo. 
    1.  certain range are known that can be used to identify categorical values. 
    2. only numerical data without an interpretation of what the values mean in specific context. 
        - can be using by changing the slope. increasing, decreasing threshold. 

### Frequency Domain 
using frequency data to identify activity. 
- activity pattern in a window size with periodicity 

#### Fourier Transformation 
any sequence of measurements can be represented by combination of sinusoid functions with different frequencies.   
    - from one period within window 
    - certain base frequency 
    - multiple k of base frequency
    - Nsec - how many data points per sec 
    - f(k) = k/ (lambda +1)/Nsec = K.Nsec/ labda + 1
    
**Discrete Fourier Transform(DFT)'** assumptions - discrete time and finite number of measurements. 
    - k is a natural number, higher the value of K, higher the frequency of the signal. 
    - number of points in a second to find k. 
    - the amplitude of frequency i in the window. 
#### Features in Frequency Domain 
- Amplitude: is associated with each of the relevant frequencies  that are part of time window. 
    - frequency with highest amplitude. gives an indication of the most important frequency in the windows under consideration. 
    - frequency with weighted signal average. average frequency in the window. computed by multiplying frequencies with their amplitude and normalizing them by the total sum of the amplitudes. 
    - Power spectral entropy: normalize the values in the total sum of 1 to get probability density function. then compute the entropy via standard entropy calculation. 
    - energy, skewness. 

### Features for Unstructured Data
using ML for getting features from unstructured data. below are the process for text based data. 
- Preprocessing: 
    - Tokenization 
    - Lower case 
    - Stemming
    - Stop word removal. 
- Bag of words: n-grams of words. n represents the number of words consider as a single unit. 
- TF-IDF: Term Frequency inverse document frequency. takes in account how unique the n-grams are. 
- Topic Modeling: extract high-level topics from the set of text. Latent Dirichlet Allocation (LDA). find the probabilities of the words associated with the topics.  


### Case Study 