# Memetic Algorithm 

## Important points
- Memetic algorithm = EA hybridised with other heuritics
- Hybridisation offers the best of both worlds: 'blient' evolution + problem specific "intelligence" 
- - known operators from other algorithms for the given problem can be used 
- domain specific kowlege can be used
- its is common practice to hybridise EAs in a real world application 
- MAs have been shown to be orders of magnitude faster and more accurate than EAs on some problem 
- MAs are the "state of the art" on many problems 
- if you can hybridise: do it



## Hybridisation
- Combination of an EA algorithm with another problem solving Heuristic 
- Improve EA 
- Improve existing techniques 
- Put EA in to larger system 
	
## Michalewich' view on EA in context 
EA enriched with knowledge 

## Memetic algorithm 
- The combination of EA with local search operators that works within the EA loop has been termed as memetic algorithms
- Memetic algorithms have been shown to be orders of magnitude faster and ore accurate than EAs on some problem 
- information copied from person to person / self-replicator 

## Hybridise
- Initial Population: known solutions: 
	- for each individual in initial population: n - tournament amongst randomly created candidate solutions
	- Multi-start local search: pick popsize points at random 
	- issues: archive apprach, already known, surry & Radcliffe: incculating popluation, found mean performance increase but best performance comes for randomness.  
- Crossover: User of problem specific information
- Offspring: Local search
	- lifetime learning: often used to speed-up the `end game` 
	- overall strategy: is the neighbourhood searched randomly, systematically or exhaustively
	- stopping: greedy ascent, steepest acesnt 
	- Most Memetic Algorithms use an operator acting on a single point, and only use that information
	- Local search pushes strongly towards better points  is subject to quickly losing diversity 
	- very likely to acceept worse neighbours c is large
	- c is small less likely to accept worst neighbours 


- Mutation: use of problem specific information 

- Selection: modified selection operator
- Boltzman selection operator: 
	- early stage more exploration, late stage more exploitation 
- Choice of operators: Can be helpful since local optimum on one landscape might be point on a slope on another
- Adaptive Memetic algorithm: Most important in MAs that incorporate local search or heuristic improvement is the choice of an good move/search operator

