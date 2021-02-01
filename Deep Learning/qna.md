# Week 1: 
- ML started from 1940
- Perception - 1958 (Rosenblatt) 
- why AI is successful
    - accessible powerful hardware
    - programming language and libraries
    - data 
- Learning as optimization: from given data D find the best data representation from a given class of representations that minimizes given learning objective (loss).  
    - min f(x:D)
- Learning tasks
    - supervised: input and output and computer do prediction we minimize prediction error
    - unsupervised: we look for data structure, reconstruction error, compression rate. 
    - reinforcement: agent, environment, policy, action, reward. 
- Component Deep learning: 
    - a lot of data 
    - computational performance 
    - models and algorithms 
- representation learning 
    - automatically extract features 
- Why ML useage Log: negetive log-lielihood function. 
    - max f(x) = min{-f(x)} = doens't change optimial 
    - long mul = sum of log

- Logistic Rgression: 
    [allwoes us to classify opbjects]
    - update: 
- Activation: 
    - sigmoid: squize values into 0 to 1. 
    - ReLU: negative value to zero 
    - softrmax: for multiple classess 
- gradient: vector of derivaties (first order derivatives of negetive log likelehood)
- Gradient descent vs Stochastic gradient decscent: more faster sometime. To save memory SGD plays good role in DL. 
- Chain rule to calculate gradients wrt all weights. 

- a single node inside hidden layer is called neuron. 
- Fully connected network: 
    - a linear layer with a non-linearity : h = f(Wx)

- Vanishing gradient problem
    - sigmoid function creates this issue. 
    - gradient of sigmoid is 1 - sigmoid(x), which mamkes gradients close to zero. 


## Backpropagetaion 
- chain of perceptraion without non-linearity collups down to single perceptron. 
- to fix this,we can introduct non- linear function 
- binary classificoation can be done sigmoin in output layer. 
- multiclass we can use softmax function [sum to one]

- how do we train a network: 
    - gradient decent 
    - arg min loss(theta)
    - find the point where loss is less in weight space plane 
- loss:
    - loss is a scaler value which tells how good our network is doing. lower the better. 
    - derivative over loss surface.the derivative is the slope of the tangent line at the point on loss. tangent line is the local approximation and slope tell how fast or slow. 
    - for multiple dimention gradient[derivative vector] points out the direction. 
GD: 
    - loop: theta <-  theta - alahpa . delta loss(theta)
        - alpha lerning rate, how big the step would be 
    - SGD: loss over one example per step 
    - mini batch: batch of samples at a time, more terminal  
    - full-batch:
- Backpropgapation is a kind of middle ground between symbolic and numeric gradient descent. 
    - secret ingredient: The chain rule 
    - as we take derivatives, we can treat as linear function. 
    - multivarient chain rule 
    - coputational graph. 
    - iterating the chain rule. 
    - break computation up into a sequence of operations 
    - workout local derivatives symbolically
    - computer global derivatives numerically 
    - only source of inaccuracy is the numerica computation 
    - much faster than symbolic differican. 


- Linear algebra 
    - easy to describe
    - computation becomes fast my maxtrix multiplication. 
- vector: simpler, easier.
- backprob always start with scaler value loss. 

- Tensor backpropagation 
    - workout scalar derivatives first then vectorize
    - apply chainrule stp by step 

- Autograd: automatic differentiation is the whole backpropagation algorithm 
- tensors - row-major ordering: in higher dimeentnal further to the right are always scanned before the dimentions to their left. meamory cheap by reshpe [shape to flat shape], size error is common 
- 

- backpropagation with autgrad: 
    - build a computation graph 
    - perform forward pass, bottom up from levaves 
    - traver the tree backwards bredth first
    - call backward for each opnode
    - add computaiton gradient to the tensor nodes. 

# Week 2:
## Convolution 
- problem with sound: noise, variations, fragmenta missing
- MLP failing for 1D sound: 
    - lots of trainin data would needed
    - the mlp does not explicity ook at the order of the inputs
    - we need very larger mlp with ots of wieths 
    - will not converge 
- solution: 
    - select a feature of sound for example amplitude [normalized, features close are more important than far away]
    - detect silence [which is pattern - silence neuron]
