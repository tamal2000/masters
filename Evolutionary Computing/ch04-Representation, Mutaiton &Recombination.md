# Representation, Mutation and REcombination 

## Important points 
- Representation is essentail when designing and EA 
- Afew data structrues are enough to represent many 
- For any given problem, there can be many suitable reprentation 
- Reproduction operatiors must fit represntation 
- Reprodciton operators can be distingushed by airt 
- repreduction operation are stochastic 

## Common Representatin of Genomes
Binary, Integer, real-value or float, permutation, tree

- What are possible representations for TSP Problem - Permutation 
- representation is in genotype space 
- binary string to positive string integer mapping need instance gray code aka reflected binay code mapping to avoid genotypics distance 
- **Strong causality principle:** Small alterations in the underlying structure of an object causes small changes in the object's behaviour 
- **Binary:** Genotype consists of a string of binary digits
  - Mutation: Alter each gene independently with a probability, mutation rate p<sub>m</sub>. between 1/pop_size and 1/chromosome_length
  - 1-point crossover: Choose a random point on the two parents, split parents at the crossover point and create childrend by exchanging tails 
  - Alternative crossover: 1-point cross over may keep together nenes known as positional bias, 
  - n-point crossover: choosn n random point, split along those points, glue part, alternating between parents. (still may have some positionatl bias)
  - Uniform Crossover: assign heads to one parent, tails to the other, flip a coin for each gene for the first child, make an inverse copy of the gene for the second child 
  - Crossover or Mutation: depends of the problem but good to have both 
  - **Exploration:** discovering promising areas in the search space. gaining more information. crossover is explorative 
  - **Exploitation:** Optimizing within a promising area using information, Mutation is exploitative. it creates rndom small variations, thereby stying near the parent. 

### Integer Representation 
- now a days its better to encode numerical variables directly instead of encoding them as binaries 
- Some problem naturally have integer valeus 
- other takes categorical values, they are symbols not numbers 
- N-point / uniform crossover operators work as previously 
- Bit-flip mutation can be generalized to random resettings. 
- z  [x,y]   represented by {a1,…,aL}  {0,1}L  where L is the user defined chromosome length
- 2<sup>L</sup> values out of infinite are represneted 
- L determines possible maximum precision of solution 
- High Precision -> long chromosomes -> slow evolution. 
- real-vlue mutation - Uniform muation/non-uniform mutation. random nosie with each variable x<sup>'</sup><sub>i</sub> = x<sub>i</sub> + N(0, mu)
- Self-adaptive Mutaion: sigma -> sigma', then x' -> x + N(0, sigma')
- real-value uncorrelated mutaion: simga' = sigma . exp(tao. N(0,1) + tao . Ni (0,1)); xi' = xi + sigma'i . Ni (0,1); tow' overall learning rate, tow' coordinate wise learning rate. 
- Covariance Matrix adaptation evolution strategy is one of the best EA fro numerical optimization. 
- Recombination: each offspring z comes from on of its parents. Intermediate: exploits idea of creating children between parents aka arithmetic recombination. z = alpah xi + (a - alpha) yi 

#### Multi parent recombination
Type 1: 
- segment and recombine parent
- diagonal crossover for n parents. 
- choose n-1 crossover points 
- compose n children from the segments of the parents in along a diagonal wrapping around 

Type 2: 
- arithmetical combination of alleles 
- ith alles in chaild is average of the parther ith alleels 
- created center of mass as child 

### Permutation Representation: TSP example 
- ordering/sequencing prblems from a special types
- task arranging some objects n a centrain order 
- if there are n variables then the representation is as a list of n integers each of which occurs exactly once. 
#### Mutaiton 
- Normal mutation operators lead to inadmissible solutions, therefore must change at leat two valeus 
- mutation parameter now reflects the probabilites that some operator is applied once to the wole string, rather than individually in each postion. 
- Swap mutation: pick two alleles at random and swap their positions 
- Inset Mutation: pick two allele values at random move the second to follow the firs, shifting the rest 
- Scramble mutation: pick a subset of genes at random and rearrange the alleles 
- Inversion mutation: pick two alles and then invert then substrings between them. 

#### Crossover 
- preserve relative order that elements occur 
- choose an arbitrary part from the first parent, copy this part to the first child, copy the numbers that are not in the first part , analogues for the second child 
- Partially Mapped crossover: PMX: choose random segment and copy from it from P1, starting 
- Cycle Crossover: elle comes from one parent toger with its position
- edge recombination: make list of tables and add + if two parent have common edge 

### Tree Representation
- trees are a universal form 
- chromosomes are linear structrues, but tree spaped chormosomes are non- linear structrues 
#### Mutation 
- replace randomly choosen subtree by randomly generated tree
- two paramets - prbability of choose mutation and internal pont of subtree 
- Pm is advised to be 0 or very small 
- size of child can exceed the size of the parent 
#### Recombination 
- Exchange two randomly chossen subtress among the parents 
- - probability Pc to choose recombniation 
- probability to choose an internal point within each parent cross over point. 

