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
* General probability of finite/countable sample space Ω: 
  + Outcome w ∈ Ω: P(w) ≥ 0, ∑<sub>w ∈ Ω</sub> = 1
  + A probability of an event, P(A) = ∑<sub>w ∈ A</sub> P(w)
  ```
  Step 1: Find the sample space Ω, 
  Step 2: Determine the probabilities: P(w) for all w in Ω, 
  Step 3: Determine the outcome belong to
  Step 4: Compute, P(A) = `∑<sub>w ∈ A</sub> P(w)`
  ```
## Addition Rule: 
Every outcome is count only once.  
Two cards pies of cards are faced down, each pile has one spade and one hearts. The probability of picking a spade is:   
**Count:** Sample Space Ω = {SS, SH, HS, HH} and then equally {a spade} = {SH, SH, SS}, hence a spade = $\frac{3}{4}$.  
**Sub:**: P(a spade) = P(spade from pile 1) + P(spade from file 2) - P(spade twice) = $\frac{1}{2}+\frac{1}{2}-\frac{1}{4}= \frac{3}{4}$  
```
P(A or B) = P(A) + P (B) - P(A and B)
P(A ⋃ B) = P(A) + P(B) - P(A ⋂ B)
```
**Notations**
  * **Union:** A ⋃ B = A or B
  * **Intersection** A ⋂ B = A and B
  ```
  Example: Three coin toss (tail twice or head in first through).  

  Ω = {HHH, HHT, HTH, THH, TTH, THT, HTT, TTT}  
  P(tail twice), P(A) = {TTH, HTT, THT} = 3/8 
  P(Head first), P(B) = {HHH, HHT HTT, HTH} = 1/4 
  P(A ⋂ B) = {HTT} = 1/8

  ∴ P(A ⋃ B) = P(A) + P(B) - P(A ⋂ B)
             = 3/8  + 1/4  - 1/8
             = 3/4
  ```

**Disjoint:** A and B are disjoined if they excluded each other.  
        P(A ⋃ B) = P(A) + P(B)  
General addition rule for disjoint events: P(A<sub>1</sub> ⋃. . .⋃ A <sub>m</sub> ) = $\sum$ P(A<sub>i</sub>)
```
Example 1: The probability of throwing a three or even number.
P(A ⋃ B) = P(A) + P(B)
         = 1/6 + 1/2 = 2/3
Example 2: Rolling two fair dice, whats is the probability of "sum equals to 4, 8, 9"?
Find Sample space, Ω = {(1,1),(1,2)...(6,6)}, contains 6x6 = 36  
Find Event spaces -  
A(Sum is 4) = ({1,3},{3,1},{2,2})
P(Sum is 8) = {(2,6),(6,2),(3,5),(5,3),(4,4)}
P(Sum is 9) = {(3,6),(6,3),(4,5),(5,4)}
P(sum 4, 8 or 9) = P(A) + P(B) + P(C) 
                 = 3/36 + 5/36 + 4/36 = 1/3 
```
**Compliment Rule**
Compliment of A; outcomes which are not in A<sup>c</sup>. P(A<sup>c</sup>) = 1 - P(A)
```
Example: Three fair coin tosses, what is the probability of at least one Heads?
Sample space Ω = {HHH,HHT, HTH, THH, HTT, THT, TTH, TTT} = 2x2x2 = 8 
Event space: 
A (no head) = {TTT} = 1
P(A) = 3/8
P(A compliment) = 1 - 1/8 = 1/8
```

## Conditional Probability
P(B|A): conditional probability that B occurs given that A has occurred.   
General formula: `P(B|A) = P(A ⋂ B) / P(A)`
and, in general: `P(B|A)≠ P(A | B)`
```
Example 1: rolls die twice and first one is 3, the probability of sum equals to 8?
Given first die is 3,  
the possibilities are {(3,1),(3,2),(3,3),(3,4),(3,5),(3,6)} = 6. 
the conditional probability of each outcome is 1/6
'sum is 8' (3,5) the desired probability is 1/6 
P(A ⋂ B) = P((3,5)) = 1/36, P(A) = 1/6, so P(B|A) = 1/6
```
```
Example 2: 2 coin tosses, what is the conditional probability of "twice head" given that.  
  1. the first flip is heads?
  2. there is at least one heads?
Ω = {HH,HT,TH,TT}, B = {HH}, 
1. first flip is head, {HT,HH}, P(B |A ) = P(A⋂B)/P(A) = 1/4 / 1/2 = 1/2
2. At least one head {HT,TH,HH}, P(B|A) = P(A⋂B)/P(A) = 1/4 / 3/4 = 1/3
```
## Multiplication Rule:
P(A ⋂ B) = P(A) . P(B|A)
```
Example 1: Vase with 9 balls,labeled 1 to 9. If we draw two balls, after each other, what is the probability of first (1) and then end is (2). 
Solution 1: Counting method: Ω = {(1,2)....(9,8)} = 9x8 = 72 elements
So: P((1,2)) = 1/72
Solution 2: Multiplication method - 
P(first1). P(draw 2 | ball is draw) = 1/9.1/8 = 1/72
```
```
Example 1: Vase with 9 balls,labeled 1 to 9. If we draw two with replacement, after each other, what is the probability of first (1) and then end is (2). 
P(first 1, then 2) = P (A ⋂ B) = P(A). P(B | A) = 1/9 . 1/9 = 1/81
```
### Independence
Two events A and B are independent if P(A⋂B) = P(A) . P(B), Thus P(B) = P (B|A)

```
Example: roll die twice. are A = {first 1} and B = {sum is 7} independent?
Ω = 6x6 = 36
P(A) = P{(1,1),(1,2),(1,3),(1,4),(1,5),(1,6)} = 6/36 = 1/6
P(B) = P {(1,6),(6,1),(2,5),(5,2),(3,4), (4,3)} = 6/36 = 1/6
P(A).P(B) = 1/6 . 1/6 = 1/36
P(A ⋂ B ) = P {(1,6)} = 1/36
here, P(A ⋂ B ) = P(A). P(B), so A and B are independent. 
```

### Sampling Method:
- sampling with replacement
- sampling without replacement   

`Small Sample Rule:`
when a small sample from a large population is taken, the selections are treated as independent events. 