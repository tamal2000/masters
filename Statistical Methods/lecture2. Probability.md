# Lecture 2
## Probability Theory

Questions on `Population`  
```
Probability of baby being 21 >= days early. (estimate this with relative frequency)  
in sample of 300 births at least 6 of them were 21 days early.   
So, the relative frequency is 6/300 = 0.02 = 2%
```
**Note** Sample should represent the population.   

Probability in statistics:  `probability of observation.`  
**Testing a claim** Is this coin unbiased?  
**Idea** Does the scenario `fit` the claim? If the claim is true then `non-fitting` have small probability of observation.

## Concepts of Probability
**Probability Experiments:** Production of (random) outcome. Ex: roll a die.  
**Sample Space Ω:** Set of all possible outcome. Example: Ω = {1,2,3,4,5,6}  
**Event:** Collection of outcomes. Ex: A = {even number is thrown} = {2,4,6}
**Simple Event:** Single outcome. Ex: {1}  
**Probability Measure:** Function P(.) assign value between 0 and 1 to events. Ex: P(A) = P({2,4,6}) = 1/2  
**Interpretation:**
* P(A) = 0; outcome A is `impossible`
* P(A) = 1: outcome A is `certain`. Ex P(Ω) = 1
* P(A) < 0.0005 (small): outcome A is `unlikely`.
  
**Three ways to calculate probability**
1. Estimate `Relative Frequency`, P(A)= $\frac{Number of times A occurred}{Number of times procedure was repeated}$
2. Classical (Theoretical) approach: Make probability model and compute P(A). Ex: Through coin three times: Sample space Ω has 2x2x2x = 8 outcomes; Ω = {HHH,HHT,HTH, THH,HTT, TTH, THT, TTT}
3. Subjective Approach: Intuition/and or experience. Example: Ajax made to semi-final last year. Probability of Ajax win this year is $\frac{1}{3}$

**Example of RF:** A player attempted 644 free throws, he scored 577. Probability of he hits is $\frac{577}{644} \approx0.896.$

**Theory of Large Numbers:** If a procedure is done again and again and outcomes are independent, then the RF of an event A is trends toward true P(A).  

**Counting Principle:** If experiment A has a>0 possible outcome and experiment B has b>0 outcome then experiment both have axb possible outcome.   
*Example 1*: license plate has 3 digit and 3 number then total number of possible outcome is $26^3 x 10^3 = 17 567 000$.   
*Example 2:* A vase with 3 red balls, 2 orange and 1 blue balls. Outcome space Ω = {red, orange, blue}, P(red) = $\frac{1}{2}$, P(orange) =$\frac{1}{3}$ P{blue} = $\frac{1}{6}$

