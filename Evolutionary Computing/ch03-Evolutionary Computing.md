# Evolutionary Computing 

## Important points 
- There are different diagrams to represent an EA schemes 
- Variation operators push towards novelity 
- selection operators push towards quality 
- variation operators need to match the representation 
- section operators are independed from the represntation aka from the problem at hand 
- variation operators on the individual level 
- selection operators act on the population level

## Common model 
- Population of individuals 
- individual have a fitness 
- reproduction/ variation operator 
  - mutation 
  - recombination aka crossover 
- selection toward higher fitness
  - survival for the fittest
  - mating of the fittest 
- fitness of population increases over time

## Two pillers of evolution 
- Novelty: variation increasing popluation diversity by `mutation` and `recombination`
- Quality: selection deceasing population by parent and survivors selection 


## Evolutionary Algorithm scheme 
- representation / evaluation / population 
- parent selction / survivor selection 
- Mutation / recombination 


### Representation 
- provides code for candidate solutions that can be manipulated by variation operators
- two levels of existence, phenotype (problem context) genotype (chomosome) 
- two mappting 
  - encoding: phenotype -> genotype (not necessarity one to one)
  - Decodeng: genotype -> phenotype (must be one to one) 

### Evaluation / fitness function 
- represents the task to solve
- enable selection 
- quality function or objective function 
- assings a single real-valued fitness to each phenotype which forms the basis for selection 

### Population 
- the candidate solutions of the problem as individuals (genotypes)
- same elements might occur multiple tiems 
- Population is the basic unit of evolution 
- population is evolving not the individuals 
- selection operators act of popluation level 
- variation operators act on individual level 

### Selection 
- Identifies individusls to become parents and to survive 
- pushes popluation to higher fitness 
- usually probabilistic/stochastic 
- any selection mechanism can be used for parent selection and for survivor selection 
- survivor selection. aka `replacement`
- often deterministic replacement 

### Variation operatos 
- new candidate generation 
- variation operator must match the given represntatin 
- Mutation: cause small random variation 
- acts on one genotype and deliver another 

### Recombination 
- merges information from parents into offspring 
- choice of what information to merge is stochastic 

### Initilisation / Termination 
- Initialisation usually doen at random 
- Termination: achiveving fitness level, number of generations,  diversity level, stagnation 

## Tyeps of EA 
- reprenstation: Binary (genetic algorithms), real-value vactor: evolution strategys, finaite state (Evolutionary programming, LISP tress, genetic programming 
-  vehaviours: stages 
  - quasi-random popluation distribution 
  - mid-stage: popluation arranged around/on hill 
  - Late-Stage: popluation concentraon hight hills 
- EA shows so called anytime behaviour 
- EAs fall into the category of generate-and-test algorithms, a.k.a. trial-and-error algorithms





















