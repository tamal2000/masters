# Deep Learning 
course materials 

## Week 1 
- Components of AI systems: Knowledge representation, knowledge acquisition, learning problems. 
- Learning as Optimization: 
  - optimization algorithm = learning algorithm. 
  - Minimizing `learning objective` (loss) to find the best `data representation` from a given `class of representations` for given `data`. 
  - min<sub>x∈X</sub> ƒ(x; D), x ∈ Y ⊆ X
- Learning tasks 
  - Supervised Learning 
    - distinguish inputs and outputs 
    - prediction 
    - minimize: prediction error 
  - Unsupervised learning 
    - No distinguish of input and outputs 
    - look for data structure/pattern 
    - minimize: reconstruction error, compression rate. 
  - Reinforcement Learning 
    - Agent interact with environment 
    - Learn policy 
    - action is rewarded 
    - maximize: total reward 
## Deep learning  
- Application Areas: 
    - Computer Vision, information retrieval, speech recognition, Natural Language Processing, recommendation systems. 
- Components: 
    - Data, Computational Performance, Model & algorithms 

### Representation Learning: 
- A representation = a set of (abstract) features 
- Deep learning automatically extract features. 
- A hidden Layer = an Abstraction level 
- Good quality features: 
    - Informative, Robust, Invariant/Equivalent
_ Calculation 
    1. Determine p(y|x)
    2. Determine p(D | x)
    3. Check constraints 
    4. find the best solution by minimizing - log p(D | x)
#### Toss a coin
- Bernoulli distribution
- likelihood function: p(D|x) = ∏ P(c | x)
- Optimization problem: 
    - negative log-likelihood function: min - log P(D | x)
        - negative: because max ƒ(x) = min {-ƒ(x)}
        - Logarithm: because log ∏ = ∑ log and optimum is the same. 
### Logistic Regression



# Lecture 5: Sequential data 

**Sequential dat:** Any type of data where order of data matters. dataset as a whole is a sequence, and the instances are ordered.
- time series: sequential data based on change in time 
- Sequency of symbols: time is not relevant. however, order of character or words matters. 

**Forward walking validation:** Train the model with the ordered training data. training approach would be take small portion of data and split in to test and val set. Then increase the size little and repeat the process.

**Sequence to Sequence Layer:** Same layer (same weight) can be applied in sequences of different length. 
- Looking backward: looking into inputs on and before the node and looking into previous nodes of same layers output. 

**One hot vector:** each possible elements are represent in a particular index of a vector. One hat vector hardly used for input to avoid storing a large amount of zeros 

**Embedding:** low dimensional vector which represent high dimensional vectors. similar to one hot vector, but activation is based on pattern rather than index. 

**One-hot vs Embeddings:** not much difference as after multiplying with weight both gives similar results. 

**Padding:** To keep unified shape the instances can be added with zeros which is know as padding. To avoid big outliers the instances can be sorted in to batches and create different length of batch. this will reduce the extra padding and decrease the batch size as we approach to ending. 

**Packing:** Sliding a kernel/window over the sequential data to get same sized instances. its used for RNN and CNN. 

**Sequence-to-sequence:** When the input and output both are sequence of a layer. 

**Masking** padded in put can be avoided while computing the loss by using mask token, this process is know as masking. 

**Global Pooling:** sequence and input and sing output. this can be done by softmax function. Generally the last layer of sequence to sequence network the pooling layer is used. This network is known as sequence to label network.

**Label-to-sequence:** example an image to its description. here a label is the input and sequence of words are the output. 

**label/seq to seq** a sequence and a label are given as input and sequence as output. 




# Week 4
# Generative models Implicit models (GAN)
GANs are not very stable to train, but it provides results fast. 

#### todo: Generative models laten variables 
- log likelihood function 
- can be estimated by Monte Carlo samples [repeat random sampling to get numeric results.]

## Density Network 
- Trining process: 
  - Sample multiple labels 
  - Apply log-sum-exp-trick and backpropagation. 
- Advantages:
  - Non linear 
  - Allows to generate 
- Disadvantages: 
  - needs lots of sample from gaussian distribution. 
  - No analytical solution 
  - fails in high dimension 
  - no straight forward log loss. 
- Implicit distribution 
  - nn that transform noise into images 
  - it defines implicit distribution and defined by dirac's delta 
## GAN 
- structure: 
  - Provide sample z 
  - generate z' 
  - [add a real input layer]
  - determine if its real or not? 
  - learning objective adversarial loss 
- Training: 
  - generate fake image and minimize wrt generator G 
  - take real, fake image and maximize discriminator 
- Adversarial loss 
  - similar to Bernoulli distribution 
  - End with sigmoid function to mimic probability 
  - minimize wrt generator 
  - maximize wrt discriminator   
- Advantages: 
  - non linear 
  - allows to generate 
  - works high dim  
  - learnable loss 
  - implicit models 
- Dis advantages 
  - unstable to train?
  - missing class 
  - no exact likelihood 
  - no good way to quantify assessment 
- Wassertein GAN: 
  - earth mover distance 
  - discriminator is 1- lipchitz function 
  - clip weights 
  - stable training but problem remains

# Week 5 
## Reinforcement Learning 
- Train __agent__ to __act__ in an __environment__ by maximizing __reward__
- DRL: __Agent__ uses neural network ___policy___ 
- Components: 
  - State: s<sub>t</sub>
  - Action: a<sub>t</sub>
  - reward: r<sub>t</sub>
  - Trajectories, : full rollout of the agent interacting with the environment and receiving rewards. it starts with initial state s_0 to end state s_T
- Simple Deep RL settings: 
  - policy network, π<sub>θ</sub>(a|s)
  - episodic, online, model-free 
  - Gradient estimation focus. 
- Markov decision process (MDP)
  - p(𝜏|𝜃) = p(s_0) 𝛱 𝜋_𝜃(a_t|s_t) p(s_t+1, r_t+1 | s_t, a_t)
  - p(s_0): normal distribution of initial state  
  - 𝛱 𝜋_𝜃(a_t|s_t): policy 
  - p(s_t+1, r_t+1 | s_t, a_t): State transition distribution  





- Gradient of log probability of trajectory is equal to sum over all time steps of the log policy probability. 

