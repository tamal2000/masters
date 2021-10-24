# Problems to be solved

## Importent Points 
- Blackbox problem types 
  - optimization - when input is unknown 
  - Modeling - when model is unknown 
  - Simulation - when predicding the output 
- Problem types 
  - FOP - Free constrain optimization problem 
  - COP - Constrain optimization problem 
  - CSP - Constrain Satisfaction problem 
  - NP - np problems 
- Problem hardness 
  - NP Problem 
  - NP Complete 
  - NP Hard problem 

## Black Box Problem 
### Optimization 
When Model and output is known, task is to find the inputs. Examples: time table, design specification, 
travelling salesman TSP, Eight-qeens problems, etc. 

### Modeling 
When corresponding sets of input and outputs are seeks model that delivers correct output for every known input. 
Modelling problems can be transfomred into optimisation problems. examples: Evolutionary machine learning, 
predicting stock exchange, voice control system for smart homes. 

### Simulation 
When a given model and whish to know the output that arises under different input conditions. Weather forecast, impact analysis, evolutionary economics. used as "what if" questions 

## Search Problem 
Optimzation and modeling problem search through large space of possibilities  
**Search Space:** collection of all objects of interest including the disired solutions.   
**Note:** search `problems`, which difines the search space, and `problem solver` which movies thourgh 
the search space fo find a solutions 

## Optimization vs Constrain satisfaction 
### Objective function
A way of assigning a value to a possible solution that reflects its quality on scale. maximize or minimize
### Constrain
Binary evaluation tellting whether a given requirement holds or not. 

|              | objective                         | Function                       |
|--------------|-----------------------------------|--------------------------------|
| Constraints  | Yes                               | No                             |
| Yes          | Constrained Optimization Problem  | Constrain Satisfaction Problem |
| No           | Free Optimization Poblem          | No Problem                     |

## NP Problem Class
- **Class P:** Some algorithm can solve the problem in polynomial time 
- **Class NP:** Problem can be solved and any solution can be verified wihtin polynomial time by some algorithm 
- **Class NP-complete:** Problem belongs to class NP and any other problem in NP can be rduced to this problem by and alogithm running in polynomial time. 
- **NP-hard:** Problem is at leat as hard as hard as any other problem in NP-complete but solution cannot be verified within polynomical time. 







