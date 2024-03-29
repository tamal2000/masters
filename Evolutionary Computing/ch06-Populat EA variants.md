# Poplar Evolutionary Algorithm Variants 

## Important points
- There are several incarnations/ dialects/ variants of the genetic EA scheme
- The classic variants are: GA, ES, EP, GP
- Primary applications: 
  - GA: discreate / combinatorial optimization
  - ES: continuous optimization
  - GP: machine learning, modeling
- Methods and tricks invented in one branch can be often applied in other ones
- Some techniques PSO, use non evolutionary metaphors,
- Novel metaphore with bombastic names - these may be equivalent to existing variants 
- The specific type of EA in ot important for pllication 

## Historical EA variants
- Genetic Algorithms (GA): 1960 USA, discrete function optimization, binary representation, not too fast, often modelled by theorists
  - also known as simple genetic algorithm: representations, mutations, crossovers, selection mechanisms, representation is too restrictive, mutation and crossover opertors only applicable for bit-string and integer representations. 
  - Good for combinatoria optimisation, constrain satisfcation, many different varients, large academic fanbase
- Evolution Strategies (ES): 160 germany, numerical optimisation, fast, good optimizer for real world 
  - recombination: averaging parental values or selection one of the parental values 
  - chromosoms consiss of three parts: objective variables, stategy paramets, mutation and roation angeles 
  - parent slection: parents are slected by uniform random distribution 
  - self adaptive follow the optimum and adjust the muation steps asize after every shift 
  - cherry brandy experiment, solution been found without a quantifiable fitness value
  - very good for numerical optimisation
  - low computation budgets and high dimentional problem 
  - self adaptation mutation
- Evolutionary Programming (EP)
  - 1960 USA, Fogel, raditaion ep, prediction by finite state machines, numerical optimization 
  - no recombination, self-adaptation of parameters and standard 
  - aimsed at achieving intelligence, 
  - prediction of the environment was considered a prerequisite 
  - Finite state machine - FSM 
  - Fitness function: 1 pont for correct , 0 point for incorrect prediction. 
  - parent selection: each fsm is selected to be mutatd once 
  - mutation is chosen randomly, add state, delete state
  - survival selection: mu + mu 
- Genetic Programming (GP)
  - 1990's USA, machine learning tasks, slow competes with nn and other ml , non linear chromosomes: tree , graphs, mutation possible but not necessary
  - offspring creation schemes: compare GA scheme using crossover and muation / crossover or mutation 
  - selection: parent selection typically fitness prportiaonate
  - survivor selection: generational scheme 
  - initialisation: maximum initial depth for trees Dmax is set
  - Bloat = survival fo the fattest, the tree sizes in the population are increasing over time 



