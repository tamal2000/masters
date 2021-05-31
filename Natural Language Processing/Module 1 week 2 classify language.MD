# Classify Language

## Learning Goals
1. Explain a standard supervised machine learning setup using the correct terminology. 
2. Evaluate and interpret the output of a classifier with the metrics accuracy, precision, recall, and f-measure based on a confusion matrix. (You should be able to calculate the metrics, explain what they measure, compare and interpret the output of different systems)
3. Explain the distinction between macro-average and weighted F1
4. Conceptually explain the functionality of a feed-forward network using the correct terminology. 
5. Recognize the matrix notation for neural networks. 
6. Explain the difference between single-label classification and sequence-to-sequence generation. 
7. Motivate why sequence processing is important in NLP. 
8. Discuss the difference between fee-forward and recurrent neural networks. 
9. Conceptually explain the calculation of the hidden states in a recurrent neural network. 
10. Explain the concept of parameter sharing. 


# Shared Tasks
1. Competition: motivate the best researchers 
2. Comparison: evaluate the performance of different systems
3. Reproducibility: researchers need to share details about their system

# Single Label Classification 
- input: a word, word pair, sentence, sentence pair, paragraph, document. 
- output: a single Label 
- Class:
    - Binary Class: relevant/not relevant, yes/no, true/false
    - Multi Class: Topics, sentiment, ratings

# Multi label Classification
- input: a word, word pair, sentence, sentence pair, paragraph, document. 
- output: multiple labels

# Classifier Development
1. Development and training: 
    - Represent the input(training data)
    - Develop a model
    - train the model
2. Evaluation 
    - Represent the input (development data)
    - Make predictions with trained model 
    - Evaluate the prediction
3. Improvement
    - modify model, or
    - input representation, 
    - regularization to avoid overfitting

# Test Classifier
1. Freeze Model
2. Evaluation
3. Interpretation

# Evaluation
- Accuracy = correct prediction / number of data
Confusion Matrix: 
xx      Pred Pos, Pred Neg  
Act Pos   TP    ,   FN   
ACt Neg   FP    ,   TN  

- Precision: How often is my prediction correct?
p = TP/(TP+FP)
- Recall: How many of the TP do I find 
R = TP/(TP + FN)

- Precision Vs Recall
    - high Precision: Less mistake
    - High REcall: Less miss a case
- F1-Measure: harmonic mean 
    F1 = 2*(Precision*Recall)/(Precision + Recall)

# Baselines 
1. Random Baseline: randomly assign a label to each instance 
2. Majority Baseline: determine majority class 

# Comparing System
- Calculate the F1-score

# Evaluation for multiple classes 
- Calculate precision and recall for every class separately
- Average the results over all classes 
    - Macro- average: does not take class imbalance into account
    - Weighted: average over class, weighted by class size

# Classification with Feed forward networks
- Input: a sentence as a vector x with n dimensions 
- x: number of x in an experimental choice
- output: a probability distribution over all language in the training set
    - softmax function over the output vector
- Hidden States: The network learns abstractions over the input to extract the relevant information for prediction. 
    - h = f(Wx), h = f(Wx+b)
    - h is a vector, W is a weight, f is a non linear activation function
    - b is bias
- Forward Propagation
    - h = f(Wx), o = g(Uh)
    - x,h,o are vectors
    - f and g are non linear functions 
- Notation: 
- h = f(Wx + b ) 
    - h_1 = f(w_11*0.2 + w_12 * 0.4, w13f * 0.1 + b) = f (∑W_1i * x_i + b)
    - h_j = f(∑W_ji * x_i + b)
- fully connected: all inputs contribute to all hidden units
- Dimensions:
    - x -> 3, h -> 4, o -> 2
    - dimensions of `o` are determined by dataset
    - dimensions of `x` and `h` are experimental choices 
- How do we learn good weights
    1. Start with random initialization 
    2. train the network
        - Calculate the predicted output with current weights 
        - Compare the predictions to the expected output
        - calculate the error 
    3. Adjust the weight relative to 
        - the size of the error 
        - Their contribution to the error 
        - the learning rate. 
    4. Try again, each try is one episode

# Sequence to Sequence Generation
- Feed Forwarding networks works well 
    - if the oder of input input is not relevant
    - if the output decisions are independent. 

- many 2 many, seq 2 seq 
    - POS-Tagging, Named Entity Recognition, len(input) = len(output)
    - machine translation, len(input) ≠ len(output)
- Recurring Neural Network(RNN)
    - are sensitive to word order 
    - can process arbitrarily long sequences 
    - hidden: h_t = f(Wx_t + Vh_t-1)
    - output: o_t = g*(Uh_t)
    -W, V and U are always same (shared weight)
    -  folded RNN: due to shared weight RNN can be folded. The hidden state is often called the activation or the memory. 

- Sequence Classification
    - Many to many 
    - many to one 



# Comprehension Questions
## Classification Language
### Chapter 4: 
- What does a confusion matrix show?
- Why is accuracy not a good metric for text classification?
- What is the difference between precision and recall?
- What does the metric f1 measure?
- Why is macro/micro averaging only necessary for multi-class classification problem? 
- What is the difference between macro and and micro averaging?
- Provide an example of a talk for which macro averaging is more informative than micro averaging and one for the other way around. 
- What is the purpose of a development test set? 
- Which problem is addressed by cross-validation?
- how can representational harms occurs? 

### Chapter 7, 7.0-7.4
- Which role does feature engineering play when training neral network
- What is a neural unit and what does it do?
- What is the role of the activation functions in a neural network?
- What is a feed-forward neural network and when is it fully-connected?
- what are the three steps in the computation by a hidden unit?
- What determines the dimensionality of a weight matrix?
- what is the function of hidden layers?
- what is the function of the output layer?
- what is a softmax function applied to the output signals?

### Chapter 9, intro and 9.2
- What are the limitations of widow-based approaches for processing sequences?
- What is the key difference between feed-forward neural networks and recurrent neural networks?
- What are the advantages of an RNN when processing language?
- How are the outputs of hidden states determined in an RNNs?
- How is an RNN trained?
- What is parameter sharing and what is it purpose in RNNs?
- Explain how a simple RNN is generally used in each of the following task types:
    - Language model
    - sequence labeling
    - sentence classification 