- Filters: 
    - acts as the feature extrator
    - filtr can be3 used fat all location to detec silence
    - sliding a filtr over all posiotn is convoluving
- Convulution operation: 
    - sliding a filter over all position. 
    - output of the convolution operattor is a vector
    - convolution is translation equivarient 
    - this operation can be understood as a small MNLP
    - in practice, con. kernels are learned. 
- how filter/karnel is learned
    - update filter weights based on loss. cross-correlation for classifcation
    - gradient utilized to update kernet weights. 
    - weights are shared across the entire inputs. 
- advantages: 
    - smaller and paramerter efficientcy 
    - data efficiency 
    - generalization improvments 
    - as many filter as needed
    - output volume is matrix 
    - add padding to avoid boundery loss
- problem: 
    - multiple filter - matrix output 
    - next layer: 
    - boundary loss - padding 
    - dimention down. - take large steps, pooling [goes over the data similar to convolutin applies deterministric function like max and usauly has stide]


- AlexNet 
    - GPU for compution convolution 
    - achived a top-5 error of 15.3 on a dataset with 1000 catagories 

## Deep Learning in Practice
Q: what are the Basic process of training a model?
- plan, get some data
- debug the model 
- tune the hyper parameter
- publish 

Q: how should we split the data?
- The size of test set is more important than training set. 
- size of test and validation set should be same 
- idea size of test set is 10,000
- use the test set just once

Q: Confidence interval in test set?
- 

Q: What are the type of training leakage: 
- test leakage:
    - Preprocessing before splitting. 
    - related data for validation and training 
- memory leakage:
    - running loss may get patched in backtracking, to avoid that take loss.item()
- NaN loss: 
    - NaN, inf or -inf [this may happen for high learning rate]
    - avoid asset not x.isnan().any()
    - avoid asset not x.isinf().any()
- No learning: 
    - check few learning 
    - check gradients x.retain_grad()
    - check: grad == None backprop didn't reach
    - check: grad ==0.0 backprop bisited, but the gradient died. 

Q: Debugging difficulties: 
- fails at runtime: shape error
    - use asset function to avoid this fail. 
- fail silently: due to broadcasting 
- may not fail at all


## Why does any of this work at all 
Q: Why does deep learning works so well?
- Randomization, 
- Double descent 
- Lottery ticket 

## Understanding Optimizers 
Q: What are the main topics for optimizers?
### Newton' method
second order optimization, conditioning is known as Newton's method. 
- NxN matrix 
- Accuracy estimation (10k batch size)
- Extra backward pass for each elements of the gradient
- inversion of the matrix. 
Q: what does newton's method is good for?
- help us understand and analyse our problem. 
- parameter interactions 
- curvature information 
### Momentum 
Q: how to explain momentum in natural language?
- heavy ball: gradient acts not like a direction but like a force. 
    -  force adds velocity and velocity adds to the position. 
    - rolls out of local minima 
    - accelerates repeating directions. 
- gradient acceleration: 
- Exponential moving average. momentum m as be seen as exponential moving average of the recently observed gradient. it means doing one step of gradient descent for the loss over a mini batch. 
### Adam 
- No convergence guarentees
- pre-parameter tuning of behaviour
- default optimizer for most DL settings. 
Q: Best practices for optimizers in NN
- start with adam with learning rate between 0.1 and 0.00001
- consider plan SGD with momentum if adam doesn't work. 

Q: What are the new optimizers: 
- Rectified Adam: adam must underestimate the early-training variance. 
- Look Ahead: two models, w and v. train w and periodically push w towards v. 
- LARS: Tune the learning rate per layer
- LAMB: tune per layer with LARs, updated with Adam 
## The bag of tricks 
### Initialization 
Q: why do we need to initialize weights and biases?  
if weights are near zero training starts very slow. if gradients blow up we get NaN.  

Q: what is the best practice for initialization?  
- initial weights should be randomly chosen in a way that keeps gradients consistent through the network. We also need to consider the activation function used. 
    - Sigmoid: if the value going in to sigmoid is close enough to zero, we still end up with a derivative of only one quarter???????  
    - ReLU: the relu activation: chance of dead neuron, can be avoided by normalization.
