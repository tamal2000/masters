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
- 
