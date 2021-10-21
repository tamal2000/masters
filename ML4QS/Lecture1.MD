# Introduction and Basics of Sensory Data 
## Lecture 1
### 31 May 2021 
**Topics:** Analyzing sensory data to help human reaching their goals. 
- ML challenges for sensory data. 
- Select ML techniques 
- How to apply selected techniques

### What is Quantified Self 
The quantified self is any individual engaged in the self-tracking of any kind of biological, physical, behavioral, or environmental information. There is a proactive stance toward obtaining information and acting on it. The self-tracking is driving by a certain goal of the individual with a desire to act upon the collected information. 

## Book Summary 
### chapter 1
Performing measurement around one's self, quantifying one's current state, is referred to as the `quantified self`.  
**Definitions:**
- The quantified self is any individual engaged in thes elf-tracking of any kind of biological, physical, behavioral, or environmental information. 
- There is a proactive stance toward obtaining information and acting on it.
- The self-tracking is driven by a certain goal of the individual with a desire to act upon the collected information.

- Types of Measurement:
    - Physical : miles, steps, calories 
    - Diet: calories consumed, fat, carbs, etc.  
    - Psychological: mood, happiness, irritation 
    - Mental: IQ, focus, memory
    - Environmental: Whether, noise, location
    - Stituational:  context, time of day etc. 
    - Socail: influence, karma, role, status.
- reason of usage: 
    - improve health, enhace aspect of life, and new life experience. 
    - self-discipline, self-design, and self-association. 
- Drawbacks:
    - User privacy on sensative date to companies 
    - location information to criminal 
    - increase control by public authorities. 
Use of Machine leaning: Machine learning is to automatically identify patterns from data. 
- Advising the training to make most progress 
- Forecasting running distances based on progress 
- Predict blood glucose level 
- determine when and how to intervence when the moood is going down 
- Finding cluster of location that appear to elevate mood 

Context: 
1. Sensory data noise
2. Missing Measurements 
3. Highly temporal data 
4. enable support intereaction with user ??
5. study using multiple datasets

### Terminalogy
- Data Terminology: 
    - Measurement is one value for an attribute recorded at a specific time point. 
        - numerical
        - categorical: ordinal and nominal 
    - Time serise is a serise of measurements in temporal order. 
- Machine leaning:
    - Supervised learning is the machine learning task of inferring a function from labeled training data.
    - In unsupervised learning, there is no target measure (or label), and the goal is to describe the associations and patterns among the attributes. 
    - Semi-supervised learning is a technique to learn patterns in the form of a function based on labeled and unlabeled training examples.
    - Reinforcement learning tries to find optimal actions in a given situaion so as to maximize a numerical reward that does not immediately come with the action but later in time.

Overview: 
- Part 1:pre processing of the data and feature generation.  
    - Data sources: Web Applications, Smartphone, Wearables
        -  ecological momentary assessment, Usage data, physical sensors, camera. 
    - User of ML: 
        - Other sensors 
        - External data
- Part 2: ml techniques to achieve analytical goals. 
    - Analytical Goals: Prediction/ clustering/ visualization/ reporting 
    - Usage: Derive recommendation, information decisions, Automate decisions, stakeholder comm

## Chapter 2
1. Three causes for substantial differences between the sensory values. 
    - Time step size 
    - Quantization 
    - Sensitivity of the sensor 
2. Four criteria that can play role in deciding on granularity for the measurements of a dataset. 
    - the task, noise level, available memory, cost of storage, computational resources, internet speed, battery life, type of device. 
3. Two task that could be performed on the crowdsignals dataset. 
    - Semi supervised tasked like pattern recognition using SVN and other clustering method.     
    - PCA for error detection to solve physical sensor data errors. https://journalofbigdata.springeropen.com/articles/10.1186/s40537-020-0285-1
### crowdsignals
- dataset collected using an application from both Smartphone and smart watches.
- focus sensors and user labels categoreis 
- fields: sensors, purpose, device, values, time interval, and used 

## Chapter 3: Handling Noise and Missing values 
2. What situations would it be better to apply a distance based outlier detection algorithm over a distribution-based algorithm. 
3. What is computations complexity of the algorimed and how to improve scalability. local outlier factor algorithm. 

### Approaches to handle sensor data noise
1. detect and remove outliers 
2. impute missing values 
3. transform data to identify important part

### Types of sensors 
- accelerometer: change of forces 
- Gyroscope: orientation 
- Magnetometer: earth magnetic field 
