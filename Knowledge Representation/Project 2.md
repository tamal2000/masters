# Project 2

**Deadline:** 16th Oct : 12

## Part 1: building a forgetting-based explanation tool for DL reasoning 
1. Justification for an entailed formula F is a minimal subset of teh original knowledge based that still entails F. 
    - Justifications are not unique. 
    - As justifications are significantly smaller than the original KB. 
    - easier to understand.
2. Sometiems has to explain why F follows from the justifications. 
    - A new way for doing this is to reason by forgetting. 
    - The result of forgetting a signature from a knowledge base KB is thereby another knowledge base that entails the same formulas than KB on the restircted vcabulary. 

forgetting the idea is to calculate a sequence of KBs with decreasing vocabulary by a sequence of forgetting oerations on the justifications of an entailment. 

## Steps: 
1. Calculate teh concept heirarchey of KB. F = (C subclass D) that is entiled by KB. 
2. for each subclass statement calculate all justifications 
3. Design a strategy for the order in which to forget all the vocabulary not in F 
4. For each justification J for F apply a forgetting algorithm to calculate the sequence of KBs 

# Updated guideline - 6 Oct'20
 Update github files 
* Choose an ontology: Real-life, toy or abstract 
* Find the number of interesting subclass relation 
    - see one of sub class produces longer or complicated justification 
    - by using the myProgram.py 
* Run explanation by forgetting by choosing different symbols 
* load ontology in protege
* Explanation by forgetting 
    1. scaling  up your experiments, or 
    2. doing a more in-depths study.
* notion of "goodness of an explanation" 
    - you use it to evaluate different methodological choices you implement b


