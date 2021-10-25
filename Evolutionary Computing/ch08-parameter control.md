# Parameter Control 

## Mutation step size 
- Varying mutation Steps size: arithmetic averaging crossover, 
- standard devidtin sigma is called mutation step size
- option 1: replace the constant sigma by a function sigma(t) changes in σ are independent from the search progress
- option 2: replace the constant sigme by a function sigma(t) after n steps changes in σ are based on feedback from the search progress
- option 3: assign a personal sigma to each individuals, changes in sigma are results of natural selection 
- option 4: assign a personal sigma to each individuals, changes in sigmai are results of natural selection 

## Varying penalties: 
- constraints - inequality contraints and equality constraints are handlled by penalties eval(x) = f(x) + W x penalty(x)
- Option 1: replace the constant W by a function. change W independently from the search progress
- options 2: replace the constant W by W(t) updated in each generate
- option 3: assign a personal W to each individual 


## Component to controll
- deterministic: some rule modifies strategy parameter without feedback from the search - basedon some counter 
- adaptive: feedback rule baed on some measure monitoring search process 
- self-adaptative: parametr values evolve along with tsolutions. 

## Informing the change
- time or no of evaluations (deterministic control)
- Population statistics ( adaptive) progress made, population diversity, gene distribution 
- relateive fitness of individuals 
- absolute evidence: predefined events triggers changes 
- Relative evidence: compare values through solution created with them. 
