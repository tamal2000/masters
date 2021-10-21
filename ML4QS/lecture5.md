# Fundamentals of Supervised Learning
a conceptual and mathematical basics of supervised learning

## Topics
- Learning Process and Elements 
	- Unknown target function 
	- Observed Data
	- Error Measure
	- Hypothesis set and Learning Machine 
	- Model selection and Evaluation 
- Learning Theory 
	- PAC Learnability 
	- VC-Dimension and VC-Bound
	- Implications 

## Learning Process and Elements 
A computer program is said to learn from experience E with respect to some class of tasks T and performance P, if its performance at tasks in T improves with E.
Two main ingredient of learning 
	1. Task, T - predict glucose level 
	2. Historical data, E - past measurements on temporal evolution of glucose level 
Additional ingredient
	3. goal,P - Measure performance, error analysis. 

### unknown Target Function
**Functional relationship:** that machine should learn many similarities with inferential stats. 
	- f: X -> y 
	- deterministic target function 
**source of noise: **
	- input error: 
	- output error: factor that influence the target 
**Unknown conditional target:** 
	- P(y|x) probability distribution of y assuming that x is fixed, and add some noise that is generate from a noise distribution. 
	- unknown input distribution: p(x), 
	- Using join distribution = p(x,y) = p(y|x) p(x)

### Observe Data
- Dataset help us to learn unknown target distribution P(y|x)
- split the observe data into training dataset, test, and 
- train data is used to find the unknown function 
- test data is used for valuating the function. Its important that the test dataset is kept separate from the learning process.
- Unbalanced: when class is skewed to one particular one
- Over fitting: way to fix unbalanced class
- validation dataset: the dataset that is used during the training for evaluation. 

### Error Measure
- risk function: E(f,h): how far apart a candidate function h is from the target unknown function f. 
- loss function: e(f(x), h(x)): measure the distance between same points. 

# Lecture 
- Fundamentals 
	- Machine can learn 
		- task, T
		- historical data, E
		- performance improvement, P
	- more data should improve learning 
	- Supervised learning: f(x -y) find the function which represent experience with target
	- Not like to be derterministic, due to 
		- measurement errors 
		- noisy target 
	- so probabilistic function. p(X|y)
	- probabilistic distribution of observation p(x) 

- Observed data 
	- training - for training, validation - for tunning parameters, test - evaluate model
	- class balance 
	- overfitting to fix skewed data
	- cross validation 
- Error Measure 
	- risk function: how far h from f.
	- loss: compute the distance per point e(f(x), h(x))
	- can we compute the error functions - NO, we can only assume or approximate. 
	- In sample error: error from training set
	- out sample error: all other errors 
- Hypothesis:
	- we try to minimize in sample error. f' = argmin E_in(h)
- Model selection
	- lowest in-sample errors on validation set 
	- careful of overfitting
- PAC 
	- we can't find perfect model 
	- minimize in sample error to minimize outer sample error 
	- probability approximately correct. 
	- For M hypothesis in in sample error < out sample error. 
	- what the eror rate, delta = 0 [full truth], delta = 0.005 [95% error rate]
	- E out < E in + sqrt(1/2N log (2m/g))
- VC 
	- 2^N hypothesis, for binary classification N is dataset
	- represent alls possible labeling the H shatters X. 
	- VC space 3, we can shatter all possible x with a line (H)
	- growth function - measure the maximum number of elements for all possible restrictions h_x. 
- Implications 
	- outer sample can be high when N is low 
	- when increase N, error will increase in sample and decrease outer sample error 
	- more N means more complex h. in and out will decrease with the complexity until a point the out sample will start increasing again. 
- Learning setup 
	- no notion of time setup 
	- 

- Algorithms 
- Case Study 