- Layer weights such that input and output had mean 0 and covariance I (uniform [0,1] is fine too). 
- He initialization: for relu we expect to lose half our output so we need to change covariance c to double the output variance. 
### Normalization
- Normalize the data using mean and standard deviation. 
- batch normalization: mean over batch, variance over batch 
- Layer, instance and group normalization. 






### Regularization

Q: Characteristics of L2: 
- Applying L2 loss is like tipping the bowl slightly to the right, so we shift the lowest point in a direction. 
- It adds a penalty to the loss for models with larger weights. 
- square the weights 

Q: Characteristics of L1:  
- L1 loss is like using square bowl, it has grooves along the dimensions.  
- if a weight is close to zero, its more likely to get set entirely to zero.  

Q: what are the difference between L1 and L2 regularization?  
L1 regularization promotes sparsity and L2 often uses squared norm of weight as penalty term. L2 is simpler to implement and calculate.   

Q: What is dropout?
dropout is a regularization trick for neural networks. Durning training some of the hidden and input nodes are removed with probability of p. This prevent network to overfit. while using the model it should activate all neurons and should correct by factor of p. 
Q: What is weight decay?
decaying the weight with a parameter gamma w = w - gamma * w. similar to L2 but only for vanilla SGD.  
Q: What is data augmentation?  
change the input data so that network get force to learn features of dataset and to reduce over fitting.   
- for images mainly. 
- rotate, flipping, adding noise, masking portions. 



# Week 3
## Sequential data: 
### Learning from Sequence 
* 1-D sequence: stock price over time, traffic to a webserver etc. 
* n-Dim: closing index of AEX and the FTSE100 over time 
* Symbolic: language as a sequence. 

Q: what is walk forward validation: 
- keep the data aligned in time and test the model at various points. training on past only and using small stretch afterward as validation. 

### Seq in Deep learning 
very versatile: S2S, L2S, S2L, autoreegressive raining, teaching. 

Q: what is S2S layers?
- Input: length t-seq of vectors 
- output: length t-seq of vectors 
- property: same weights can be applied to seq of different length.  

Q: MLP vs Repeated MLP 
- a fully connected would simply connect every input with every output. 
- each batch is connected with singe neuron with same weight.  

Q: Causal vs non-causal 
- causal: generally s2S can only look backward in the input seq. 
- in non-causal s2s models are prfereable as they can look at the whole sequence to produce their output.  

Q: One-hot vectors: 
- its called one hot because in the vector in only one place it has value or know as hot.  

Q: What is embeddings: 
- combine embeddings in some talk and learn ex by backprobp ????   

Q: what is padding?
- to create batches of uniform lenght we can pad our sequence with zeros.  

Q: what is packing?
- data will be sorted in a single sequnce that intervleaves the diffferent instances in the batch. this can be implimented using sliding window.  

Q: types of sequencial models?
1. Sequence to sequence
2. sequence to model 
3. lable to sequence 
4. lable + seq to sequence 

Q: what is pos tagging?
- parts of speech tagging. tag each word in sentence with its grammatrical category. 

Q: what is Masking?
- using masked for padded part of the sequence while computing loss.  

Q: Autoregressive model?
- only for causal model 
- feed it some sequnce to set the target as the same sequence. shifted one token to the left. 
- An autoregressive (AR) model predicts future behavior based on past behavior.

Q: What is global pooling?
- for S2L setting. we get a sequnce as input and single output. this can be done by softmax vector or simply an output vector if we need multiple output. 
- A global pooling layer sums, averages or maxes across the time and results in a single vector 


- RNN: 
    - any nn that has cycle 
    - RNN are sequence to sequence 
    - causal 
    - potentially unbounded memory. [practically short]
    - slow because of layer by layer calculation 
    - vanishing gradient prblem with sigmoid 
- LSTM: 
    - long short term memory 
    - selctive forget 
    -  first succesfull deep neural network 


- Elman: fully connected network plus a input extended by three nodes to with the hidden layer is coppied 
- how to train RNN: 
    - backpropagate through time: remember the history as a computation graph. 
    - untrollin a network 

# Week 4
# Graph 
- knowlege graphs: Cyc, Freebase, DBPedia, Wikidata, YAGO, Thomson Reuters, Microsoft Satori, Yahoo KG, Springer. 
- types of graphs: undirected, selfloop, multigraph, directed, edges, nodes, RDF(ontology), weights. 
- For a given graph, you should know whether it has:
    ○ Self loops or not
    ○ Multigraph or not
    ○ Directed/undirected/mix
    ○ Edge labels (unique?)
    ○ Node labels (unique?)
    ○ Properties on edges (also called qualifiers)
        ■ Edge weights
