# Fitness, slection, Population Management 

### Important Points
- Selection increase quality, decreaes diversity 
- selection can occur at two places in the evolution loop, parent selection and survivor selection
- Most selection operators can be used for both purpose 
- Selection pressure is an important feature of EA
  - Strong selection -> too fast convergence, local optima 
  - Weak selection -> slow progress, almost random walk 
- Keeping up diversity is important 
- There are specific mechanisms for this in EAs 

## Population Management 
- Generation model: each individual survies for exactly one generation 
- Steady state model: a few new individuals are generated per generation 
- Generation Gap: The proportion of the population replace: 1.0 means Generational EA, <1.0 means steady state EA 

## Selection: 
Fitnes based competition 
- Parent selection: individuals from current generation to take part in mating 
- Survior selction: indiidual from parent + offspring to go into next generation 
- Fitness-Proportionate selection, FPS: P(i) f / Sum(fj), probabilities for individual to be selected for mating in apopulation of size mu with FPS, one high fit member can rapidly take over. 
- Scaling: windowing and sigma scaling 
rank based selection 
- attempt to remove problems of FPS by basing selection on probabilities on relative rather tan absolute fitness 
- Linear ranking: parametrise by factor s: 1 < s <= 2 
- Exponential Ranking: P_exp(i) = 1-e/c 

### Sampling algorithms 
- roullet wheels
- stochastic nunversal samples 
- Tournamet selection: All method otherthan this depends on global population. this one is using local fitness information, pick k memeber at random then select the best of these
- Uniform Parent selection P_u = 1/mu 
- Survivor selction: select mu indiiduals to form the next generation from mu parents and lama offspring. 


## Survivor Selection 
- parent selection machanisms can also be used for selection survivors
- survior can be selected baed on fitness based or age based 
- Elitsim: always keep at least one copy of the fittest 
- Delete wost: 
- Round robin tounament: pariwise competitions in round robin format 
- finess based survivor selction: 
  - comma strategy (mu, lambda)
  - plus strategy ( mu + lambda)

## Slection Pressure 
- takeover time two* is a measure to quantify the selection pressure
- it is the number of generations it takes until the application of selection completely fill the population with copies of the best individuals 
- Multidodality: most interesting problem have more than one locally optimal solution 
- Approaches for presevign diversity: 
  - explicit: make similar individual compete for resource , finess sharing, crowding 
  - implicit: impose and quivalent of geographic sparation, automatic speciation, Island models, cellular eas
  - 
  - 
  - 
- 
- 
