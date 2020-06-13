# Lecture 3

## Bayes' Theorem

```
Selfies from a famous celebrity
40% posted only on Instagram (Inst), the rest both on Instagram and Facebook (FB). 70% from only Inst, and 90% posted on both Inst and FB: appear on gossip website.
What is the probability that a random selfie appears on a gossip website?
I = .4,  I & F = .6, I2 = .7 I and F = .9, O = 0.1
Let B ={on gossip site}, A ={inst}, A_compliment  ={selfie on inst and FB}
Computer P(B), we know P(B|A) = 0.7, P(B|A_comp) = 0.9, P(A) = 0.4, P(A_com)=0.6.
selfie from Inst on gossip, P(B ⋂ A) = P(B|A).P(A) = 0.7x0.4 = 0.28
selfie from inst on gossip, P(B ⋂ A_com )  = P(B|A_xom).P(A_com) = 09 x 0.4 = 0.54
Addition rule: P(B) = 0.28 + 0.54 = 0.82  
 ```
**Addition rule for disjoint events (B ∩ A & B ∩ A_compliment):** P(B) = P(B ∩ A) + P (B ∩ A_compliment).  
by `multiplication rule` we get, P(B) = P(B|A).P(A) + (P|A_com).P(A_com)

**Simple Law of total probability** P(B) = P(B|A).P(A) + (P|A_com).P(A_com)  
by adding conditional probability with multiplication rule

`P(A|B) = P(A ∩ B)/P(B) = P(B|A).P(A)/P(B|A).P(A) + (P|A_com).P`  
Note: P(B|A) + P(B_com|A) = 1, but in general (B|A) + P(B|A_com) ≠ 1

```
Example: 0.1% population has a disease. 
disease given positive: 0.98
Not disease given Negative: 0.99
Q: positive, what is the probability of disease?
B = {positive}, A = {disease}, 
B_= {negative}, A_ ={no disease}
P(A|B) = ?
given, (B|A) = 0.98, (B_|A_) =0.99, P(A) = 0.001
so, (B_|A) =0.2, (B|A_) = 0.1 , P(A_) = 0.999
P(A|B) = P(B|A).P(A)/P(B|A).P(A)+P(B|A_).P(A_)= .98 . 0.001/09 . 0.001 + 0.01 . 0.999 = 0.089 = 8.9%
```
### Law of Total Probability 
P(B) = ∑ P(B ⋂ A)  = ∑ P(B|A<sub>i</sub>).P(A<sub>i</sub>)

By applying 'Law of total probability in `Bays' theorem` we get, 


<center><img src="https://render.githubusercontent.com/render/math?math=P(A _r | B) = \frac{P(B|A_{r}) . P(A_{r})}{\sum P(B|A_{i}). P(A_{i}) }"></center>


```{python}
Example: Machine 1,2 and 3 produce 30%, 45% and 25% of all products. Respectively 2%, 3% and 2% there are defective. A randomly selected product is defective. what is the probability it came from machine 2. 
Ai = {machine i made product},
B  = {product defective}, 
we need to find P(A2|B). 
Given,
P(A1) = 0.3, P(A2) = .45, P(A3) = .2,
P(B|A1) = 0.02, P(B|A2) = 0.03, P(B|A3) = 0.02
so, P(B|A1).P(A1) + P(B|A2).P(A2) + P(B|A3)P(A3) = 0.0245. 

from bays' theorem,
P(A2|B) = P(B|A2).P(A2)/ P(B|A1).P(A1) + P(B|A2).P(A2) + P(B|A3)P(A3) = 0.55 

```


## Probability Distribution 

A `Probability distributions` determines all probabilities of possible values of a random variable. Given by a table, formula or graph. 

Outcomes 𝓌 in Ω and the probability measure P determine the probability distribution of X:
<code>P(X = x) = P({w ∈ Ω: X(𝓌) = x})</code> 

- **Random Variable** is a variable that assigns a numerical value to each outcome of probability distribution. *Notation*: X,Y,.... 
  ```
  Example: two coin toss, let the random variable X be the number of heads. 
  Sample Space Ω = {HH,HT,TH,TT}, 
  value of X for outcome = X(HH)=2, X(TH) =1, X(HT)=1, X(TT) = 0 
  X takes values : 0,1,2. 
  what is P(X=0) = 1/4, P(X=1)= 1/2, P(X=2) = 1/4 
  ```
- **Probability distribution** determines all probabilities of possible values of a random variable. *Given by* a table, graph or formula. 
- **Discrete Random Variable** has finite many different values. Its probability distribution is the collection of all their individual probabilities is 1. 
- **Continuous Random variable** has uncountable many different values. Its probability distribution is given by probability density function. Probability can be counted by area under the function. 

### Steps to find probability distribution of discrete random variable
1. Determine the sample space Ω, of the probability experiment and the probabilities of the outcomes 𝓌. 
2. List teh values X(𝓌) for all 𝓌 in Ω. 
3. For each value x of X, find all simple events {𝓌} with value x. 
4. Probability P({𝓌}) determine the probability of {X = x}: 
   P(X=x) = P({𝓌: X(𝓌) = x}) = ∑ P({𝓌})
5. Prepare a table: left column with all values of x of X. right column with probabilities P(X = x)

## Expectation 

- **Expected Value** of a discrete random variable X with possible values x<sub>1</sub>, ..... x<sub>k</sub> is the weighted average of all possible values of X:  
   
  <center>μ = E(x) = ∑ x<sub>i</sub> . P(X = x<sub>i</sub>)</center>
- **Variance** Variance for discrete random variable X with values x<sub>1</sub>,...x<sub>k</sub>: 
  <center>σ<sup>2</sup> = Var(x) = ∑ [(x<sub>i</sub>  - μ)<sup>2</sup>. P(X = x<sub>i</sub>)]</center>
  The Standard deviation of X is: 
  <center>σ = SD(X) = √Var(X) = √∑ [(x<sub>i</sub>  - μ)<sup>2</sup>. P(X = x<sub>i</sub>)] </center> 
  <center>or</center>
  <center>Var(X) = ∑<sup>k</sup><sub>i =1</sub> [x<sup>2</sup><sub>i</sub>P(X =x<sub>i</sub>)] </center>


- **Law of Large Number** Let X1,...,Xn be n independent versions of random variable X, where X has expected value μ. Then their mean 1/n (X1 + . . . + Xn ) tends to approach μ.

**Continuous Random Variable**  
Has uncountable many different values. Its probability distribution is given by probability density function. Probability can be counted by area under the function.
```
Let X denote a random point between -2 and 1. What is the probability distribution of X?
uniform(−2,1) density

```

- **Normal distribution (continues distribution)** A random variable X has a normal distribution if it has probability density 
  <center><img src="https://render.githubusercontent.com/render/math?math=P(x) = \frac{1}{2\pi}e x^{ -\frac{1}{2}(\frac{x- \mu }{ \sigma })^2}"></center>
- **Standard normal distribution**