- Embbeding: 
    - low dimention: way lower than original data
    - representation: corresponding to original data
    - word, images, audio, graph 
    - Imgaes: smile, background, gender, baldness 
    - Words: 
        - You shall know a word by the company it keeps.
        - If units of text have similar vectors in a text frequency matrix, then they tend to have similar meaning
        - One vector representation for each word w2v 
- Embedding graph:
    - One vector for each entity
    - Preserve the information
        - Preserve topology: Keep neighbours close together
        - Preserve Similarity: Keep similar nodes close together
    - Unsupervised
    - Efficient computation
    - Low dimensional representation
- Usage of graphs in machine learning: 
    - recomendation
    - classification, regression, clusterting of nodes/edges
    - document modeling 
    - link prediction/ find errors 
    - link text with semi structured knowledged 
- Tradinal challenges
    - problem with scale 
    - manual feature engeniearning 

- Improve original data
    ● Knowledge Graph Completion
    ● Link Prediction
    ● Anomaly Detection
- Downstream ML Tasks
        ● Classification/Regressio n/Clustering/K-NN
        Then used as part of a larger process
        ○ QA/dialog systems ○ Translation
        ○ Image segmentation






# Week 6 
## Self attention 
Q: what is RNN?  
A: RNN is any neural network which has cycle on it.  

Q: What are properties of sequence to sequence layer 
A: 
- Defining: can handle sequence of different length.  
- Versatile: s2l, l2s, s2s and auto-regressive training. 
- Casual: casual models can only look backwards 

Q: Difference between RNN,CNN and Self Attention: 
RNN: 
- can look back indefinitely far back in sequence. 
- sequential processing is slow 
CNN: 
- has limited access to look back in sequence 
- Compute output in parallel, hence is its fast 
Self Attention: 
- parallel processing with potential infinite memory. 

Q: What is self attention: 
Sequence to sequence layer with parallel computation, perfect long-term memory.  

Q: Properties of self attention
- output is weighted sum of input
- weights are not parameters, only derived from input 
- input and output size is always same
- 'Projection Layer' can be used to transform different layer. 

Q: What is a Bells and Whistles self attention?
- scaled dot product [divide the dot product with √k, k=number of dim]
- key, value and query transformation 
    - key: the input vector that the query is matched against 
    - value: the vector used in weighted sum and ultimately provides the output 
    - query: the input vector that corresponds with current output, matched against every other inputs. 
- multi-head attention [he input sequence down to several lower dimensional sequences, and apply a separate low- dimensional self attention to each of these. After this, we concatenate their outputs, and apply another linear transformation]


Q: What are the basic tricks of transfer learning?  
- Get a large model to classify image or NL: ImgNet, BERT, GPT-e, MobileNet, ResNet
- Remove the last layer
- Add a new classification layer, train on this layer
- add a custom input layer 
[gradients requires only for last layer]



## how to make AI research to increase power efficient 
momory used by 
- Large memory
- Computation
solution: 
- compression network. mean less neurons by pruning 
- Quantization: 
    - lower the bit of the inputs 
    - memory usage reduce 
    - power consumption reduces
    - Latency reduce 
    - Silicon area??
    - find the tradeoff between performance and cost
- how quantization works?
    - scaling vector and 8bit value 
    - Semmentric quantization
    - Asymmetric quantization 

- Simulate quntization
    - quantization is generally simulate in floating point instead of actually running in integer math. 
    - no dedicated kernael nescsary 
    - find min/max 
    - round(x-min/s)
    - running errors is small so pc or mobile will be similar. 
    - old networks works fine with quantization. 
- quantization aware trining
    - rounding operation doenst ahve a gradient
    - solution: 
        - redefined gradient op as 'straing-trough'
        - random rounding 

- RQ:
    - No data
    - No back propagation 
    - No architecture changes 
- rounding method: 
    - stochastic(best) round up and down. 
    - how to find this: 
        - taylor serise expansion of loss: jakovian and hassine matrix 
        