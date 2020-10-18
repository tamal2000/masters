# Probabilistic Graphical Model 
--------

* Probabilistic graphical modes is a major field in AI
    * choice of representing uncertainty.
    * Representing a potentially complex system compactly 
    * Stand alone model, representing the world. 

Classical - Binary system - Possible / Not possible.  
A `degree of belief` of `probability` in [0,1] world w: Pr(w).  
`Probability` of  given sentence  $\alpha$ $Pr(\alpha) = \sum{Pr(w)}$

**State of belief** or `joint probability distribution`. 
- Pr(Earthquake) = Pr(w1) + Pr(w2) = .1 

**Properties of Belief** 
- 0 ≤ Pr(a)≤ 1 ; for any sentence `a`
- Pr(a) = 0 ; when `a` is inconsistent
- Pr(a) = 1 ; when `a` is valid 
- Pr(a) + pr(¬a) = 1 
- `Pr(a V b) = Pr(a) + Pr(b) - Pr(a ^ b)`
- `P(a v b) = P(a) + P(b) ; when a and b are mutually exclusive 

**Updating Belief/Probability** for known value (given): 
- Given ß, update Pr(.) to Pr(.|ß)
- hence, P(.|ß) to assign a belief of 1 to ß: P(ß|ß) = 1
- implies, P(¬ß|ß) = 0 and hence, every world w that satisfy ¬ß must be assigned the belief 0
    - P(w|ß) = 0 for all w ⊨ ¬ß
- Update: 
    - ∑Pr(w|ß) = 1 
    - P(w|ß) = 0 for all w where Pr(w) = 0 (impossible world)
    - relative probability of positive probability: 
        - Pr(w)/Pr(w') = Pr(w|ß)/Pr(w'|ß) 
        - hence, `P(w|ß) = P(w)/Pr(ß)`

**Independence** A and B are independent in Pr if Pr(A|B) = P(A) or P(B) = 0 

**Join Probability of Independent**
- P(A ^ B ) = P(A).P(B)

**Graphical tool for independence** 
- nodes represent propositional variables 
- edges represent direct causal influences 

